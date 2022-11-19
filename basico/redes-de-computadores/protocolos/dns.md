# DNS

El protocolo DNS es uno de los más importantes en lo que se refiere a navegación por Internet y en nuestro día a día.

## Función principal

DNS (Domain Name System o Sistema de Nombres de Dominio), es un protocolo que traduce las direcciones IP de los servidores que están ejecutando las páginas de Internet que intentamos visitar a los nombres de dominio que vemos comúnmente como www.google.com.

Esto es así porque el enrutamiento que tiene lugar para encontrar el camino hasta el servidor no se podría llevar cabo si su "dirección" no fueran números, así es la informática.

Es por esto que existen los servidores de DNS, que mantienen información acerca de las equivalencias entre las direcciones IP de los servidores y los dominios de las páginas que los representan.

## Sistema de DNS

Para llevar a cabo todo este proceso, existe una serie de servidores de DNS con diferentes nombres y jerarquías que se complementan para así poder devolver la información necesaria. Sin embargo, nos vamos a indagar tanto en este blog ya que nos encontramos en la rama básica de las redes de computadores, pero si os interesa [aquí](https://www.cloudflare.com/es-es/learning/dns/what-is-dns/) podéis encontrar una gran explicación a fondo.

Básicamente, cada uno de los servidores de esta jerarquía está encargado de un grupo cada vez más pequeño de dominios, y se va haciendo una consulta recursiva hacia los servidores más pequeños de la jerarquía hasta que encontramos la equivalencia entre dominio e IP deseada.

<figure><img src="../../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

En ocasiones, no es necesario llevar a cabo toda esta serie de pasos, ya que los servidores DNS tienen buffers en los que almacenan las direcciones más requeridas, de manera que si una petición por parte de un cliente se encuentra en el buffer no es necesario preguntar a los servidores más altos de la jerarquía, si no que se devolverá la equivalencia instantáneamente, ahorrando una gran cantidad de tiempo.
