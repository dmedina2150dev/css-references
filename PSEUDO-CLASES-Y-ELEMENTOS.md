# PSEUDOCLASES & PSEUDOELEMENTOS


## PSEUDOCLASES
Son un tipo de selector en CSS que indica mayormente el estado de un elemento y nos ayuda a generar interaciones en nuestra pagina con CSS. Las pseudoclasses empiezan con (:) siempre empiezan con dos puntos, y tienen una especificidad de (10). 

Aunque la mayoria indica un estado de los elementos, hay especiales como (root) esta nos sirve para declarar (custom properties) en la raiz del documento, ya que (:root) es exactamente lo mismo que la etiqueta (html).

````
html {
    background-color: steelblue;
}
:root {
    background-color: tomato;
}
````
Esto vendria siendo lo mismo porque (root) es una pseudoclasse que represente (html), pero al ser una pseudoclasse tiene una especificidad de (10) y se distinge con los (:) al principio. Tambien las pseudoclasses pueden ir solas o acompañadas de otro selector.


Estos estados de los elementos nos sirven para crear animaciones.

### ESTADOS

>:hover --> Cuando se pasa el mouse por el elemento.
````
.link:hover {
    background-color: blueviolet;
}
````

>:active --> Cuando el elemento esta siendo presionado por el mouse.
````
.link:active {
    background-color: blueviolet;
    transform: translateY(10px);
}
````

>:target --> Sirve para referenciar elementos html usando la etiqueta de ancla (<a>#</a>).
````
.element1:target {
    transform: translateX(100%);
}
````

>:checked --> Sirve para los elementos radio y checkbox cuando estan en estado activos.
````
.check:checked + .label {
    background-color: green;
}
````

>:focus --> Indica cuando el usuario esta haciendo foco o esta activo en un input.
````
.input:focus {
    color: #FFF;
    background-color: #000;
}
````

>:placeholder-shown --> Indica el estado cuando se muestra el placeholder donde se este mostrando

[Listado PseudoClases](https://developer.mozilla.org/es/docs/Web/CSS/Pseudo-classes)



## PSEUDOELEMENTOS
Podrian ser iguales a las pseudoclasse, pero no es tan correcto. A diferencia de los pseudoclasse los pseudoelementos empiezan con (::), y a demas en vez de indicar estados de los elementos, estos permiten crear estilos extra en CSS y su especificidad es de (1) asi como los selectores de tipo.

Los mas utilizados o fundamentales son (::after) y (::before), estos nos permiten crear elementos sin que los escribamos en el HTML. Estos elementos deben contener una propiedad obligatoria que es (content). Los pseudoelementos pueden utilizar cualquier propiedad de CSS.

````
.element1::before {
    content: "";
}
.element1::after  {
    content: "";
}
````
[Listado de PseudoElementos](https://developer.mozilla.org/es/docs/Web/CSS/Pseudo-elements)

**NOTA: Los input no pueden usar pseudoelementos** 