# Virtual Local Area Network (VLAN)

Es la segmentación de red, permite crear independencia entre las redes, evitar inundación ARP, y gestionar mejor los switches, ya que se pueden asignar las bocas a una VLAN determinada.

Cada VLAN tiene un dominio de difusión, una IP. Ahora un broadcast solamente se propagará por el dominio de la VLAN. Los host no saben que pertenecen a una VLAN, no conocen la existencia de la misma. Otra cosa es que lo sepa el usuario, pero el equipo como tal, no.

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

La pertenencia a una VLAN se dice en el SWITCH, NO EN EL EQUIPO. Se puede ver que la separación física no es un impedimento para pertenencia a una VLAN.

## Tipos de VLAN:

### VoIP

Para tráfico de voz, prioridad para bajar el ping a menos de 150ms

### Predeterminada

Todos los puertos del switch están por defecto en esta.

### Nativa

Para tráfico no etiquetad

### Administracion

Para las capacidades de admin del switch

Enlace troncal: enlace punto a punto que lleva datos de más de una VLAN. No está asociado a ninguna VLAN en concreto, y se usa IEEE802.1Q como protocolo de enlace para etiquetar tramas. El switch se encarga de comprobar estas etiquetas, y la quita una vez vaya al sitio correspondiente. Si no va etiquetado, será VLAN nativa (como pone ahí arriba).

VLAN nativa: tráfico de control, dado que no va etiquetado.

Un switch no puede enviar tráfico entre dos VLAN diferentes sin la ayuda de un router, encargado del enrutamiento, ya que no tiene esa limitación. Excepto los switches MLS (Multi- Level Switch), que sí que pueden al poder moverse en varios niveles. Ahora se crean subinterfaces lógicas en los routers, rollo interfaz g0/0.30 para la VLAN 30, y así se etiqueta mejor y no hacen falta reservar una interfaz por VLAN.

## Ataques

Si hay automatización, se puede atacar. Vienen a raíz de VTP y DTP:

### VTP (VLAN Trunk Protocol):

Permite manejar las VLAN en un switch por un admin. El server VTP distribuye y sincroniza la info en los enlaces por los switches en toda la red conmutada.

### DTP (Dynamic Trunk Protocol):

De Cisco, maneja la negociación de canales si el puerto del switch vecino está configurado con un modo de enlace que permita DTP.

Los ataques son:

### VLAN Hopping Attack

El atacante se aprovecha de DTP para hacer que su enlace al switch sea troncal. La contramedida es ponerlo todo a mano, para evitar automatismos.

### Double-tagging attack

Ppara enviar tráfico a una VLAN de la que no se tiene acceso. Se aprovecha del VLAN Hopping, etiqueta con la VLAN nativa y la víctima, usando un puerto que no tenga VLAN configurada, cambia la etiqueta a la VLAN víctima y redirige el tráfico. Como ponerle una “máscara” a la VLAN troncal, cuando en realidad la VLAN nativa es otra.

#### Prevencion

No poner la VLAN nativa a ningún puerto de acceso, no permitir el tráfico de la VLAN nativa por el enlace troncal (no recomendable), o forzar que todo el tráfico del enlace troncal lleve etiqueta, aunque sea de la nativa (la mejor solución). Vlan dot1q tag native en el conf t del switch, o switchport trunk native vlan tag en la interfaz g del switch.

### CAM Table Overflow

Abusa de una inundación hacia las tablas CAM, de modo que el switch no puede hacer distinciones de tráfico y logramos VLAN hopping saltándonos restricciones de VLAN.

#### Prevencion

Seguridad en puertos. Poner máximo número de direcciones MAC, función “sticky” para quedarse con la MAC dinámica de forma fija, un tiempo con “aging”...
