---
description: >-
  Aquí podéis encontrar varios ejercicios resueltos para que practiquéis los
  conceptos vistos.
---

# Ejercicios

### Ejercicio 1 \~ Amor a los números

### Enunciado:

Nuestro amigo Juan Caminante está buscando pareja y eso se une a su amor por el análisis de datos. En concreto, para que Juan muestre algo de interés en conocer a una persona se deben dar varias condiciones:

1. Su estatura debe de ser entre 1,70 y 1,83 m.
2. Debe pesar menos de 90 Kg.

Deberás desarrollar un programa que ayude a Juan a saber si debe conocer a una persona o no, en base a su altura y peso. En concreto, el programa imprimirá un 1 cuando sí deba conocer a la persona, y 0 si no cumple alguno de los requisitos.

### Entrada:

La entrada de este ejercicio será un número decimal e y un número entero p (cada uno en una línea), donde e es la estatura de la persona candidata, y p es el peso.

### Salida:

Se deberá imprimir un único número que represente si Juan debe conocer a la persona o no. En caso de que sí deban conocerse (porque cumple todas las condiciones) el programa imprimirá un 1; e imprimirá 0 en caso contrario.

| Ejemplo de entrada   | Ejemplo de salida |
| -------------------- | ----------------- |
| <p>1,80</p><p>94</p> | 0                 |
| <p>1,75</p><p>85</p> | 1                 |

### Solución:

```c
#include <stdio.h>

int main() {

    char letra;
    int pos;
    int letranumerica;
    int limite = 'z';
    scanf("%d",&pos);
    scanf("%c", &letra);


    letranumerica = letra;
    letranumerica = letranumerica + pos;

    if (letranumerica > limite){
        letranumerica = letranumerica-26;
    }

    letra = letranumerica;

    printf("%c", letra);


    return 0;
}

```

### Ejercicio 2 \~ Chollometro

### Enunciado:

Con el precio que tiene la vida actualmente, todos buscamos ahorrarnos un dinero a la hora de comprar artículos por la red. Una de las aplicaciones más utilizadas para lograr este objetivo es Chollometro, que nos avisa de todas las ofertas que se pueden encontrar en cierto momento en Internet. El problema es que, normalmente, los cupones de descuento que nos ofrecen tienen un número de usos limitados.

Por ello, nos han pedido que desarrollemos un contador de veces que se ha utilizado un cupón, para así saber cuál debemos darnos prisa en utilizar si queremos aprovecharlo.

### Entrada:

La entrada serán seis enteros N que representan el número de veces que se ha usado un cupón

### Salida:

Por cada cupón se imprimirá el identificador del cupón (un número donde el primer cupón es el 1 y el último el 6), un espacio en blanco, y un número de caracteres ‘=’ igual al número de veces que se ha utilizado. En la última línea se imprimirá la cadena “El mas usado es el cupon M con P usos” donde M es el identificador del cupón con más votos y P el número de usos.

| Ejemplo de entrada | Ejemplo de salida                                                                                                                                                              |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 7 9 13 18 10 12    | <p>1 ======= </p><p>2 ========= </p><p>3 ============= </p><p>4 ================== </p><p>5 ========== </p><p>6 ============ </p><p>El mas usado es el cupon 4 con 18 usos</p> |

### Solucion

```c
#include <stdio.h>
#define N 7

int main(){
    int usos[N],mayor=-2;
    for (int i = 1; i < N; ++i) {
        scanf("%d",&usos[i]);
        if (usos[i] > usos[mayor]){
            mayor=i;
        }
    }

    for (int i = 1; i < N; ++i) {
        printf("%d ",i);
        for (int j = 0; j < usos[i]; ++j) {
            printf("=");
        }
        printf("\n");
    }
    printf("El mas usado es el cupon %d con %d usos", mayor, usos[mayor]);

    return 0;
}
```

### Ejercicio 3 \~ Cerveza

### Enunciado:

La aparición de las cervezas artesanales ha hecho que todo el mundo se vuelva loco comparando la calidad de las cervezas. Uno de los ı́ndices más utilizados para medir el amargor es el Inter- national Bittering Unit (IBU). Mucha gente asocia un alto amargor a una buena calidad, ası́ que nos han pedido que hagamos un programa que evalúe la calidad de una cerveza en función de sus IBUs. En concreto, se tiene en cuenta la siguiente escala:

| Escala                  |
| ----------------------- |
| Más de 46: MUY BUENA    |
| Entre 36 y 46: BUENA    |
| Entre 21 y 35: REGULAR  |
| Entre 11 y 20: MALA     |
| Entre 0 y 10: CRUZCAMPO |

Se pide desarollar un programa que imprima por pantalla la calidad de la cerveza en función de sus IBUs.

### Entrada

La entrada consistirá en un número entero n que representa los IBUs de la cerveza.

### Salida:

Se deberá imprimir por consola la calidad de la cerveza.

| Ejemplo de entrada | Ejemplo de salida |
| ------------------ | ----------------- |
| 41                 | BUENA             |

### Solucion:

```c
#include <stdio.h>

int main() {
    
    int n;
    scanf("%d", &n);

    if (n>46){
        printf("MUY BUENA");
    } else if (n>=36 && n<=46){
        printf("BUENA");
    } else if (n>=21 && n<=35){
        printf("REGULAR");
    } else if (n>=11 && n<=20){
        printf("MALA");
    } else{
        printf("CRUZCAMPO");
    }
    
    
    
    return 0;
}

```
