# IPSec y TLS

Se añade TLS a la capa SSL en la propuesta de Netscape para añadir la seguridad que no tienen los protocolos. Soluciones propuestas:

### Confidencialidad

Cifrado simétrico

### Integridad

Funciones hash

### Autenticación

Certificados por PKI (Public Key Infrastructure)

## Obtención de claves en cifrado simétrico:

### Generación por Diffie-Hellman

### Intercambio de claves por cifrado RSA



## Intercambio de claves:

* Para pasar un mensaje que solamente la otra persona pueda descifrar, cifro con la clave pública del receptor y con eso ya le puedo compartir la clave simétrica con la que vamos a cifrar el resto de los mensajes. El cifrado asimétrico es \*muy costoso\* y lento, por eso nunca se cifra en asimétrico sino en simétrico, porque es más rápido.
* Servidor y cliente usan un nonce (números que se usan una única vez, para prevenir ataques de reproducción, “grabar una conversación y repetirla después”, generado aleatoriamente + fecha y hora para que no vuelvan a salir), que no me preocupa que se vean (van en claro).
*   Ambos hosts usan varias claves:

    * Ka, Kb: para que no se “desgasten” las claves, cada host descifra con una.
    * Vectores de inicialización, IV1 IV2.
    * MAC: Message Authentication Code, con funciones hash hago H(MAC1+m+MAC2), es decir, HMAC.

    TLS: basado en Record y Handshake.

    TLS Nonces: se calculan cada uno en un sentido a partir de un IV y haciendo XOR con el número de secuencia de 64-bits

    TLS Padding: se ajusta la longitud para evitar análisis de tráfico y tener longitudes similares.

### TLS Record:

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

### TLS Handshake:

<figure><img src="../../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

### Client Hello

Versión, RandomNumber (Nonce formado por 28 bytes + 4 fecha), SessionID, CipherSuites (lista de algoritmos y tamaños que soporta el cliente) y CompressionMethods (métodos de compresión soportados). Si un servidor se niega a utilizar un tipo de cifrado, puede rechazar la comunicación. Estructura de un CipherSuite:

<figure><img src="../../.gitbook/assets/image (15) (1).png" alt=""><figcaption></figcaption></figure>

### Server Hello

Igual, pero hace la elección del CipherSuite del cliente, así como el método de compresión (no permitido en TLS 1.3)

### Certificate

El server envía el certificado de confianza, que el cliente comprueba si es legítimo (no revocado, no expirado, etc.)

### **ServerKeyExchange**

**S**i es necesario, hay que enviar los valores necesarios para el intercambio de claves. Con DH sí que hace falta por los valores intermedios de los cálculos, en RSA no.

### **CertificateRequest**

Si así lo pidiese el server, el cliente se auténtica. Le pasa CertificateTypes (lista de certificados admitidos) y DistinguishedNames (lista de nombres admitidos)

### **ServerHelloDone**

Todo correcto, no envía nada más.

### **Certificate**

Si el 5 fue solicitado, el cliente lo envía.

### **ClientKeyExchange**

Se envía info al server sobre la clave utilizada en el cifrado simétrico, Pre-Master Secret. En RSA, el cliente manda la PMS cifrada con la clave pública (enviada en fase 3), mientras que en DH manda el material necesario para los cálculos y que así el servidor tenga la PMS que ya puede calcular el cliente.

### **ChangeCipherSpec**

**A** partir de este momento la comunicación va cifrada (cliente -> server).

### Finished

El cliente envía al server un hash de toda la info intercambiada para comprobar que nadie se haya metido entre medias, y el server hace el mismo hash para comprobar si concuerda con lo enviado.

### **ChangeCipherSpec**

lo mismo

### **Finished**

ídem pero cambiar respectivamente cliente por server, y viceversa.

### **Application Data (ida y vuelta)**

TLS 1.3 Handshake hace todo en menos pasos (3 en vez de 5) y realiza una negociación más rápida y segura.

## Ataques

### Suplantación

En el paso de pedir la clave pública de un usuario legítimo, se da otra clave pública diferente. De ahí la necesidad de usar los PKI, para comprobar la legitimidad de estas claves públicas...

<figure><img src="../../.gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

### Man in the Middle

Me cuelo en medio para ir descifrando lo que va para la víctima, y lo voy cifrando en su nombre.

### Downgrade

Engañar al cliente o el servidor para bajar las características de seguridad, es decir, liar al CipherSuite. Por ejemplo, pasar de HTTPS a HTTP, bajar TLS/SSL. Prevención: HSTS, donde el navegador recuerda el protocolo al que te conectaste por primera vez al server.

### Beast

Afecta a SSL 3.0 y TLS 1.0, vulnerabilidad que inyecta paquetes y averigua el IV y por ende descifra los paquetes, causada por una vulnerabilidad de diseño de CBC. Se propuso RC4 para solucionarlo, pero después se vio que seguía habiendo vulnerabilidades y se hizo revert.

### Crime

Ir averiguando los valores que había en la cadena por la compresión TLS. Actualizas y ya

### BREACH

Lo mismo, pero por medio de la compresión de HTTP. Solución: deshabilitar compresión HTTP, no poner claves en user input, proteger contra forgeries.

### POODLE

Descifra un mensaje con un downgrade para hacer que la comunicación fuese por SSL 3.0 y atacase al diseño del padding de CBC. Para prevenir, deshabilitar SSL 3.0 y actualizar.

### Truncamiento

Finalizar la negociación SSL/TLS. El atacante intercepta la conexión, enviando un TCP FIN no cifrado a la víctima, haciendo creer que ha cerrado la sesión, cuando en realidad el atacante la conserva. Se resuelve enviando el registro ClosureAlert por ambas partes, para verificar un cierre correcto.

### HeartBleed

Atacaba a OpenSSL, que lo usaba todo el mundo xD. Se podían obtener datos de la memoria del servidor por medio de una fuga de datos cuando el cliente decía la longitud del mensaje y filtraba la clave privada.

## VPN

Crear una red privada. Es algo costoso, si hubiera que hacerlo desde cero. Lo que se hace es crear un túnel entre router central y sucursal donde cifro la comunicación que vaya de un sitio a otro. Lo que hace es _asegurar la comunicación de un punto a otro_. No es lo mismo que un proxy, que es un repetidor/intermediario que hace las comunicaciones por mí. El TunnelBear hace ambas cosas al final, me garantiza túnel seguro entre un sitio y otro

### Tipos de VPN:

### Acceso Remoto

Para acceder a la red corporativa

### Intranet

Para ir de forma segura entre diferentes partes de la red de la empresa

### Extranet

Para dar acceso seguro a terceros.

### Con IPSEC

Comunica los datos entre extremos en la capa de red sin estar asociado a una aplicación en concreto, necesita normalmente software especializado en los equipos y la negociación de los parámetros de la seguridad es compleja.

### Con SSL/TLS

Va en capa de aplicación, comunica con seguridad los datos enviados por la web, es más flexible y no requiere software específico. Tiene control de acceso más detallado, y es más simple, al permitir su paso por nodos intermedios.

## IPSEC

Protocolo complejo, más bien un conjunto, implementables y usables en IPv4 (optativo) e IPv6 (soporte nativo, pero no habilitado), permite cifrar e identificar a nivel de red. Lo hace transparente a los usuarios, todo va cifrado por el camino (entre máquina cliente y el proveedor).

Permite tener:

### Autenticación mutua de ambos equipos

### Cifrado de datos con protocolos simétricos estándar (AES, DES, 3DES)

### Establece una asociación de seguridad:

Conjunto de algoritmos y parámetros que se están usando para la comunicación, hace falta una por cada sentido.

### Directivas

Permiten configurar toda la utilización de IPSec mediante reglas que dictan cómo (SAD), cuándo, a qué tráfico y qué tipo de cifrado (SPD) van a ser utilizados.

IPSec da CIA y prevención de ataques por reproducción (por los nonce). Hay dos protocolos: AH (Authentication Header, integridad de los datos y autenticación de origen) y ESP (Encapsulation Security Protocol, da CIA); y directivas de seguridad (conjunto de reglas).

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

## Modos de IPSec:

### Túnel

Cada vez que se haga side to side, conecto red entre central y sucursal, se encapsula. El cifrado se hace en el router y lo encapsula.

### Transporte

De extremo a extremo (puerta a puerta), no hace falta encapsular uno dentro de otro. Creas el paquete directamente poniendo la cabecera de los equipos, y lo cifras. El cifrado viene del equipo origen.

<figure><img src="../../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

Hace falta crear un par de asociaciones de seguridad (SAs, comunicación virtual simple que especifica los parámetros con los que cifro la comunicación) que tienen unos valores: índice de 32-bits, interfaces, origen y destino, y especifica cómo va a hacerse el túnel (cifrado, protocolo, clave de cifrado de autenticación). Se hace de forma simétrica. Se almacena en una base de datos SAD (Security Association Database, dicen el cómo) y en una SPD (Security Protocol Database, que almacena qué tráfico va cifrado por el túnel). Deben guardar estado para saber cuáles están activo y cuáles no. Un router tiene una única SAD, y otra SPD.

## Pasos de datagrama IPSec:

1. Cola ESP: relleno para el cifrado de bloque, y decir qué cabecera sigue. Se cifra según lo establecido en la SA.
2. Cabecera ESP: no va cifrada, digo el SPI, Service Provider Index (para indexar en la tabla y encontrar la SA a la que se pertenece). El receptor mira a qué SA se corresponde y así con ello hacer el descifrado. Tiene tb un número de secuencia que previene ataques por reproducción.
3. Cola MAC: lleva un hash de mensaje + clave secreta, obtengo integridad para ver si alguien lo ha modificado.
4. Nueva cabecera IP: origen y destino del túnel

Números de secuencia en IPSec: se incrementan cada vez que se envía un datagrama.

IPSec nos previene muchísimo de MITM, gracias a que las IP origen y destino van cifradas, así como todo el protocolo, y con todo el tema de integridad, no reproducción, etc.

Un hash NO TIENE CLAVE. Cuando pone clave, se refiere al hash con el que se hace la comprobación de integridad.

IKE (Internet Key Exchange): automatiza intercambio de clave en 2 fases sobre UDP:

* Establecer un canal seguro bidireccional ISAKMP, diferente del SA IPSec. Clave compartida en una misma política (CPT)
* Se emplea el canal seguro ISAKMP para negociar el túnel de verdad que va a ser el SA IPSec (uso del set para establecer el mapa donde se indican los peers)

Fase 1: para crear el canal seguro

1. Se eligen métodos a utilizar, como el cifrado, hash, método de autenticación (clave compartida o clave pública + certificados).
2. Intercambio de valores por Diffie-Hellman + nonces (esto es lo que garantiza la seguridad de la comunicación por este túnel)
3. Autenticación de nodos
4. Modo:
   1. Principal: da protección de identidad, oculta identidad de los nodos, todo en 6 mensajes
   2. Agresivo: 3 mensajes, con identidad compartida, sin cifrar.

Fase 2: para negociar parámetros de SA IPSec

1. Se establece la SA: protocolos, modo (transporte o túnel), cifrado e integridad, y otros parámetros como SPI, tiempo de vida
2. Se hace de forma segura gracias al ISAKMP creado en la fase 1

PFS: Perfect Forward Secrecy, que aún si me pillan la clave no me descubran el mensaje.
