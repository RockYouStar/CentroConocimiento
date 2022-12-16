# Scripts

La shell tienen un lenguaje de scritpting que permite escribir programas utilizando los comandos y algunas estructuras de control de flujo. Podemos separar las sentencias con un cambio de línea o con un `;`

Para poder añadir comentarios usamos el `#`

La primera línea de un script es conocida como Shebang y comienda con `#!`

Esta línea indica qué debe usarse para interpretar el script

### Ejemplo de script básico:

```bash
#! /bin/bash

echo "hola estoy dentro de un script"
echo "voy a listar los archivos"
ls
```

```bash
$ ./script1.sh 
hola estoy dentro de un script
voy a listar los archivos
archivo1.txt  archivo2.txt  directorio2  script1.sh
```

Es muy importante saber que al ejecutar un script se crea una subshell que lo interpreta y ejecuta.

Se puede ejecutar un script con o sin permiso de ejecución invocando de forma explícita a la shell:

```bash
$ bash script1.sh
```

Se puede ejecutar un script en el entorno actual sin crear una subshell:

```bash
$ source script1.sh
```

Los scripts pueden recibir una serie de parámetros o argumentos cuando se ejecutan.

Para poder acceder a los parámetros dentro del script existen unas variables especiales:

* `$#` : número de parámetros.&#x20;
* `$n` : argumento n-ésimo.&#x20;
* `$*` : todos los argumentos en una única cadena.&#x20;
* `$@` : todos los argumentos, cada uno en una cadena.&#x20;
* `$?` : código de error del último mandato ejecutado.&#x20;
* `$$` : pid de la shell que ejecuta el script.

### Ejemplo de uso:

```bash
$ ./script1.sh arg1 arg2 pepe
hola estoy dentro de un script
he recibido 3 argumentos
los argumentos son arg1 arg2 pepe
```

