# POSITION
Es la propiedad CSS que nos permite cambiar la forma en que un elemento o varios se posicionan en el navegador. Existen distinos tipos de posicionamiento, Algunos de ellos nos permiten modificar el flujo del navegador.

## Flujo del navegador
Es la forma o manera en la que cada elemento se va posicionando. Al estar vacia la web y crear el primer elemento se posiciona desde la parte superior izquierda del navegador.

### Position (static)
Es el valor que todos los elemento tienen por defecto. Esto hace que todos los elementos siguientes se comporten de forma natural practicamente no cambia nada si asignamos este valor a la propiedad.

Muchas veces no se considera este valor por ser el por defecto que traen todos los elementos.

````
.static {
    background-color: tomato;
    position: static;
}
````

**NOTA**
Los valores de la propiedad (position) que viene de aqui en adelante desbloquean 4 propiedades que nos ayudan a mover el elemento de position en el navegador. Estas propiedades o valores que se desbloquean son los siguientes: (top, left, right, bottom). Estas propiedades al utilizarlas no modifican el posicionamiento de los demas elementos. Como si lo haria el (margin)

**top:** Movera el elemento desde la parte superior hacia abajo si el valor es positivo, si el valor es negativo lo movera hacia arriba desde la parte superior del elemento.

**left:** Movera el elemento desde la parte izquierda hacia la derecha si el valor es positivo, si el valor es negativo lo movera hacia la izquierda desde la parte izquierda del elemento.

**right:** Movera el elemento desde la parte derecha hacia la izquierda si el valor es positivo, si el valor es negativo lo movera hacia la derecha desde la parte derecha del elemento.

**bottom:** Movera el elemento desde la parte de abajo hacia arriba si el valor es positivo, si el valor es negativo lo movera hacia abajo desde la parte inferior del elemento.

### Position (relative)
Por defecto se posiciona como cualquier otro elemento, no se visualiza ningun cambio al principio. Asignar este valor a la propiedad (position) desbloque las 4 propiedades anteriores explicadas, estos valores son valores de offset, es decir son valores que permiten desplazar al elemento a traves del navegador en base a una posicion. Cuando hablamos de relative, la posicion de partida es donde se encuentra el elemento. 


````
.element {
    width: 150px;
    height: 150px;
}

.relative {
    background-color: steelblue;
    border: 4px solid crimson;
    position: relative;
    top: 50px;
    left: -50px;
    right: 180px;
    bottom: 200px;
}
// Esto no funcionara del todo por logica se estan cambiando todas las posiciones a la vez
````

***De igual forma al cambiar la posicion con relative, la posicion del elemento se sigue respetando por los demas elementos.***

### Position (absolute)
Cuando asignamos el valor absolute a la propiedad (position), ese elemento es removido del flujo normal del posicionamiento de los elementos. Es decir ya no tiene lugar reservado en el posicionamiento natural de los elemento como en el caso de (relative). A diferencia de relative, absolute se mueve o tiene como referencia de origen a cualquier elemento ansentro que tenga un position diferente a static. Si no es el caso de algun ansestro, su referencia de origen es body. Este valor igualmente habilita las 4 propiedades anteriormente explicadas.

````
.element {
    width: 150px;
    height: 150px;
    position: relative;
}

.absolute {
    background-color: teal;
    position: absolute;
    margin: 0;
    right: 0;
    bottom: 0;
}
````

### Position (fixed)
Al igual que absolute, este elemento es removido del flujo natural de posicionamiento de elementos del navegador. A diferencia de absolute, fixed se posiciona o tiene como referencia de origen el viewport y ese es el mayor beneficio que contiene fixed, que se referencia al viewport. Este valor igualmente habilita las 4 propiedades anteriormente explicadas.

````
.element {
    width: 150px;
    height: 150px;
    margin-bottom: 15px;
}

.fixed {
    background-color: red;
    position: fixed;
    left: 0;
    bottom: 0;
    margin: 0;
}
````


**NOTA**
Todos los elemento que tengan un position distinto a static, tambien desbloquean un contexto de apilamiento, el que cual nos sirve para manipular que elemento estar por encima de otros elementos, en caso de que 2 elementos o mas lleguen a ocupar el mismo espacio en el navegador. Esto se hace por medio de un eje (z) imaginario. La propiedad es (z-index).

Por defecto cualquier elemento posicionado tiene un (z-index: auto). z-index solo acepta valores enteros. Es recomendado usar numeros grandes con el fin de evitar problemas posicionando otros elementos en medio

````
<div class="container">
    <div class="element relative"></div>
    <div class="element fixed"></div>
</div>

.element {
    width: 150px;
    height: 150px;
    margin-bottom: 15px;
}

.relative {
    background-color: steelblue;
    position: relative;
    left: 30px;
    z-index: 100;
}

.fixed {
    background-color: red;
    position: fixed;
    top: 80px;
}
````

