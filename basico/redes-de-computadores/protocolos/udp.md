# UDP

UDP es otro de los protocolos de Internet más usados en la actualidad, y esto se debe a su gran rapidez a la hora de transmitir datos.

## Características

Lo más importante a comentar acerca de este protocolo es que, a diferencia de TCP, no necesita ni el establecimiento de una conexión previa para poder llevar a cabo la comunicación, ni la comprobación de que todos los paquetes van llegando. Pero esto tiene un precio, y es que no asegura que todos los paquetes enviados vayan a llegar a su destino, ya que no hay manera alguna de que el emisor compruebe qué paquetes le han llegado a receptor para enviar los perdidos de nuevo.

Es precisamente por eso que el protocolo tiene unos usos muy concretos en los que se prioriza la velocidad a la "calidad". Por ejemplo, la transmisión de datos en videojuegos o el envío de videos en directo (streaming) son servicios en los que no pasa nada por que un paquete concretamente no llegue (se puede "rodear"). Sin embargo, si este envío fuera lento sería catastrófico para la calidad de la experiencia del cliente.

<figure><img src="../../../.gitbook/assets/image (1) (3).png" alt=""><figcaption><p>Comparación entre TCP y UDP</p></figcaption></figure>
