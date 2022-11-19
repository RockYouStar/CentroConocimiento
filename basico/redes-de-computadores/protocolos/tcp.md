# TCP

El protocolo TCP es un protocolo usado en redes de computadores (en Internet es muy usado), que permite el intercambio de información de manera que no se pierde ninguna parte de la información.

Esto se debe al método que usa para emplear la comunicación, que consiste en el envió de paquetes muy ligeros (muy poco impacto en el ancho de banda) que sirven para comunicarle al otro usuario o máquina que la información que ha enviado ha llegado correctamente. De ese modo, el emisor podrá enviar el siguiente paquete de información y así sucesivamente hasta que se complete la comunicación.

Además, estos paquetes, denominados ACK, usan un número de secuencia concreto para poder identificar cuál es el paquete concreto que ha llegado.

Es por esto que se trata de un protocolo muy seguro en lo que se refiere a la pérdida de datos, ya que asegura al 100% que toda la información va a llegar, pero precisamente por esto se convierte en un protocolo más lento que algunos otros como [UDP](udp.md).

## Apertura y cierre de una conexión TCP

Para poder empezar o acabar de comunicarnos mediante este protocolo necesitamos seguir una serie de pasos concretos para asegurar que todo ha ido bien, que al fin y al cabo es la característica principal de este protocolo.

Para el establecimiento de una conexión, el cliente enviará un paquete concreto llamado SYN al servidor, que le indicará que quiere establecer una conexión TCP con él. Si todo va bien y el servidor esta disponible, responderá con un paquete SYN+ACK, informando al cliente de que si que puede crear una conexión. Cuando el cliente reciba este segundo paquete, enviará un último paquete ACK y se habrá dado por establecida la conexión.

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

En cuanto al fin de la conexión, se llevará a cabo el shutdown, que tiene los siguientes pasos.&#x20;

Quien quiera cerrar la conexión enviará un paquete FIN, que será recibido por el otro intermediario, quién enviará un ACK para este paquete y otro paquete FIN al primer intermediario. Cuando este lo reciba, enviará un último ACK, que será recibido por el otro cliente y se habrá dado por finalizada la conexión.

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

## Ejemplo completo

Un ejemplo completo de una conexión TCP con intercambio de datos de principio a fin sería la siguiente, en la que se pueden apreciar las diferentes fases que hemos comentado a lo largo de todo el apartado.

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>
