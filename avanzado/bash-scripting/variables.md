# Variables

En la shell se puden declarar variables, dándoles un valor directamente:

```bash
NOMBRE=valor
```

Frecuentemente, se utilizan mayúsculas para el nombre de la variable.

Para usar la variable podemos usar `$NOMBRE` o `${NOMBRE}`

```bash
$ NOMBRE=DIEGO
$ echo $NOMBRE
DIEGO
```

Hay variables predefinidas como:&#x20;

* `HOME`: el directorio inicial del usuario.&#x20;
* `HOSTNAME`: nombre de la máquina.&#x20;
* `PATH`: lista de directorios donde la shell busca ejecutables.&#x20;

Los comandos `env`y `printenv` muestran las variables definidas. Solo si son exportables a los procesos hijos.

Podemos eliminar una variable con `unset`:

```bash
$ NOMBRE=DIEGO
$ echo $NOMBRE
DIEGO
$ unset NOMBRE
$ echo $NOMBRE

$
```

Las variables almacenan información alfanumérica. Es importante saber que todas las variables y operadores se tratan como strings.

Para poder realizar operaciones aritméticas debemos usar los comandos `bc` o `expr` o `$((operacion))`

```bash
$ expr 10 + 10
20
$ echo $((4*4))
16
$ echo "3 * 6" | bc
18
```
