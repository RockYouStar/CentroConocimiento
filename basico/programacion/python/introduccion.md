# Introducción

Python es un lenguaje increíblemente potente, aunque cuenta con ciertas particularidades que son necesarias para empezar hacer uso de su potencial. En primer lugar, hay que mencionar que es un lenguaje interpretado, es decir, que no se compila antes de su ejecución (como en [c](../c/ "mention")) sino que se va traduciendo a código máquina según se va ejecutando. De esta forma, los errores te los indica en tiempo de ejecución en vez de en tiempo de compilación.

Otra de las grandes características con las que cuenta Python es su increíblemente débil tipado. Esto implica que las "variables" como tal pueden ser cualquier cosa, y no es necesario especificar si se trata de un número entero, de coma flotante, una cadena de caracteres o un diccionario (como se verá más tarde en [estructuras-de-datos.md](estructuras-de-datos.md "mention") de este lenguaje).

## Bloques de código

Además, el uso de llaves para abrir y cerrar funciones, bucles, y condicionales desaparece por completo, siendo sustituido por la tabulación, de modo que todas aquellas líneas de código que estén a la misma altura pertenecerán al mismo fragmento.

<figure><img src="../../../.gitbook/assets/image (3) (2).png" alt=""><figcaption><p>Código de ejemplo</p></figcaption></figure>

Como podemos ver en el código anterior, desde la línea 4 hasta la 7 podemos encontrar un bucle for, delimitado simplemente por la tabulación. Lo mismo pasa con el condicional if en el interior de este bucle.

El funcionamiento, de este modo, es que todo lo que este después de la delcaración del bloque (y de los dos puntos al final de esta) y esté tabulado más allá de la propia declaración, pertenecerá a este bloque.

Esto consigue que el lenguaje sea más rápido de programar, más visual y menos complejo a la hora de entender código.

## Declaración de funciones

Las funciones son fragmentos de código que se pueden llamar y ejecutar en cualquier punto del programa, y que pueden devolver un resultado para la operación deseada o llevar a cabo cualquier modificación.

Para crearlas usaremos la palabra reservada def, seguida del nombre que le queremos dar a la función y un enumerado de los parámetros que le queremos pasar a la función. Por último usaremos los dos puntos mencionados anteriormente para declarar un fragmento de código y escribiremos todo el contenido de la función de manera tabulada.

Por último, si queremos devolver un valor como resultado en vez de simplemente llevar a cabo una modificación de un dato, usaremos return al final de la función, seguido de la variable que queramos devolver.

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Función con nombre explore, y g como argumento</p></figcaption></figure>

## Peculiaridades del lenguaje

Como hemos podido comprobar a través de las anteriores capturas, algunos os habréis dado cuenta de que el fin de línea no se define con un ';', si no que no se define.

Esto es algo bastante útil, ya que normalmente los ';' nos traen muchos problemas, y puesto que cualquier programador cambia de línea cuando va a escribir la siguiente línea de código, estos puntos y comas no son necesarios y crean un código más fácil y visual.

Otra diferencia no muy extraña pero que nos ha parecido digna de mencionar es la función para imprimir por pantalla. Mientras que en el resto de lenguajes en su mayoria esta función tiene un nombre extraño o demasiado largo (como System.out.println()), en este maravilloso lenguaje esto es tan fácil como poner print().

