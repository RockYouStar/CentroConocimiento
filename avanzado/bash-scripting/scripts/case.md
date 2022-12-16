# Case

Usar case es mucho más fácil que escribir muchas sentencias if y elif anidadas juntas, así que si tienes muchas condiciones que probar, case es la mejor opción.

### Ejemplo de case:

```bash
#!/bin/bash

day=$(date +"%a")

case $day in 

  Mon | Tue | Wed | Thu | Fri)
    echo "today is a weekday"
    ;;

  Sat | Sun) 
    echo "today is the weekend"
    ;;

  *)
    echo "date not recognized"
    ;; 
esac
```

### Ejemplo de ejecución:

```bash
$ ./scriptCase.sh 
today is the weekend
```
