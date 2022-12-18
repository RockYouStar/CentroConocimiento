# Simétrica

### Funciones hash

Funciones con dominio en {0,1}\* y rango en {0,1}^m, siendo m un numero entero positivo prefijado, resumen cadenas de bits y son resistentes a colisiones. Uno de sus usos principales es la comprobación rápida de información, también se usan para garantizar la integridad.

### Cifrados en flujo

Un cifrado en flujo toma contenido de tamaño arbitrario y lo cifran, bit por bit, devolviendo un texto cifrado del mismo tamaño.

Tomamos un generador pseudoaletorio "G" con factor de expansión l y construímos un esquema de cifrado:

Gen(1n) elige k ∈ {0,1}n

Dado m ∈ {0,1}l(n) Enc (m):= G(k) ⨁ m

Dado c ∈ {0,1}l(n) Dec (c):= G(k) ⨁ c

### Cifrados en bloque

Los cifrados de bloque trabajan sobre un conjunto de bits de tamaño fijo, produciendo un texto cifrado del mismo tamaño. Básicamente son permutaciones pseudoaletorias.

#### DES

Consiste en una red de Feistel de 16 rondas, en cada ronda se genera una subclave de 48 bits eligiendo 24 de la parte izquierda y 24 de la parte derecha de la clave original.

Contra DES el mejor ataque conocido en la práctica es la búsqueda exhaustiva en el espacio de claves.

#### AES

Creado en 1997, cuando sacaron a concurso la creación un nuevo cifrador en bloque que sustituya a DES.

Es, esencialmente, una red de sustitución-permutación, un array 4x4 de bytes, llamado state se va modificando a lo largo de las rondas.

1. AddRoundKey: se genera una subclave de 128 bits a partir de la clave, se interpreta como un array 4x4 de bytes y se hace XOR con el estado.
2. SubBytes: cada byte del estado se sustituye por otro mediante una S-caja fija para todo el algoritmo.
3. ShiftRows: los bytes de cada fila del estado se desplazan hacia la izquierda 0 posiciones en la primera fila 1 posición en la segunda fila 2 posiciones en la tercera fila 3 posiciones en la cuarta fila.
4. MixColumns: se multiplica el estado por una matriz 4x4 invertible fija.

Los únicos ataques no triviales son a variantes con menos rondas de AES y, aún así, no son eficientes.
