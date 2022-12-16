# While

El bucle while se ejecuta mientras una condición es verdadera:

```
while condicion
do
    ...
done
```

Las condiciones las podemos construir con el comando [test](condicionales.md).&#x20;

### Ejemplo de cálculo del factorial

```bash
#!/bin/bash

contador=$1
factorial=1
while [ $contador -gt 0 ]
do
   factorial=$(( $factorial * $contador ))
   contador=$(( $contador - 1 ))
done
echo "$factorial"
```

Recibe el contador como primer argumento.

### Ejemplo de ejecución:

```bash
$ ./script.sh 6
720
```
