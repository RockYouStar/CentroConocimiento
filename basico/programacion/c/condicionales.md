# Condicionales

### Introduccin

Este tipo de sentencia permite modificar el flujo del programa en función de ciertas condiciones.

Encontramos varias estructuras:

### IF

```c
if (condición){

sentencia;

}
```

La sentencia se ejecuta sólo si se cumple la condición. En caso de no cumplirse, el programa continúa sin ejecutar la sentencia.

### IF ELSE

```c
if (condición){
	sentencia1;
}else{
	sentencia2;
}
```

Si la condición se satisface, se ejecutará la sentencia1, en caso de no hacerlo, se ejecutará la sentencia2. En cualquier caso, el programa continuará a partir de la sentencia2.

### ELSE IF

```c
if (condición){
	sentencia1;
}else if (condición){
	sentencia2;
}else if (condición){
	sentencia3;
}else{
	sentencia4;
} 
```

Con este formato, el programa sólo entra en una de las condiciones. Si se cumple una de ellas, se ejecuta la sentencia correspondiente y se salta al final de la estructura para continuar el programa.

Ejemplo:

```c
#include <stdio.h>
int main(){
	int a,b;
	printf("Introduzca el primer numero: ");
	scanf("%i",&a);
	printf("Introduzca el segundo numero: ");
	scanf("%i",&b);

	if(a>b){
		printf("El mayor es el primer numero"); 
	}else if(a==b){ 
		printf("Los numero son iguales"); 
	}else{
		printf("El mayor es el segundo numero");
	}
	return 0;
}
```

### SWITCH

Esta estructura se suele utilizar en los menús, de manera que, en base a la opción seleccionada, se ejecutan una serie de sentencias.

```c
switch (variable){
		case caso1:
			sentencias;
			break;
		case case2:
			sentencias;
			break;
		default:
			sentencias;
	}
```

Cada caso podrá incluir una o varias sentencias sin necesidad de ir entre llaves, ya que se ejecutarán todas hasta encontrar la sentencia BREAK. La variable que se evalúa sólo puede ser de tipo entero o carácter. Por defecto, se ejecutarán las sentencias que incluye tras default:

Ejemplo:

```c
#include <stdio.h>

int main() {

	int dia;
	printf("Introduce el día: ");
	scanf("%i",&dia);
	switch(dia){
	case 1: printf("Lunes"); break;
	case 2: printf("Martes"); break;
	case 3: printf("Miércoles"); break;
	case 4: printf("Jueves"); break;
	case 5: printf("Viernes"); break;
	case 6: printf("Sábado"); break;
	case 7: printf("Domingo"); break;
	}
}
```
