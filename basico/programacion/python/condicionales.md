# Condicionales

Sabiendo lo anteriormente comentado en está página, aplicar los condicionales en este lenguaje es muy simple.

En python solo existe el condicional if, con sus respectivos elif (equivalente a else if en otros lenguajes), y else.

## Condiciones booleanas

Existen numerosos tipos de condiciones booleanas, aquí explicaremos solamente las principales ya que python, como casi cualquier lenguaje de programación, es un mundo a la hora de flexibilidad en el código.

Las mas importantes son '==' o '!=', que se traducen como 'igual que' o 'distinto que' respectivamente. Así pues, si queremos comprobar si una variable es igual a 0, podriamos usar la siguiente sentencia:

```
if number == 0:
    print("The number is, indeed, 0)
```

Otro uso de las condiciones booleanas es el 'in' o el 'not in', que comprueba de manera automática si la variable introducida forma parte del conjunto iterable (como una lista o un conjunto) especificado a continuación. Esto se verá ejemplificado en el siguiente apartado del documento

## Sintaxis de un condicional

De este modo, para crear un condicional simplemente escribiremos if, seguido de la condición (que devuelva un valor booleano) sin paréntesis, y dos puntos para declarar el comienzo del bloque. A partir de ahí escribiremos el contenido que querremos que se ejecute si la condición booleana introducida es True.

<figure><img src="../../../.gitbook/assets/image (5) (1).png" alt=""><figcaption><p>Ejemplo de función if</p></figcaption></figure>

Como podemos ver, la comprobación que se lleva a cabo en el anterior ejemplo es que la variable no esté incluida en la variable visited (de tipo lista, conjunto, etc...).

¿Pero qué pasa si queremos realizar varias comprobaciones, o realizar alguna acción si la comprobación no resulta verdadera? Ahí es donde entra el 'else' y el 'elif'.

A parte del if, podemos colocar 'else' a la misma altura que el if al que pertenece para dar comienzo al bloque de código que se ejecutará en caso de que la condición o condiciones anteriores no se cumplan.

'else if' hace lo mismo pero llevando a cabo una nueva comprobación booleana antes de entrar a su bloque de código. Un ejemplo en el que ambos elementos se ven aplicados es el siguente:

<figure><img src="../../../.gitbook/assets/image (1) (2) (1).png" alt=""><figcaption></figcaption></figure>

La ejecución de los condicionales va en orden, es decir, primero se ejecuta el 'if', luego el 'elif' y por último el 'else'. La peculiaridad de esto es que si cualquiera de estas condiciones resulta ser verdadera el resto no se ejecutará, ya que al acabar el bloque de código de la sección verdadera se saltará al final del condicional.
