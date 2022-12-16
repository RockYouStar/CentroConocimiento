# Condicionales

La sintáxis básica de los condicionales en bash es:

<pre class="language-bash"><code class="lang-bash">if [ expresion condicional ]
<strong>    then
</strong><strong>        comando
</strong>    else
        comando
fi
</code></pre>

No se pueden hacer comparaciones del tipo a > b directamente. Necesitamos usar el comando test.

test permite hacer comparaciones y algunas comprobaciones útiles:

* test a -eq b --> comprueba si el número a es igual a b.
* test -z cadena --> comprueba si la cadena está vacía.
* test -n cadena --> comprueba si la cadena no está vacía.
* test cadena1 = cadena2 --> comprueba si las cadenas son iguales.
* test -e fichero --> comprueba si existe el fichero.
* test -f fichero --> comprueba si es un fichero.
* test -s fichero --> comprueba si existe el fichero y contiene datos.
* test -d fichero --> comprueba si es un directorio.

### Ejemplo de script:

```bash
#! /bin/bash

echo -n "Introduce un numero: "
read x

if [ $x == 0 ]; then
  echo "El numero es 0"
elif [ $((x%2)) == 0 ]; then
  echo "El numero es par"
else
  echo "El numero es impar"
fi
```

### Ejemplo de ejecución:

```bash
$ ./script1.sh 
Introduce un numero: 0
El numero es 0
$ ./script1.sh 
Introduce un numero: 2
El numero es par
$ ./script1.sh 
Introduce un numero: 4
El numero es par
$ ./script1.sh 
Introduce un numero: 3
El numero es impar
```
