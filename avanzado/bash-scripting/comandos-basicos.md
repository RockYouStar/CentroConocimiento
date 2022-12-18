# Comandos Básicos

## echo

El comando **echo** es uno de los comando más básicos y fundamentales en los scripts de bash. Se utiliza principalmente para imprimir el texto o la salida de la terminal linux.&#x20;

El comando echo imprimirá el texto o datos en la terminal sea lo que sea que escribas.

### Ejemplo de uso:

```bash
$ echo "Hola, estamos imprimiendo con echo"
Hola, estamos imprimiendo con echo
```

## cat

El comando **cat** es uno de los comandos más utilizados en Linux. Se utiliza para listar el contenido de un archivo.

### Ejemplos de uso de cat:

```bash
$ cat archivo1.txt 
hola que tal todo?
```

Podemos redirigir la salida estándar (stdout) a un fichero:

```bash
$ cat archivo1.txt > archivo2.txt
$ cat archivo2.txt 
hola que tal todo?
```

## cp

El comando **cp** permite copiar archivos de un directorio a otro. Se puede copiar al mismo directorio renombrando el fichero.

### Ejemplo de uso:

```bash
$ ls
archivo1.txt  archivo2.txt  directorio1  directorio2
$ cp archivo1.txt directorio2/
$ cd directorio2/
$ ls
archivo1.txt
```

## grep

Permite buscar por determinados términos en el contenido de un archivo o una cadena que se le pase como argumento. Sigue la estructura:

`grep opciones expresiones archivo/string`

### Ejemplo de uso:

```bash
$ cat ejemplo.txt
Linea 1
Line 2
Ejemplo 3
$ grep "Line" ejemplo.txt
Line 2
```

## find

Comando de búsqueda recursiva que busca tanto en el directorio especificado como en los que subyacen al mismo, que permite buscar por otra clase de parámetros más propios de los nombres de fichero. Estructura:

find directorio condiciones/opciones

Ejemplo de uso:

```bash
$ find /bin/ -name "y*"
/bin/yelp
/bin/yes
/bin/ypdomainname
```

## mv

El comando **mv** permite mover archivos de una ruta a otra. También permite renombrar ficheros. Los argumentos son:

`mv archivo destino`

### Ejemplo de uso:

```bash
$ mv directorio2/archivo1.txt directorio1/
```

## mkdir

El comando **mkdir** permite crear un nuevo directorio. Los argumentos son:

`mkdir nombreDirectorio`

### Ejemplo de uso:

```bash
$ mkdir directorio3
$ ls
archivo1.txt  archivo2.txt  directorio1  directorio2  directorio3
```

## rmdir

El comando **rmdir** permite eliminar un directorio. Es importante saber que solo podemos borrar directorios vacíos.

### Ejemplo de uso:

```bash
$ ls
archivo1.txt  archivo2.txt  directorio1  directorio2  directorio3
$ rmdir directorio3/
$ ls
archivo1.txt  archivo2.txt  directorio1  directorio2
```

## rm

El comando **rm** se utiliza par eliminar archivos y directorios. Si queremos borrar un directorio con contenido podemos usar:&#x20;

```bash
rm -rf directorio
```

### Ejemplo de uso:

```bash
$ ls directorio1/
archivo1.txt
$ rm -rf directorio1/
```

