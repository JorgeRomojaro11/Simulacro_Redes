# Simulacro Redes

## Parte I: Conceptos y Teoría

### Pregunta 1: Modelos OSI y TCP/IP

#### a) Diferencias entre el modelo OSI y el modelo TCP/IP

1. **Número de capas**:
   - El modelo **OSI** tiene **7 capas** (Aplicación, Presentación, Sesión, Transporte, Red, Enlace de Datos y Física).
   - El modelo **TCP/IP** tiene **4 capas** (Aplicación, Transporte, Internet y Acceso a la Red).

2. **Orientación**:
   - **OSI** es más **teórico** y sirve como referencia para entender la comunicación en redes.
   - **TCP/IP** es más **práctico**, basado en protocolos reales usados en Internet.

3. **Capa de aplicación**:
   - En **OSI**, la capa de Aplicación se divide en tres: **Aplicación, Presentación y Sesión**.
   - En **TCP/IP**, la capa de Aplicación **engloba estas tres funciones en una sola capa**.

#### b) Ventajas y limitaciones de cada modelo

**Modelo OSI**  
**Ventajas**:  
- Ayuda a entender mejor la comunicación en redes.  
- Es modular, facilitando el desarrollo de nuevos protocolos.  

**Limitaciones**:  
- No fue adoptado completamente.  
- Es más teórico y no se aplica directamente en muchas redes.  

**Modelo TCP/IP**  
**Ventajas**:  
- Se usa en la práctica, especialmente en Internet.  
- Tiene menos capas, lo que lo hace más simple y eficiente.  

**Limitaciones**:  
- No separa algunas funciones con tanto detalle como OSI.  
- No tiene capas específicas de Presentación o Sesión.  

---

### Pregunta 2: Función de la Capa de Transporte

La **capa de transporte** gestiona el envío de datos de manera organizada y eficiente. Su objetivo principal es **asegurar que la información llegue correctamente al destino**.

#### 1. Funciones principales:
- **Entrega de datos de extremo a extremo**: Divide la información en segmentos y los reensambla en el destino.
- **Control de flujo**: Evita que el receptor se sature con demasiados datos.
- **Corrección de errores**: Verifica que los datos lleguen sin alteraciones.
- **Multiplexación**: Permite que varias aplicaciones usen la red sin interferencias.

#### 2. Protocolos de la capa de transporte:

- **TCP (Transmission Control Protocol)**:
  - Asegura que los datos lleguen completos y en orden.
  - Establece una conexión antes de la transmisión.
  - Usado en navegación web, correos electrónicos y transferencias de archivos.

- **UDP (User Datagram Protocol)**:
  - No garantiza orden ni integridad, pero es más rápido.
  - No necesita establecer una conexión previa.
  - Usado en videollamadas, transmisiones en vivo y videojuegos.

---

### Pregunta 3: TCP vs. UDP

| Característica        | TCP                                        | UDP                          |
|----------------------|--------------------------------|------------------------------|
| **Orientación a conexión** | Sí (requiere "handshake") | No (envía datos directamente) |
| **Fiabilidad** | Sí, garantiza entrega y orden | No, no garantiza entrega ni orden |
| **Velocidad** | Más lento (verifica y corrige errores) | Más rápido (sin correcciones) |
| **Ejemplos de uso** | HTTP, HTTPS, FTP, correo | VoIP, streaming, videojuegos |

---

### Pregunta 4: Protocolo para Transferencia de Archivos

#### a) Protocolo tradicional
**FTP (File Transfer Protocol)** permite la transferencia de archivos en redes TCP/IP. Funciona con **TCP**, garantizando que los datos lleguen completos y en orden. Sin embargo, **no cifra los datos**, lo que lo hace inseguro en redes abiertas.

#### b) Alternativas seguras
1. **SFTP (SSH File Transfer Protocol)**: Usa SSH para cifrar la transferencia, protegiendo la información.  
2. **FTPS (FTP Secure)**: Agrega cifrado SSL/TLS a FTP, manteniendo compatibilidad con sistemas que usan FTP tradicional.  

---

### Pregunta 5: Resolución de Nombres en DNS

Cuando un usuario ingresa una URL en su navegador, el sistema la **traduce a una dirección IP** siguiendo estos pasos:

1. **Búsqueda en caché**: Se revisa si la dirección IP está almacenada localmente.  
2. **Consulta al servidor DNS recursivo** (ISP o servicio público).  
3. **Consulta a los servidores raíz**, que redirigen al servidor **TLD** (dominio de primer nivel).  
4. **Consulta al servidor autoritativo**, que proporciona la **IP real** del sitio.  
5. **Conexión al servidor web**, usando la dirección IP obtenida.  

---

### Pregunta 6: Comunicación en el Modelo TCP/IP

El modelo **TCP/IP** tiene **4 capas**, cada una con un rol específico:

1. **Capa de Aplicación**  
   - Interacción entre aplicaciones y la red.  
   - Protocolos como HTTP, FTP, SMTP preparan los datos.  

2. **Capa de Transporte**  
   - Divide los datos en segmentos y garantiza su entrega.  
   - **TCP** asegura orden y fiabilidad, **UDP** envía sin comprobaciones.  

3. **Capa de Internet**  
   - Encapsula segmentos en paquetes y asigna direcciones IP.  
   - **IP (Internet Protocol)** se encarga del enrutamiento.  

4. **Capa de Acceso a Red**  
   - Convierte paquetes en tramas y los envía físicamente (cableado o Wi-Fi).  
   - Usa direcciones MAC para identificar dispositivos en la red local.  

#### Proceso inverso en la recepción:
1. **Capa de Acceso a Red** recibe los datos y los envía a la **Capa de Internet**.  
2. **Capa de Internet** revisa la dirección IP y pasa los datos a la **Capa de Transporte**.  
3. **Capa de Transporte** reensambla los datos y los pasa a la **Capa de Aplicación**.  
4. **Capa de Aplicación** entrega los datos a la aplicación correspondiente.  

# Parte II: Capa Física y Ejercicios Prácticos 

## Pregunta 7: Cálculo de Tasa de Transmisión Máxima (Fórmula de Shannon) 

Utiliza la fórmula de Shannon: 

\[
C = B \times \log_2(1 + SNR)
\]

donde: 

- **C** es la tasa de transmisión máxima (bps). 
- **B** es el ancho de banda (Hz). 
- **SNR** es la relación señal a ruido en escala lineal (recuerda que \( SNR_{\text{lineal}} = 10^{SNR_{\text{dB}} / 10} \)).

### Enunciado:
Calcula la tasa de transmisión máxima para un canal con las siguientes características:

- **Ancho de banda:** 500 MHz 
- **SNR:** 20 dB 

### Cálculos:

#### 1. Convertir el SNR de dB a escala lineal: 

\[
SNR_{\text{lineal}} = 10^{\frac{SNR_{\text{dB}}}{10}}
\]

Para \( SNR = 20 \) dB:

\[
SNR_{\text{lineal}} = 10^{\frac{20}{10}} = 10^2 = 100
\]

#### 2. Sustituir en la ecuación de Shannon: 

\[
C = 500 \times 10^6 \times \log_2(1 + 100)
\]

Aproximando \( \log_2(101) \approx 6.658 \):

\[
C = 500 \times 10^6 \times 6.658
\]

\[
C \approx 3.329 \times 10^9 \text{ bps} = 3.329 \text{ Gbps}
\]

---

## Pregunta 8: Ubicación de Portadoras para Eficiencia Espectral 

Dado que en un sistema de comunicación la primera portadora se encuentra a **1.2 GHz** y 
el ancho de banda en banda base de cada canal es de **300 MHz**, determina: 

1. **Frecuencia de la portadora anterior**  
   \[
   1.2 \text{ GHz} - 300 \text{ MHz} = 0.9 \text{ GHz}
   \]

2. **Frecuencia de la portadora posterior**  
   \[
   1.2 \text{ GHz} + 300 \text{ MHz} = 1.5 \text{ GHz}
   \]

### Importancia de la Ubicación de Portadoras:

- Evita solapamiento de canales para minimizar interferencias. 
- Maximiza el uso del espectro al colocar portadoras eficientemente. 
- Permite **multiplexación por división de frecuencia (FDM)**. 

---

## Pregunta 9: Identificación de Modulación en Función del BER 

Se sabe que la robustez ante el ruido de una modulación depende del número de 
símbolos por baudio, de manera que:

- **BPSK (2-QAM)** es la más robusta. 
- **QPSK (4 símbolos)** ofrece el doble de eficiencia que BPSK. 
- A medida que se incrementa el número de símbolos (**16-QAM, 64-QAM, 256-QAM**), 
  la eficiencia aumenta pero la tolerancia al ruido disminuye. 

### Orden de robustez ante el ruido (de mayor a menor): 

1. **BPSK (2 símbolos) → Más robusta**
2. **QPSK (4 símbolos)**
3. **16-QAM (16 símbolos)**
4. **64-QAM (64 símbolos)**
5. **256-QAM (256 símbolos) → Menos robusta**

**Conclusiones:**
- **Más símbolos = mayor eficiencia, pero más sensibilidad al ruido.**  
- **BPSK** es la más resistente porque tiene solo dos símbolos bien separados.  
- **QPSK** duplica la eficiencia de **BPSK** sin perder mucha robustez.  
- **16-QAM, 64-QAM y 256-QAM** aumentan la velocidad, pero necesitan alta SNR para evitar errores.  

---

## Pregunta 10: Eficiencia del Sistema de Encapsulamiento 

Considera un sistema de encapsulamiento con la siguiente configuración:

- **Capa 5:** Envía un bloque de datos de **1.5 Kbytes** (1 Kbyte = 1024 bytes). 
- **Capas 4 y 3:** Cada una añade una cabecera de **40 bytes**. 
- **Capa 2:** Permite el envío de tramas de **400 bytes** como máximo. 
- **Capa 1:** Por cada 2 bytes de datos, se añaden: 
  - **8 bits (1 byte) de inicio**  
  - **1 byte de parada**  
  - **8 bits (1 byte) de CRC**  

### Cálculos:

#### a) **Tamaño total del mensaje después de las cabeceras de Capa 4 y 3**  
\[
T_{\text{mensaje}} = 1536 + 40 + 40 = 1616 \text{ bytes}
\]

#### b) **Número de tramas de 400 bytes**  
Cada trama puede contener **400 bytes**, pero debemos considerar las cabeceras:

\[
\frac{1616}{400} = 4.04 \Rightarrow 5 \text{ tramas necesarias}
\]

#### c) **Sobrecarga de Capa 1**  

Cada **2 bytes de datos** → **3 bytes adicionales**  

- **Cada trama tiene 400 bytes**  
- **Datos por trama**:  
  \[
  \frac{400}{3} \times 2 = 267 \text{ bytes}
  \]
- **Sobrecarga por trama**:  
  \[
  400 - 267 = 133 \text{ bytes}
  \]
- **Total de sobrecarga**:  
  \[
  133 \times 5 = 665 \text{ bytes}
  \]

#### d) **Eficiencia del Sistema**  

\[
\text{Eficiencia} = \left( \frac{\text{Datos Útiles}}{\text{Total de Datos}} \right) \times 100
\]

\[
\text{Eficiencia} = \left( \frac{1536}{1536 + 665} \right) \times 100
\]

\[
\text{Eficiencia} = \left( \frac{1536}{2201} \right) \times 100
\]

\[
\text{Eficiencia} \approx 69.8\%
\]


 
