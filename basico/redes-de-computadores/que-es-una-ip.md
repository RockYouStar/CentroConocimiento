# ¿Qué es una IP?

Una dirección IP (Internet Protocol) es una etiqueta que se asigna a cada uno de los dispositivos que se conectan a la red (ya sea esta pública como Internet, o privada como la red del router de nuestra casa) para así poder ser identificados fácilmente.

Sin embargo, estas direcciones no solo sirven como una identificación, si no que también funcionan como una serie de reglas para poder llevar a cabo toda la comunicación entre dispositivos y procesos.&#x20;

Puesto que las direcciones IP son secuencias de caracteres, no son infinitas, y para nunca quedarnos sin una dirección que asignarle a un nuevo dispositivo que se incluye en la red, tenemos dos tipos de direcciones IP.

## Direcciones IPv4

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption><p>Diferentes partes de una dirección IPv4</p></figcaption></figure>

Como podemos ver en la imagen, la dirección IPv4 consiste en 4 números desde el 0 al 255 separados por puntos, como el ejemplo anterior que es la dirección '192.149.252.76'.

Desde el punto de vista informático y más profundo, podemos ver que cada uno de esos 4 números consiste en 8 bits (de ahí la capacidad de 0-255 de cada uno de los números), que conforman un byte.

Este tamaño se eligió así en un primer momento ya que otorga una gran cantidad de combinaciones diferentes (\~4.294 millones) y a su vez no conforma un gran espacio (solamente 4 bytes) para así no colapsar los sistemas que procesan estas direcciones.

Sin embargo, este rango de direcciones se acabó por completo en el 2011, año en el que se asignaron las últimas direcciones disponibles.

## Direcciones IPv6

Estas direcciones surgieron en 2012 para sustituir a las direcciones IPv4 que ya estaban acabadas para aquel entonces.

La aparición de estas direcciones cambio el protocolo de Internet por completo, teniendo que cambiar toda la estructura de procesamiento de la red para así poder llevar a cabo este cambio y ampliación de direcciones

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Formato de una dirección IPv6</p></figcaption></figure>

Como podemos ver, una dirección IPv6 está compuesta por 8 grupos de 4 dígitos hexadecimales. Cada uno de estos dígitos tiene una equivalencia en binario a 4 bits, por lo que la cantidad de bits de una dirección de este tipo es de 128.

Debido a esto, este tipo de direcciones otorgan un total de 340 sextillones de combinaciones nuevas para asignar a nuevos dispositivos, un número prácticamente incomprensible en cuanto a su magnitud.

Es precisamente por eso por lo que este formato de IP se mantendrá durante un muy largo período de tiempo
