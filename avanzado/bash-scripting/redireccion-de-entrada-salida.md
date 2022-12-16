# Redirección de entrada salida

La entrada estándar (stdin) es el sitio de donde lee los datos de entrada un comando o programa, normalmente es el teclado.&#x20;

La salida estándar (stdout) es el sitio donde escribe mensajes un comando o programa, normalmente es la pantalla.&#x20;

También existe una salida de error (stderr) que es donde envían los comandos o programas los mensajes de error.

Se puede redireccionar stdin, stdout y stderr de cualquier mandato o programa:

* comando < fichero: coge stdin del fichero.
* comando > fichero: envía stdout al fichero.
* comando >> fichero: envía stdout al fichero.
* comando 2> fichero: envía stderr al fichero.
* comando 2>&1: envía stderr al mismo sitio donde vaya stdout.&#x20;
* comando &> fichero: envía stderr y stdout al fichero.

Otra forma de redirección son los pipes, que permiten redireccionar el stdout de un mandato al stdin de otro mandato:

```bash
$ cat /etc/passwd | wc -l
54
```

```bash
$ echo "hola" | rev
aloh
```

No todos los programas reciben su entrada por la entrada estándar. Puede que los reciban por argumentos.

Para unir comandos que generan su salida por stdout con otros que reciben su entrada por argumentos se puede ejecutar el mandato antes de que se evalúe la linea completa. Esto se consigue encerrando el mandato entre comillas invertidas \`mandato\` o con `$(mandato).` Otra solucióne es usar `xargs:`

```bash
$ find . -name "*.txt" | xargs cat
hola que tal todo?
hola que tal todo
```

