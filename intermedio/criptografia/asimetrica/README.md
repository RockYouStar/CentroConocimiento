# Asimétrica

### Protocolo Diffie-Hellman

Es un protocolo de intercambio de claves para compartir información de manera segura.

Partimos de un escenario en el que 2 individuos, Alice y Bob, quieren compartir información de forma segura.

Para ello Alice genera un grupo cíclico G de orden q y su generador g, luego escoge "a" de manera aleatoria, calcula h = g^a y le envia G, q, g, h a Bob.

Bob elige b aleatoriamente, calcula j=g^b y se lo envía a Alice. Bob obtiene la clave kb = h^b y Alice la clave ka = j^a.

EL protocolo es correcto si ka= j^a=(g)^b\*a y kb= h^b=(g)^a\*b.

Este protocolo solo es seguro si el adversario es pasivo.

### Clave Pública

Se basa en 3 algoritmos, uno de generación (Gen), uno para cifrar (Enc) y el último que descrifra (Dec).

Gen genera un par clave pública/clave privada.

Enc cifra el mensaje y Dec lo descifra.

