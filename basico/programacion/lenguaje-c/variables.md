# Variables

### Introducción

En el lenguaje C, toda variable, debe ser declarada antes de poder ser usada. Para ello, es necesario especificar el tipo de dato que almacenará. Una variable no es más que un nombre simbólico que identifica una dirección de memoria.

Toda variable en C se declara de la siguiente forma: ;

Ejemplo:

Declaración una variable entera numero1 de tipo int:

`int numero1;`

Declaración una variable entera numero2 de tipo int:

`int numero2;`

En C existen cinco tipos de datos según puede verse en la siguiente tabla:

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

### Modificadores de tipo

Además, hay cuatro modificadores de tipo, que se aplican sobre los tipos de datos mencionados anteriormente. Los modificadores de tipo permiten cambiar el tamaño, etc., de los tipos de datos. Estos modificadores, que preceden sintácticamente a la declaración del tipo de datos, son:

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Por este motivo, podemos declarar variables como:

Declaración una variable uchar de tipo unsigned char:

`unsigned char uchar;`

Declaración una variable ldouble de tipo long double:

`long double ldouble;`

Declaración una variable shorti de tipo short int:

`short int shorti;`

## Definición de constantes en C

Una constante hace referencia a un valor que no puede modificarse

Se suelen definir utilizando la directiva `#define` del preprocesador de C

Ejemplos:

`#define PI 3.141592`

`#define YEAR 2022`

## Arrays

Un array es una estructura que permite almacenar varios elementos de un mismo tipo bajo la misma variable. La declaración de un array debe también indicar su tamaño, es decir, el número máximo de elementos que entran. El índice para acceder a cada elemento empieza en 0, incrementando sucesivamente hasta "tamaño - 1".

De esta forma el array:

`int array[10];`

Nos permite almacenar 10 enteros, pudiendo acceder desde la posición `int[0]` hasta `int[9]`.

