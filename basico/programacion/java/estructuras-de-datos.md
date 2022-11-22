# Estructuras de datos

**La estructura de datos en Java** es el sistema mediante el cual se organizan los datos en la memoria de la aplicación que se está programando. Existen muchas formas de organizar los datos en la memoria, veremos a continuación las listas, los conjuntos y los mapas.

### Listas

Las listas son un tipo de colección que hereda de la interface collection, son una estructura de datos que respeta el orden en el cual fueron agregados los elementos, también permiten registros repetidos.

Esta interface o los objetos de esta, representan una colección ordenada de elementos, en la cual se tiene un control absoluto y preciso del lugar en el que se quiere insertar.

Por medio de la Lista nosotros tenemos la posibilidad de decir en que posición (al inicio, al final o cualquier otro lugar) puede ser insertado o eliminado un elemento.

También es posible acceder a sus elementos a través de su índice; el cual representa la posición del elemento en la lista y así se podría buscar un elemento en dicha lista.

La interface List se encuentra en el paquete java.util, algunas de las clases que implementa esta interface son ArrayList, LinkedList, Vector.

### Conjuntos

Los conjuntos no son un tipo de estructuras de datos que no mantienen el orden de inserción y por lo tanto es imposible recuperar los elementos en el orden en que fueron insertados.

Otra característica muy interesante es que no se permiten elementos duplicados, por tanto, al insertar un elemento en el conjunto no tendremos que comprobar si el elemento está ya o no en el conjunto con otra función aparte.

Por estos motivos es la estructura de datos más eficiente buscando elementos pero la inserción de elementos es mas costosa que en las listas

### Mapas

La Interface Map en Java, nos permite representar una estructura de datos para almacenar pares "clave/valor"; de tal manera que para una clave solamente tenemos un valor. Esta estructura de datos también es conocida en otros lenguajes de programación como "Diccionarios", aunque en cada lenguajes esta estructura de datos tiene sus matices.

Otro elemento importante a la hora de trabajar con los Maps (aunque no lo es tanto como a la hora de trabajar con los ArrayList) son los Iteradores. Los Iteradores sirven para recorrer los Map y poder trabajar con ellos. Los Iteradores solo tienen tres métodos que son el _“hasNext()”_ para comprobar que siguen quedando elementos en el iterador, el _“next()”_  para que nos de el siguiente elemento del iterador; y el _“remove()”_ que sirve para eliminar el elemento del Iterador. En realidad se puede prescindir de los iteradores para trabajar con los Map ya que la gran ventaja de los Map frente a los ArrayList, es que estos tienen una clave asociada al objeto y se les puede buscar por la clave, aunque nunca esta de más saber utilizar los iteradores para manejar los Map.
