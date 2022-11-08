# Funciones

### Introducción

Una función en C es un bloque sobre el cual se ejecuta código. La función principal, indispensable en todo código, es el main(), pero también existe la posibilidad de elaborar nuestras propias funciones con el fin de dividir nuestro código en secciones, o en el caso de que repitamos código, hacer factor común y llamar a dicha función para que repita las sentencias.

### Declaración

Una función en C está compuesta por 4 elementos:

1. <mark style="color:blue;">Tipo de variable devuelta:</mark> int, char, void...
2. <mark style="color:purple;">El nombre de la función</mark>
3. <mark style="color:orange;">Argumentos, que opcionalmente se incluyen en los paréntesis</mark>
4. <mark style="color:yellow;">El cuerpo de la función con las instrucciones a ejecutar.</mark> Debe incluir un <mark style="color:green;">"return", que devolverá un valor</mark> en función del tipo especificado en la cabecera, En el caso de que la variable devuelta sea void, no es necesario incluirlo, pues no se devuelve nada.

Ejemplo:&#x20;

<mark style="color:blue;">`int`</mark><mark style="color:purple;">`suma`</mark>`(`<mark style="color:orange;">`int a, int b`</mark>`) {`\
&#x20; ```  `<mark style="color:yellow;">`int c;`</mark>\
&#x20;  <mark style="color:yellow;">`c = a + b;`</mark>\
&#x20; ```  `<mark style="color:green;">`return c;`</mark>\
`}`



### La función main()

La función sobre la cual se ejecuta todo programa, también cuenta con argumentos que se pueden usar durante la ejecución (si se escriben en los paréntesis de la cabecera):

* `int argc`: contiene el úmero de argumentos en la línea de órdenes que recibe el programa en su llamada.
* `char *argv[]`: contiene punteros (ver [punteros.md](punteros.md "mention") para más información) a cada uno de los argumentos de la línea de órdenes.
* `char *env[]`: contiene punteros a cada variable de entorno del sistema operativo.&#x20;

### Paso por valor y por referencia

Por defecto, los argumentos que se pasan a las funciones en C son por valor (también llamado por copia). Esto significa que en el ejemplo anterior de la [suma](funciones.md#declaracion), los enteros "a" y "b" que recibe la función son copias de los valores que tendrían las variables en su momento. Es decir, que si paso las variables `intA=7` y `intB=5`, la función `suma(intA, intB)` recibe directamente el 7 y el 5, lo que implica que cualquier modificación que sufran esas variables dentro de la función no afecta a las originales.

Sin embargo, en el caso de que queramos modificar las variables y que el cambio trascienda al ámbito de la función, se debe hacer el paso por referencia, y en su lugar, pasar los punteros de las variables que correspondan (también la cabecera debe adecuarse, como se verá a continuación). De esta forma, pongamos un `main()` así:

`int main() {`\
&#x20;  `int a = 3;`\
&#x20;  `incremento (&a);`\
&#x20;  `printf("%d", a);`\
`}`

Y la función `incremento()` es la siguiente:

`void incremento(int* entero) {`\
&#x20;  `*entero += 1;`\
`}`

La sentencia de imprimir da como resultado un 4, pues el incremento se ha realizado pasando un puntero a la función, y modificando el contenido referenciado. Observa que la cabecera recibe datos de tipo `int*`, por lo que debe recibir punteros a enteros. Además, es una función tipo void, de ahí que no sea necesario el return.
