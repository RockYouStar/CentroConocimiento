# Orientación a objetos

La orientación a objetos es una propiedad de numerosos lenguajes de programación que restringe el uso de ciertas funciones a variables del tipo del objeto que estamos usando. Este tipo de objeto se denomina clase, y lo definiremos a continuación.

El objetivo principal de la orientación a objetos es la herencia de funciones (explicado en la sección de [Herencia](herencia.md) ), la encapsulación (usar funciones privadas) y el polimorfismo.

## Clases

Lo primero que tenemos que definir para entender la orientación a objetos son las clases, que son los tipos de objetos que vamos a usar a la hora de aplicar sus funciones. Cada clase tendrá instancias propias, que serán estos objetos, y que tendrán cierta independencia cada uno del resto.

Así, las clases se definen en base a sus atributos, que son los diferentes campos de variables que tienen los objetos. Por ejemplo, una clase coche tendría unos atributos como "matrícula", o "modelo", que serían específicos para cada una de las instancias de esta clase.

<figure><img src="../../../.gitbook/assets/image (1) (1) (2).png" alt=""><figcaption><p>Declaración de una clase en Java</p></figcaption></figure>

Como podemos comprobar, antes de cada declaración de variable tenemos un campo que en este caso es 'private'. Esto quiere decir que solamente se podrá acceder a ese campo desde la propia clase, concretamente desde una de las funciones que declaremos en su interior. Esto asegura la encapsulación, ya que no deja acceder a información de los objetos desde fuera de estos. Este campo podría ser 'public' si se pudiera acceder desde fuera de la propia clase.

Otro tipo de atributo muy importante son los atributos estáticos. Estos atributos tienen una característica principal y es que no son únicos para cada objeto, como el resto de ellos, si no que se comparten entre todos los objetos de la clase. Un ejemplo sería si quisiéramos llevar una cuenta de los objetos de una clase que hemos creado. Puesto que es una característica de la clase entera y no de cada uno de los objetos, podríamos declararlo como estático.

`static int cuenta;`

## Constructores

En las clases existen un tipo de métodos a parte de los que realizan tareas una vez dentro de la clase que se llaman constructores. Estos son fragmentos de código que se ejecutan cada vez que se crea un objeto de la clase que estamos especificando, de ahí su nombre. Su objetivo principal normalmente es ajustar los diferentes parámetros del objeto, aunque realmente pueden llevar a cabo cualquier operación.

Para declarar un constructor, tendremos que hacerlo después de la declaración de atributos pero antes de la declaración del resto de los métodos de la clase.

Para crearlo escribiremos su tipo de acceso, que siempre tiene que ser 'public', seguido del nombre de la clase y de un paréntesis que contenga los argumentos que le meteremos al constructor para que este pueda llevar a cabo su tarea.

Podremos crear todos los constructores que queramos, siempre y cuando no existan dos con el mismo número de argumentos, ya que si no no se podría distinguir entre ellos. Los constructores también pueden ir sin argumentos. Algunos ejemplos de implementación son los siguientes.

<figure><img src="../../../.gitbook/assets/image (5) (2).png" alt=""><figcaption></figcaption></figure>

Para crear otros métodos que no sean el constructor, usaremos un formato similar, con la diferencia de que antes del nombre del método deberemos especificar el tipo de dato que devuelve (como cualquier otra función), y el nombre deberá ser otro diferente al de la clase en la que nos encontremos

## Uso del this

Por último, comentar brevemente como acceder a los atributos del objeto una vez dentro de un método de una clase (solo podremos acceder a estos atributos desde dentro del método por la encapsulación)

Para indicar que queremos referirnos a un atributo, usaremos this.nombreAtributo. De esa manera, no existirá confusión con otras variables de mismo nombre que puedan llegar a causar confusión. Un ejemplo es la imagen expuesta anteriormente, en la que se refieren a todos los atributos del objeto.
