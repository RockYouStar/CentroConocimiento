# Bucles

### Introducción

Existen varios tipos de bucles, cada uno de ellos con una serie de características que los diferencian entre sí. Sin embargo, todos ellos comparten el hecho de que repiten un fragmento de código y en cada una de las iteraciones se evalua una condición que permitira la salida o continuación del bucle.

### Bucle While

Este bucle repite su fragmento de código hasta que la condición evaluada deja de ser cierta. De este modo, la condición debe ser de tipo booleano.&#x20;

Su sintaxis es la siguiente:

`while (<condición) {`

`sentencia1;`

`sentencia2;`

`}`

Ejemplo:&#x20;

`int x=0 while(x<=100){`

`x++; //añade 1`

`}`



Bucle Do While

Muy similar al bucle While, con la diferencia de que evalua la condición al final ejecutandose como mínimo una vez.&#x20;

La sintaxis es la siguiente:

`do{`

`sentencia1;`

`sentencia2;`

&#x20;`} while(<condición>);`

Ejemplo:

`int x=-3;`

`do{`&#x20;

`x--;`

&#x20;`} while(x>0);`

Puesto que la variable x ya empieza teniendo un valor menor que 0 (condicion a evaluar), no debería ni siquiera entrar en el bucle, pero puesto que en la primera iteración no se ha evaluado la condición, entra una vez "gratis" al bucle y luego sale.





Bucle For

Este bucle es el más elaborado, ya que además de evaluar una condición como el resto de bucles, se encarga de la inicialización e incremento de una variable que normalmente será utilizada en la condición. Su sintaxis es la siguiente:

`for(<inicialización>;<condición>;<incremento>){`

`<sentencia1>`

`<sentencia2>`

&#x20;`}`

Ejemplo:

`int coches=0;`&#x20;

`for(int i=0;i<=10;i++){`&#x20;

`coches+=5;`&#x20;

`}`
