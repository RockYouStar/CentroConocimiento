# Shell

## Definición

La shell es el un programa que sirve de interfaz de comandos entre usuario y Sistema Operativo. Desde ella se pueden ejecutar mandatos y programas para llevar a cabo las tareas que se requieran por parte del usuario o los diferentes servicios.&#x20;

## Primer y segundo plano

Una de las cosas que toda shell convencional suele ofrecer es la posibilidad de usar comandos y sus funciones asociadas en primer o segundo plano. De esta manera, si lo que queremos es dejar procesos ejecutándose que nos impedirían seguir enviando más mandatos (como el comando `cat` sin argumentos, `sleep`, etc.), no se nos bloquea el intérprete.

Cada proceso posee un identificador de proceso o PID, el cual es un identificador único que permite su localización de cara a aquellos mandatos que los gestionen (como los que se verán a continuación)

De esta manera, existen comandos asociados a la gestión de este primer plano (foreground) y segundo plano (background), que son los siguientes:

## ps

Permite ver todos los procesos existentes y sus identificadores de proceso asociados.

### Ejemplo de uso:

```bash
$ sleep 100 &
$ ps
    PID TTY          TIME CMD
   3116 pts/0    00:00:00 bash
  13145 pts/0    00:00:00 sleep
  13146 pts/0    00:00:00 ps
```

Nota: añadir "&" al final de un comando los envía a segundo plano

## jobs

Permite visualizar los procesos que se encuentran detenidos o corriendo en segundo plano.

### Ejemplo de uso:

```bash
$ sleep 100 &
[1] 13183
$ sleep 200
^Z (pulsar Ctrl+Z para detener el comando)
$ jobs
[1]-  Running                 sleep 100 &
[2]+  Stopped                 sleep 200
```

## fg

Permite rescatar el último comando detenido (mediante Ctrl+Z típicamente), o el que se especifique a través de su PID.

### Ejemplo de uso:

```bash
$ cat &
$ fg
cat
hello (presionar intro)
hello
```

## bg

Al igual que fg, permite enviar el proceso especificado (o el último detenido) a un segundo plano

### Ejemplo de uso:

```bash
$ sleep 100 &
^Z
$ bg
[1]+ sleep 100 &
$ jobs
[1]+  Running                 sleep 100 &
```
