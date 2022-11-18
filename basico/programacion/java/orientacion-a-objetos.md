# Orientación a objetos

La orientación a objetos es una propiedad de numerosos lenguajes de programación que restringe el uso de ciertas funciones a variables del tipo del objeto que estamos usando. Este tipo de objeto se denomina clase, y lo definiremos a continuación.

El objetivo principal de la orientación a objetos es la herencia de funciones (explicado en la sección de [Herencia](herencia.md) ), la encapsulación (usar funciones privadas) y el polimorfismo.

Clases

Lo primero que tenemos que definir para entender la orientación a objetos son las clases, que son los tipos de objetos que vamos a usar a la hora de aplicar sus funciones. Cada clase tendrá instancias propias, que serán estos objetos, y que tendrán cierta independencia cada uno del resto.

Así, las clases se definen en base a sus atributos, que son los diferentes campos de variables que tienen los objetos. Por ejemplo, una clase coche tendría unos atributos como "matrícula", o "modelo", que serían específicos para cada una de las instancias de esta clase.

<figure><img src="../../../.gitbook/assets/image (1) (3).png" alt=""><figcaption><p>Declaración de una clase en Java</p></figcaption></figure>

Como podemos comprobar, antes de cada declaración de variable tenemos un campo que en este caso es 'private'. Esto quiere decir que solamente se podrá acceder a ese campo desde la propia clase, concretamente desde una de las funciones que declaremos en su interior. Esto asegura la encapsulación, ya que no deja acceder a información de los objetos desde fuera de estos. Este campo podría ser 'public' si se pudiera acceder desde fuera &#x20;
