# For

El bucle for tiene una sintaxis distinta a la habitual de otros lenguajes.&#x20;

```
for variable
do
    ...
done
```

### Ejemplo que imprime los números del 1 al 10:

```bash
#!/bin/bash
for i in {1..10}
do
    echo "Iteracion $i"
done
```

### Ejemplo de ejecución:

```bash
$ bash script.sh 
Iteracion 1
Iteracion 2
Iteracion 3
Iteracion 4
Iteracion 5
Iteracion 6
Iteracion 7
Iteracion 8
Iteracion 9
Iteracion 10
```
