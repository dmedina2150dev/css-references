# TRANSITIONS
Las transiciones son un paso o cambio de un estado a otro. En CSS las transiciones son la primera forma de animar a un elemento, nos permiten animar cambios de estado a otro, haciendo que esto pase de manera no instantanea. Y normalmente las propiedades (transform) y (opacity) se crearon para generan animaciones y transiciones.

Lo normal es que las transiciones requieran un diparador, como las psudoclasses (active, hover, target, focus, checked).

**NOTA: CUANDO USAMOS TRANSICIONES SE RECOMIENDA TENER UN CONTENDOR PADRE PARA EVITAR QUE SE MUEVA EL ELEMENTO DE FORMA EXTRAÑA**

> Existen propiedades que no son animables y por ende las transiciones no funcionan en ellas como por ejemplo (justify-content)

[Propiedades animables en CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)


````
.element {
    margin: 150px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    transition: .5s;
}
````

(transition) es un shorthand de (transition-property)


### transition-property
Especifica la propiedad o propiedades que tendra la transicion. Las propiedades aqui definida cuando cambien de estado o valor, no lo haran de forma instantanea si no con una transicion o animacion. Siempre y cuando la propiedad sea animable. Por defecto es (all). Para definir mas propiedades las declaramos separadas por (,) comas.

````
.element {
    margin: 150px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    
    transition-property: all;
}
````

**NOTA: Es recomendable definir la propiedad o las propiedades, para evitar consumir tantos recursos del navegador**

### transition-duration
Especifica la duracion de la transicion. Por defecto usa valores de tiempo. Se pueden utilizar segundos **(s)**, o milisegundo **(ms)**. El valor por defecto es de (0s). Por esto es que se requiere pornerle un valor de segundos a la animacion o transicion.

````
.element {
    margin: 150px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    
    transition-property: background-color, transform;
    transition-duration: 300ms;
}

.container:hover .element {
    background-color: black;
    transform: translate(100%, 100%) scale(1.3) rotate(80deg);
}
````

**NOTA: Lo más basico de una transicion o el minimo requerido para una transicion es la duracion.**

### transition-timing-function
Define la curva de aceleracion de la transicion, entre el estado inicial y el estado final. Es decir como se comporta la transicion.

Por defecto es **(ease)** que aumenta la velocidad de la transicion a la mitad y disminuyendola al final de la misma. Primero acelera y al final decrementa la velocidad.

````
.element {
    margin: 150px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    /* transition: .5s; */
    transition-property: all;
    transition-duration: 300ms;
    transition-timing-function: ease; /*Por defecto*/
}
````

Tambien tenemos **(ease-in)** que comienza lentamente y al final la velocidad va en aumento.

````
.element {
    margin: 150px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    /* transition: .5s; */
    transition-property: all;
    transition-duration: 300ms;
    transition-timing-function: ease-in;
}
````

Otro seria **(ease-in-out)** que la animacion comienza lentamente, acelera y al final disminuye.

````
.element {
    margin: 150px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    /* transition: .5s; */
    transition-property: all;
    transition-duration: 300ms;
    transition-timing-function: ease-in-out;
}
````

Tenemos tambien **(ease-out)** que comienza la animacion rapidamente, pero cuando pasa el tiempo disminuye la velocidad.

````
.element {
    margin: 150px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    /* transition: .5s; */
    transition-property: all;
    transition-duration: 300ms;
    transition-timing-function: ease-out;
}
````

Y otro mas seria **(linear)** que seria una velocidad uniforme de principio a fin.

````
.element {
    margin: 150px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    /* transition: .5s; */
    transition-property: all;
    transition-duration: 300ms;
    transition-timing-function: ease-out;
}
````

### transition-delay
Define el tiempo de espera, para que una transicion se ejecute. Al igual que (transition-duration) requiere unidades de tiempo. Y por defecto igual su valor es (0s).

````
.element {
    margin: 150px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    /* transition: .5s; */
    transition-property: all;
    transition-duration: 300ms;
    transition-timing-function: ease-out;
    transition-delay: 1000ms;
}
````

**NOTA**
> Cuando usamos el shorthand (transition), no hay diferencia en el orden en que coloquemos los valores. Pero siempre el primer valor de tiempo que se coloque se tomara como el valor de la duracion

````
.element {
    margin: 150px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    transition: background-color, transform .5s linear 1s;
    
}
````