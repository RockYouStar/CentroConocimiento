# Bucles

En lo que a bucles se refiere, Java es un lenguaje enormemente similar a C, de modo que todos los bucles se usan de la misma manera. Por eso, para información básica de bucles en Java mire el apartado de [bucles en C](../lenguaje-c/bucles.md)

## Bucle for mejorado

Sin embargo, existe un tipo de bucle digno de mejorar, que nos ayudará a agilizar ciertos procesos en algunas ocasiones. Se trata del bucle for mejorado, o for-Each, que nos permitirá recorrer una colección iterable (como una lista o una pila) elemento a elemento sin necesidad de usar índices como realmente veníamos haciendo hasta ahora.

<figure><img src="../../../.gitbook/assets/image (1) (1) (3).png" alt=""><figcaption></figcaption></figure>

Su sintaxis es esta, donde Type el el tipo de variable o elemento que contiene la lista (int si es de enteros, por ejemplo), item es el nombre que tendrá la variable donde se guardará el elemento de la lista de cada una de las iteraciones, e iterableCollection es la variable que guarda esta lista a recorrer.

A través del usuario de esta funcionalidad evitamos tener que acceder por cada uno de los elementos a través de los '\[]', agilizando así el proceso de programación.
