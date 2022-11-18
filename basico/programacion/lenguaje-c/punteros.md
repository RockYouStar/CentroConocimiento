# Punteros

Los punteros en c son una de las características más útiles de este lenguaje, aunque a la vez se podría decir que es la más complicada de utilizar.

Un puntero es una variable que apunta a la dirección de memoria de otra variable

<figure><img src="../../../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>Representación de estructura de memoria del ejemplo</p></figcaption></figure>

Como podemos ver en la imagen anterior, la variable situada en la dirección 200 (el recuadro amarillo) guarda la dirección de memoria de la variable n1 (en la dirección 100).

¿Cómo podemos manejar este tipo de variables?

&#x20;

### Declaración de punteros

`[tipo] *[nombre]`

Esto creará una variable de tipo puntero al tipo de dato especificado (este tipo de dato será el que está presente en la dirección de memoria del puntero) con el nombre especificado.

Un ejemplo podría ser

`Int *p1;`

Que crearía un puntero a entero llamado p1

&#x20;

### Asignación de punteros

```c
int x;
int y;
int *p1=&x;    //Asignamos a p1 la dirección en memoria de la variable x
int *p2;       //Inicializamos el puntero p2
p2=&y;         //Asignamos a p2 la dirección en memoria de la variable y
```

Aquí hemos usado el carácter reservado ‘&’, que lo que hace es devolver la dirección de memoria de la variable que le situemos a continuación.

Para conseguir que la dirección de memoria del puntero apunte a otra dirección de memoria diferente haremos esto:

```c
int *p1=&x;
p1=p1+1;
```

Lo que esto hará será que el puntero p1 apunte un entero (4 bytes) más allá de la dirección de memoria establecida para la variable x. Esto es especialmente útil con arrays de datos, que veremos más adelante.

&#x20;

### Acceso al valor del puntero

Sin embargo, en ocasiones no queremos acceder a la dirección de memoria que guarda el puntero, si no al valor guardado en esa dirección, pero siempre a través del puntero.

Para hacer esto haremos lo siguiente:

```c
int x;
int *p1=&x;
*p1=30;               
//Aquí meteremos el valor 30 en la dirección de memoria a la que apunta p1

printf("%d", *p1);    
printf("%d", x)       
//Esto imprime el valor dentro de la dirección, que en este caso es 30,
//es decir, lo mismo en ambos casos
```

### Variables por valor y por referencia en las funciones

Cuando le pasamos una variable a una función de manera normal, es decir, sin hacer uso de los punteros, lo que estamos haciendo es pasarle una copia del valor de esa variable, que se puede utilizar dentro de la función para lo que sea pero que no actualizará el valor de la variable fuera de la función, ya que es una copia.

De este modo, si queremos pasar una variable para modificarla dentro de la función, la pasaremos por referencia de la siguiente manera:

```c
int x;
sumar(&x);             //Le pasa la direccion de memoria con ‘&’
 
void sumar(int *x){    //Recoge la dirección de memoria con un puntero
      *x+=1;           //Modifica el valor de la dirección de memoria del puntero
}
```

Lo que conseguimos de este modo es que se modifique la dirección de memoria de la variable original, y no la copia que hemos creado solamente la ejecución de esa función como pasaría si no hubiéramos usado punteros.

&#x20;

### Arrays como punteros

Los arrays son punteros y los punteros son arrays, pero expresados de manera diferente.

Al fin y al cabo, un array es una serie de espacios en memoria que pueden guardar tantos valores del tipo de dato especificado como huecos haya. Puesto que esto se guarda consecutivamente, podemos hacer uso de los punteros y de su capacidad para apuntar a direcciones de memoria contiguas para acceder a los diferentes valores de un array.

<figure><img src="../../../.gitbook/assets/image (8) (1).png" alt=""><figcaption><p>Representación de estructura de memoria de un vector de 4 posiciones</p></figcaption></figure>

Cuando declaramos un array, lo que realmente declaramos aunque no lo sepamos es un puntero a la primera posición de este. Es por esto que, para acceder a la segunda posición, tendríamos que acceder a la primera +1 (4 bytes por encima de la primera).

```c
v[0]=*v;
v[1]=*(v+1);
v[2]=*(v+2);
```

Todo eso son sentencias equivalentes, aunque comúnmente por comodidad se pone de la forma de los corchetes.

Esto mismo pasa con las Strings, ya que en C no existe el tipo de dato String como tal, si no que usamos un puntero a la primera posición de un vector de chars como variable String. De este modo, para acceder a la segunda posición de la String, lo que haríamos seria \*(string+1).

&#x20;

### Acceso a campos de una variable

En ocasiones nos referimos a una variable de tipo struct con un puntero (cuando la pasamos por referencia a una función para poder modificarla, por ejemplo). Para acceder a los campos de esta struct a través de un puntero, podemos hacerlo de una manera especial:

```c
typedef struct alumno{                //Declaramos la struct
                Char *nombre;
                Int edad;
                Char *DNI;
}
Alumno a1;
Alumno *a=&a1;         //Declaramos un puntero a un tipo de dato de la struct
*(a).edad = 21;
a->edad=21;
```

Las dos últimas sentencias hacen exactamente lo mismo, es decir, recogen el valor del struct almacenado en la dirección de memoria concreta y acceden a un campo en concreto, en este caso la edad, pudiendo modificarlo a través del puntero.

La segunda sentencia es una manera más bonita y rápida de hacer lo mismo que en la primera, pero se puede usar cualquiera de las dos perfectamente.
