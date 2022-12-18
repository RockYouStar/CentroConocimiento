---
description: >-
  Aquí podéis encontrar varios ejercicios resueltos para que practiquéis los
  conceptos vistos.
---

# Ejercicios

### Ejercicio 1 \~ Par o impar?

Hacer un programa que, dado un array de números los separe en números pares y números impares en 2 arrays distintos.

Los arrays de números han de tener el tamaño adecuado, no más.

### Entrada:

Se inicializa el array de números en el código, por lo tanto no hay entrada al uso.

### Salida:

Se imprimirán los dos arrays de pares e impares, asi como el array original.

### Ejemplo de salida:

<figure><img src="../../../.gitbook/assets/image (3) (1).png" alt=""><figcaption><p>Salida</p></figcaption></figure>

### Solución:

```java
public static void main(String[] args) {

			// se declara e inicializa el array de números enteros
            int[] numbers = { 3, 4, 6, 2, 5, 1, 0, 10, 11 };

            int evenNumbersCount = 0;
            int oddNumbersCount = 0;

            // Contar el número de pares e impares
            for (int i = 0; i < numbers.length; i++) {
                if (numbers[i] % 2 == 0) {
                    evenNumbersCount++;
                } else {
                    oddNumbersCount++;
                }
            }

            // Crear los nuevos arrays
            int[] evenNumbers = new int[evenNumbersCount];
            int[] oddNumbers = new int[oddNumbersCount];

            // Copiar los números al array correspondiente
            evenNumbersCount = 0;
            oddNumbersCount = 0;
            for (int i = 0; i < numbers.length; i++) {
                if (numbers[i] % 2 == 0) {
                    // Insertar en array de pares
                    evenNumbers[evenNumbersCount] = numbers[i];
                    evenNumbersCount++;
                } else { // Insertar en array de impares
                    oddNumbers[oddNumbersCount] = numbers[i];
                    oddNumbersCount++;
                }
            }

            System.out.println("Enteros");
            for (int i = 0; i < numbers.length; i++) {
                System.out.print(numbers[i] + " ");
            }
            System.out.println();

            System.out.println("Pares");
            for (int i = 0; i < evenNumbers.length; i++) {
                System.out.print(evenNumbers[i] + " ");
            }
            System.out.println();

            System.out.println("Impares");
            for (int i = 0; i < oddNumbers.length; i++) {
                System.out.print(oddNumbers[i] + " ");
            }
            System.out.println();

        }
```

### Ejercicio 2 \~ Buscar y Destruir: Zero Edition

Dado un array bidimensional de números enteros, eliminar aquellos elementos de cada fila iguales a cero, redimensionando las filas que se hayan modificado.

Además, una vez se hayan eliminado los ceros, hay que ordenar las filas de menor a mayor longitud.

Para ordenar los arrays por tamaño se puede usar el algoritmo de la burbuja:

Consiste en revisar cada elemento del array con el siguiente, intercambiándolos de posición si están en el orden equivocado.

### Entrada:

Se inicializa la tabla de números en el código, por lo tanto no hay entrada al uso.

### Salida:

Se imprimirán todas las filas ordenadas de mayor a menor longitud.

### Ejemplo de salida:

Teniendo la siguiente entrada:

```java
int[][] tabla = { { 7, 0, 2, 1, 0, 1 }, { 3, 0, 0, 2 }, { 7, 9, 0 },
      { 6, 5, 0, 1, 0, 2, 0 } };
```

<figure><img src="../../../.gitbook/assets/image (1) (2) (2).png" alt=""><figcaption><p>Salida</p></figcaption></figure>

### Solución:

```java
public static void main(String args[]) {

		// se declara e inicializa la tabla bidimensional
		int[][] tabla = { { 7, 0, 2, 1, 0, 1 }, { 3, 0, 0, 2 }, { 7, 9, 0 },
				{ 6, 5, 0, 1, 0, 2, 0 } };

		// tabla.length -> longitud de la primera dimensi�n
		// tabla[indice].length -> longitud de la segunda dimensi�n

		// comprimir eliminando ceros
		//Recorrer el array y por cada fila
		//Contar el número de ceros
		//Crear un array con el nuevo tamaño (quitando los ceros)
		//copiar los números que no son 0 al nuevo array
		for (int i = 0; i < tabla.length; i++) {
			int noCeros = 0;
			for (int j = 0; j < tabla[i].length; j++) {
				if (tabla[i][j] != 0)
					noCeros++;
			}
			// se reserva justo lo que se necesita
			int[] secuenciaAux = new int[noCeros];

			for (int j = 0, k = 0; j < tabla[i].length; j++) {
				if (tabla[i][j] != 0) {
					secuenciaAux[k] = tabla[i][j];
					k++;
				}
			}
			tabla[i] = secuenciaAux;
		}

		// ordenar por longitud
		//Mientras haya intercambios
		//Recorrer el array comparando posición i con i+1
		//si tamaño posicion i > tamaño posicion i+1
		//intercambio
		boolean cambio;
		do {
			cambio = false;
			for (int i = 0; i < tabla.length - 1; i++)
				if (tabla[i].length > tabla[i + 1].length) {
					int[] sAux = tabla[i];
					tabla[i] = tabla[i + 1];
					tabla[i + 1] = sAux;
					cambio = true;
				}
		} while (cambio);

		// se visualiza para comprobar
		for (int i = 0; i < tabla.length; i++) {
			for (int j = 0; j < tabla[i].length; j++)
				System.out.print(tabla[i][j] + " ");
			System.out.println();

		}
	}
```

### Ejercicio 3 \~ Clase Fracción

Crear la clase Fracción con 3 funciones básicas: Saber si dos fracciones son iguales, saber si dos fracciones son equivalentes y la división resultante de dividir las dos partes de una fracción. No hay ni entrada ni salida en este ejercicio.

### Solución:

```java
class Fraccion {

	private float numerador;
	private float denominador;

	public Fraccion(){
		this(0.0f,0.0f);
	}
	
	public Fraccion(float numerador, float denominador){
		this.numerador = numerador;
		this.denominador = denominador;
	}

	public String toString(){
		return this.numerador+"/"+this.denominador;
	}
	
	public boolean igual(Fraccion fraccion){
		return (this.numerador == fraccion.numerador) && 
			(this.denominador == fraccion.denominador);
	}
	
	public boolean equivalente(Fraccion fraccion){
		return this.numerador / this.denominador == 
			fraccion.numerador / fraccion.denominador;
	}
	public float resultado(){
		return this.numerador / this.denominador;
	}

    public void recogerTeclado(){
    	java.util.Scanner s = new java.util.Scanner(System.in);

		System.out.print("Dame el numerador: ");
		this.numerador = s.nextInt();
		
		System.out.print("Dame el denominador: ");
		this.denominador = s.nextInt();
    }


}
```
