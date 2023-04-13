# PSEUDOCLASES & PSEUDOELEMENTOS


## PSEUDOCLASES
Son un tipo de selector en CSS que indica mayormente el estado de un elemento y nos ayuda a generar interaciones en nuestra pagina con CSS. Las pseudoclases empiezan con (:) siempre empiezan con dos puntos, y tienen una especificidad de (10). 

Aunque la mayoria indica un estado de los elementos, hay especiales como (root) esta nos sirve para declarar (custom properties) en la raiz del documento, ya que (:root) es exactamente lo mismo que la etiqueta (html).

````
html {
    background-color: steelblue;
}
:root {
    background-color: tomato;
}
````
Esto vendria siendo lo mismo, pero al ser una pseudoclase tiene una especificidad de (10) y se distinge con los (:) al principio. Tambien las pseudoclases pueden ir solas o acompañadas de otro selector.

````
.link:hover {
    background-color: blueviolet;
}
````

Estos estados de los elementos nos sirven para crear animaciones.

### ESTADOS

>:hover --> Cuando pasa el mouse por el elemento
>:active --> Cuando el elemento esta siendo presionado por el mouse.
>:target --> Sirve para referenciar elementos html usando la etiqueta de ancla (<a>#</a>).
>:checked --> Sirve para los elementos radio y checkbox cuando estan activos

