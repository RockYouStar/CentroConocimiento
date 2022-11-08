# Protección del perímetro: Firewalls y DMZs

Nodos bastión: hay que protegerlos mucho. Cerrar puertos innecesarios, sistemas de logs. Son los que están en el perímetro. Al estar tan expuestos tienen que estar especialmente protegidos:

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption><p>El torreón es la torre bastión</p></figcaption></figure>

ACL: Lista de reglas que definen que tráfico vamos a permitir y cual vamos a denegar. Es una lista de reglas ordenada. Cada una de las reglas van a filtrar que paquetes van a pasar . Se aplican en un router o firewall.

Reglas según:

• Puerto origen-destino&#x20;

• IP origen&#x20;

• Protocolo&#x20;

ACLs usan máscaras wildcard (comodín) igual que la máscara de red normal, pero al revés (0 en vez de 255 y viceversa). Se comprueba el tráfico regla a regla. Importante, está ordenada. Si ponemos una regla más específica debajo de otra más genérica, se cumple la genérica y nunca se va a cumplir la especifica.

### Defensa en Profundidad

Tenemos que defender tanto amenazas externas como internas, que no salga o entre información que nos perjudique. El perímetro hoy en día es muy difuso, pero pondremos que tenemos un nodo de entrada/salida: un único acceso a proteger (router frontera) -

> nodo bastión: son nodos o equipos que debemos tener bien protegidos (cerrados los puertos no usados, sistema de control de acceso, parchearlos...).

### Listas de control de Acceso (ACLs)

Una ACL es una lista de reglas que definen que tráfico permitimos o denegamos. Cada una de esas reglas (ACE) filtran qué paquetes van a atravesar ese dispositivo de red siguiendo unos criterios (aplicadas a un firewall o a un router). Con estas reglas diremos qué ips o puertos permito o deniego. Estas listas están ordenadas: tiene una importancia el orden; vas comprobando regla a regla hasta que te salgas de la lista (ejecutas la acción que sea y se sale; esta la cumple? No-> siguiente...). Es muy importante el orden: si pones una regla específica después de una general, no va a pasar por esa regla. Al final de la lista, como no ha cumplido ninguna de las reglas, vas a denegar o permitir en función de la política que sigas: denegar todo y permitir lo necesario (denegación por defecto: la más usada), o permitirlo todo y ver si luego cumple. Una buena política a la hora de configurar las ACL, es comentar el por qué se pone esa regla.

Diferencia entre ACL estándar y extensas: las estándar sólo pueden especificar el origen, las extendidas pueden especificar origen y destino; esto nos obliga a poner los bloqueos lo más cerca del origen posible (en las estándares).

AntiSpoofing con ACLs, firewalls con ACL (bloqueando diferentes tipos de tráfico), impidiendo abuso de ICMP con ACLs...

### Tecnologias de Firewall

Puede ser hardware o software. Filtra el tráfico, analizándolo y dejándolo pasar en función de ciertos criterios establecidos. Los firewalls hardware son más potentes.&#x20;

## Tipos de Firewall: (de menos a más seguros)

### Filtrado de paquetes&#x20;

Es el más sencillo. Se fija en las cabeceras, sobre todo en las de transporte y de red. Son sencillos y fáciles de usar, causan poco impacto en la red y son muy compatibles, lo malo es que no se fija en los datos, y pueden colar malware con ello, por ejemplo.

### Stateful Firewall (SPI)

Voy a saber si había una conexión establecida (el estado de la conexión vaya) y guardará ese valor en una tabla. Ejemplo diapositiva: permite una vez que se hayan enviado datos.

### DPI (Deep Packet Inspection Firewall)

Estos miran ya el contenido del paquete, además de las cabeceras y demás que incluían los anteriores. En el ejemplo de la diapositiva (27) se complementan los DPI con las ACL (chequean si pueden llegar los paquetes en función de ciertos criterios y luego pasan esos paquetes por el DPI).

### Next-Generation Firewalls (NGF)

Hacen muchas más cosas a parte de filtrar paquetes
