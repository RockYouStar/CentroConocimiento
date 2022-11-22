# Condicionales

### Introducción

Este tipo de sentencia permite modificar el flujo del programa en función de ciertas condiciones.

Encontramos varias estructuras:

### IF

<pre class="language-java"><code class="lang-java">if (&#x3C;condición>){ // expresión booleana

<strong>    (sentencia);
</strong><strong>    
</strong>}</code></pre>

La sentencia se ejecuta sólo si se cumple la condición. En caso de no cumplirse, el programa continúa sin ejecutar la sentencia.

### IF ELSE

```java
if (<condición>){ // expresión booleana

	(sentencia1);
}else{

	(sentencia2);
}
```

Si la condición se satisface, se ejecutará la sentencia1, en caso de no hacerlo, se ejecutará la sentencia2. En cualquier caso, el programa continuará a partir de la sentencia2.

### ELSE IF

```java
if (<condición>) {
(sentencia);
} else if (<condición>) {
(sentencia);
} else {
(sentencia);
}
```

Con este formato, el programa sólo entra en una de las condiciones. Si se cumple una de ellas, se ejecuta la sentencia correspondiente y se salta al final de la estructura para continuar el programa.

Ejemplo:&#x20;

```java
 public static void main(String args[]) {
   int a = 1; //cualquier numero
   int b = 15 //cualquier numero
   
    if(a>b) {
      System.out.print("a es mayor que b");
    } else if(a<b) {
      System.out.print("a es menor que b");
    } else {
      System.out.print("a y b son iguales");
    }
  }
```

### SWITCH

Esta estructura se suele utilizar en los menús, de manera que, en base a la opción seleccionada, se ejecutan una serie de sentencias.

```java
switch (variable){
		case caso1:
			sentencia;
			break;
		case case2:
			sentencia;
			break;
		default:
			sentencia;
	}
```

Cada caso podrá incluir una o varias sentencias sin necesidad de ir entre llaves, ya que se ejecutarán todas hasta encontrar la sentencia BREAK. La variable que se evalúa sólo puede ser de tipo entero o carácter. Por defecto, se ejecutarán las sentencias que incluye tras default:

Ejemplo:

```java
switch (nota) {

        case 0:
        case 1:
        case 2:
        case 3:
        case 4: resultado = "Suspenso"; 
                break;
        case 5:
        case 6: resultado = "Aprobado"; 
                break;
        case 7:
        case 8: resultado = "Notable"; 
                break;
        case 9:
        case 10: resultado = "Sobresaliente";
                break;
        default: resultado = "Fuera de rango";
}
```
