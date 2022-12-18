# Comandos

Un comando o mandato es una instrucción que debe ser interpretada por una terminal o shell (como se verá en el siguiente apartado) el cual ejecuta las diferentes tareas que se indiquen, de acuerdo con su sintaxis.

Algunos de los más básicos (pueden seguirse viendo más en el apartado de [Bash Scripting](../../../avanzado/bash-scripting/comandos-basicos.md) asociado) son:

## ls

El comando **ls** es un comando muy básico del shell que lista la información de archivos y directorios en un sistema de archivos.

### Ejemplo de uso:

```bash
$ ls
archivo1.txt  archivo2.txt  directorio1  directorio2
```

## pwd

El comando **pwd** permite saber la ruta del directorio de trabajo actual en el que nos encontramos.

El comando devuelve una ruta absoluta,

### Ejemplo de uso:

```bash
$ pwd
/tmp/deleteme
```

## cd

El comando **cd** permite navegar por los directorios de Linux. Podemos trabajar tanto con rutas absolutas como relativas.

* **cd ..** permite ir un directorio hacia arriba
* **cd** para ir directamente al directorio HOME
* **cd-** para ir al directorio anterior

### Ejemplo de uso:

```shell
$ ls
archivo1.txt  archivo2.txt  directorio1  directorio2
$ cd directorio1/
$ pwd
/tmp/deleteme/directorio1
```

## chmod

Permite editar los permisos con los que cuenta un archivo, si se dispone previamente de los privilegios suficientes para realizarlo. Se puede hacer tanto por opciones especificando el usuario afectado en letras, como por números en octal que se corresponden a los diferentes permisos cuando se transcribe a binario.

### Ejemplos de uso:

`$ chmod 544 archivo.txt`: otorga a archivo.txt los permisos de lectura y ejecución para el usuario, pero solamente de lectura para usuarios del mismo grupo y resto de usuarios

`$ chmod -u+x -g-x -o-x archivo.txt`: da a archivo.txt permisos de ejecución al usuario, y se los elimina al resto de usuarios (tanto grupo como otros)

`$ chmod -urwx archivo.txt`: en este caso archivo.txt dispone de todos los permisos para el usuario.
