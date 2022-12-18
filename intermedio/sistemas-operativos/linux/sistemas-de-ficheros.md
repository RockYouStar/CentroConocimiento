# Sistemas de ficheros

## Características principales

El sistema de ficheros de Linux se basa en directorios y archivos exclusivamente. Todos los directorios y archivos nacen del directorio raíz, "/", del cual derivan todos los otros subdirectorios, como el de los binarios ejecutables `/bin` o el que contiene los directorios de inicio de todos los usuarios `/home`.

Una de las particularidades con las que cuenta el sistema Linux es su peculiar diferenciación a la hora de reconocer archivos. Para el sistema operativo, todo son o bien ficheros, o bien directorios. Linux no hace distinciones por extensión como lo haría Windows (ver [Ficheros y ejecutables](../windows/ficheros-y-ejecutables.md)), sino que se fija en los permisos que tiene cada uno de ellos, o por los llamados "bits mágicos" que se encuentran en el archivo, que dan información sobre su codificación (UTF-8, Unicode, etc.).&#x20;

## Permisos y clasificación de ficheros

Un archivo puede tener, por separado o simultáneamente, los permisos de lectura, escritura y ejecución. Estos pueden ser otorgados, respectivamente en orden, para el usuario actual, usuarios que pertenezcan al mismo grupo, y resto de usuarios. Para cambiar los permisos de un archivo se emplea el comando `chmod` visto previamente y para observar los permisos (así como si algo es un directorio o no) se puede mirar mediante el comando ls con la opción -l:

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption><p>Ejecución del comando ls -l</p></figcaption></figure>

Los directorios vienen indicados por el comienzo d, mientras que los archivos tienen un "-". Los permisos de lectura (r), escritura (w) y ejecución (x) se muestran en función de si son concedidos o no para los diferentes tipos de usuarios. También se puede observar que existe un código de colores para indicar si se trata de archivos o <mark style="color:blue;">directorios</mark> (blanco y azul respectivamente), o si se dispone de permisos para su manejo (en <mark style="color:red;">rojo</mark> para los que no).
