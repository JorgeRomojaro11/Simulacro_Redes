# Simulacro_Redes


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

#### 📌 Proceso inverso en la recepción:
1. **Capa de Acceso a Red** recibe los datos y los envía a la **Capa de Internet**.  
2. **Capa de Internet** revisa la dirección IP y pasa los datos a la **Capa de Transporte**.  
3. **Capa de Transporte** reensambla los datos y los pasa a la **Capa de Aplicación**.  
4. **Capa de Aplicación** entrega los datos a la aplicación correspondiente.  

---

### 📌 Conclusión
Este simulacro cubre los conceptos esenciales de redes, incluyendo modelos de comunicación, protocolos y procesos clave como la resolución de nombres y la capa de transporte.  

📌 **Referencias**:  
Este contenido se basa en la teoría de redes y protocolos TCP/IP y OSI.  
