# ANIMATION
Las animaciones o la propiedad (animation) es la segunda forma de animar elementos en CSS, y se diferencia de la propiedad (transition) porque no requiere un disparador o un trigger, para generar la animacion. Pero de igual forma permite cambiar o animar el cambio de un estado a otro, a su vez permite animar distintos estilos o propiedades a la vez y asi controlar todo el flujo de la animacion.

Para utilizar las animaciones se utiliza la propiedad (animation) que es un shorthand de varias propiedades. A demas utilizamos los (@keyframes) o conocidos como regla add rule keyframe.


> @keyframes -> se inicia con el nombre de la animacion puede ser el nombre que queramos, y hasta se pueden conformar oraciones pequeñas separadas por guiones (-).

> Basicamente los (keyframes) nos permitirar crear o declarar y controlar los pasos de una animacion.

> Los (keyframes) contienen dos palabras claves que forman un estilos de metodos dentro de él. Estas palabras o metodos son (from{}) y (to{}).

````
@keyframes cambiar-color {
    from {
        width: 250px;
        background-color: #000;
    }
    to {
        width: 300px;
         background-color: purple;
    }
}
````

> Tambien es posible utilizar porcentajes y podiramos representar a (from{}) y a (to{}) con ellos.

````
@keyframes cambiar-color {
    0% {
        width: 250px;
        background-color: #000;
    }
    100% {
        width: 300px;
         background-color: purple;
    }
}
````

Y como se puede notar se pueden agregar varias propiedades de estilos dentro de estos bloques de codigo CSS. Pero es igual que con las transiciones, solo podemos animar las propiedades animables. 

Tambien es posible que añadamos tantos porcentajes como sean necesarios para controlar nuestra animacion, Siempre y cuando estos este en el rango de 0% a 100%.

````
@keyframes cambiar-color {
    0% {
        transform: scaleY(1);
    }
    20% {
        transform: scaleY(1.2);
    }
    33% {
        transform: scaleY(2);
    }
    57% {
        transform: scaleY(1.5);
    }
    100% {
        transform: scaleY(2.3);
    }
}
````

### animation-name
Referencia al (keyframes) que tendra el selector.


### animation-duration
Representa la duracion de la animacion. Al igual que la propiedad (transition-duration) es una propiedad que acepta valores de tiempo, y requiere un valor en segundos (s).


### animation-timing-function
Es una propiedad muy similar a (transition-timing-function), su valor por defecto es (ease), Por defecto es **(ease)** que aumenta la velocidad de la transicion a la mitad y disminuyendola al final de la misma. Primero acelera y al final decrementa la velocidad.

Tambien tenemos **(ease-in)** que comienza lentamente y al final la velocidad va en aumento. Y **(ease-in-out)** que la animacion comienza lentamente, acelera y al final disminuye. Tenemos tambien **(ease-out)** que comienza la animacion rapidamente, pero cuando pasa el tiempo disminuye la velocidad. Como tambien **(linear)** que seria una velocidad uniforme de principio a fin.


### animation-iteration-count
Con esta propiedad defiinimos cuantas veces se va a repetir la animacion, por defecto es (1). La animacion solo sucedera una vez. Este valor pueden ser numeros enteros. Y tambien unu valor con una palabra clave (infinite) el cual hace que la animacion nunca termine.

### animation-direction
Con esta propiedad definimos desde que punto parte la animacion hablando del (keyframe). Su valor por defecto es **(normal)**, tambien tiene un valor clave llamado **(reverse)** que va desde (to) a (from) o de 100% a 0% pero esto va de un golpe. Existe otro como **(alternate)** que no regresa de golpe si no que regresa del 100% a 0% con una animacion. Y **(alternate-reverse)** que vamos a empezar del 100% al 0% y llegando al 0% vamos regresar al 100% pero no de golpe si no con una animacion. 


### animation-fill-mode 
Define lo que sucede antes y despues de que una animacion se ejecute. Se encarga de notificarle al navegador si los estilos de la animacion se aplican despues de que termine o antes de que empiece. Por defecto es **(none)**, tambien tenemos **(forwards)** hace que los estilos de la animacion se seguiran aplicando aunque esta alla terminado. O tambien podemos usar **(backwards)** este valor es lo contrario, el elemento tendra los estilos de la animacion antes de comenzar la animacion. Por ultimo tenemos **(both)** este valor es una combinacion o union de **(forwards)** y **(backwards)** antes de que empiece la animacion tomara los estilos del keyframes y una vez que termine se quedara con esos estilos


### animation-delay
Es igual que (animation-duration) requiere un valor en segundos (s). Y este es para indicar cuanto tiempo va a demorar la animacion en ejecutarse. Por defecto es (0s).


### animation-play-state 
Esta propiedad nos permite controlar cuando corre o no la animacion. Su valor por defecto es (running) es decir la animacion esta corriendo. Tambien podriamos utilizar (paused) Lo cual pausara la animacion.



Todas la anteriores propiedades son parte del shorthand (animation) y como en (transition) no importa el orden. Los unicos que llevan un orden son los tiempos (animation-duration) y (a nimation-delay) donde el primer valor de tiempo siempre sera para duration.


````
/** Este ejemplo nos lo da vscode **/
.selector {
    animation: name duration timing-function delay iteration-count direction fill-mode;
}
````