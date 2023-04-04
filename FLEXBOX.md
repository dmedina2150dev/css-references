# FLEXBOX
Es un modulo de CSS, que fue diseñado para crear sitios flexibles y adaptables a dispositivos moviles.

Para utilizar flexbox lo que necesitamos es un elemento contenedor y este contenedor como minimo debe tener un elemento dentro.

Para habilitarlo en el contenedor lo hacemos con la propiedad (display) y con el valor (flex). Al hacer esto usamos flexbox y creamos un contexto, donde el contenedor ahora se llamara (flex-container) y sus elementos hijos se llamaran (flex-items), pero solamente los hijos directos del contenedor.

````
<div class="container">
    <div class="element element1">#1</div>
    <div class="element element2">#2</div>
</div>

.container {
    display: flex;
}
````

Flexbox permite alinear los elementos uno al lado del otro. Si agrandamos el tamaños de los elementos hijos estos no se desbordarian del contenedor.

En flexbox existen dos ejes, el main axis o eje principal y el cross axis o eje secundario.

## main axis
Por defecto va de izquierda a derecha. 

## cross axis
Por defecto va de arriba hacia abajo.

Para modificar los ejes y utilizar el cross axis usamos la propiedad (flex-direction), esta propiedad nos permite cambiar el eje principal o el main axis en el que trabaja flexbox.

````
<div class="container">
    <div class="element element1">#1</div>
    <div class="element element2">#2</div>
</div>

.container {
    display: flex;
    flex-direction: row;
}
````

Por defecto esta propiedad viene con el valor (row) el main axis natural de izquierda a derecha. Pero existe otro valor que es row-reverse que cambia el eje principal o el main axis de derecha a izquiera

````
<div class="container">
    <div class="element element1">#1</div>
    <div class="element element2">#2</div>
</div>

.container {
    display: flex;
    flex-direction: row-reverse;
}
````

Luego tenemos un valor de (column) este cambia el main axis de horizontal a vertical, de arriba hacia abajo. Y el cross axis sera de izquierda a derecha.
Y como en (row) existe (column-reverse) ahora el main axis sera de abajo hacia arriba. Y el croos axis se mantiene de izquierda a derecha.

````
<div class="container">
    <div class="element element1">#1</div>
    <div class="element element2">#2</div>
</div>

.container {
    display: flex;
    flex-direction: column;
}
````

````
<div class="container">
    <div class="element element1">#1</div>
    <div class="element element2">#2</div>
</div>

.container {
    display: flex;
    flex-direction: column-reverse;
}
````


Tambien tenemos la propiedad (flex-wrap), define el comportamiento de los hijos cuando su tamaño sumado revasa el tamaño del main axis, por defecto esta propiedad esta en (nowrap), para evitar que se desborden los hijos del contenedor, y hace que se encojan o reduce su tamaño para que no suceda esto.

````
<div class="container">
    <div class="element element1">#1</div>
    <div class="element element2">#2</div>
</div>

.container {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
}

.element {
    width: 300px;
    height: 100px;
}
````


Con el valor (wrap), los elementos ocupan el espacio real que deberia ocupar, se crean nuevas lineas en el cross axis.
````
<div class="container">
    <div class="element element1">#1</div>
    <div class="element element2">#2</div>
</div>

.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}

.element {
    width: 300px;
    height: 100px;
}
````

Para cambiar la alineacion en el main axis tenemos la propiedad (justify-content), para utilizar esta propiedad se debe tener espacio disponible en el eje principal.  

Esta propiedad tiene diversos valores los cuales modifican la alineacion y ubicacion de los elementos dependiento del flex-direction que contenta.

Por defecto:
> flex-start: Toma todos los flex-item y los agrupa al comienzo del contenedor o el main axis.

> flex-end: Al contrario agrupa todos los flex-item al final del contenedor.

> center: Permite centrar los flex-item en el contenedor

> space-between: Permite alinear equitativamente los elementos en el main axis. El primero elemento siempre se pegara al inicio el main axis, y el ultimo al final del main axis.

> space-around: Todos los elementos se distrubuyen equitativamente en ambos lados de los elemento, cuando hay dos elementos juntos se suman los espacios que distrubuyen a los elementos.

> space-evenly: Este igual distrubuye equitativamente los espacios, sin importar si hay elementos uno al lado del otro. 


Para cambiar la alineacion en el cross axis tenemos dos propiedad (align-items) y (align-content), esta propiedades y su alineacion varian respecto a la direccion del main axis (row) o (column).


**align-items: Permite modificar el cross axis y por defecto su valor es (stretch)** 

> stretch: Esto hace que todos los elementos que no tienen un heigth definido se estiren por todo el cross axis.

> flex-start: Los manda al inicio del cross axis.

> flex-end: los manda al final del cross axis.

> center: los alinea al centro del cross axis

> baseline: hace que todos los elemento se alineen a la linea base de los elementos o el contenido que tengan por dentro como el texto.

**align-content: Permite modificar el cross axis, pero solo funciona cuando hay mas de una fila o columna y por defecto su valor es (normal)** 

> nomarl: Esto no hace ningun cambio en el cross axis.

> flex-start: Agrupa todos los elementos y los manda al inicio del cross axis.

> flex-end: Agrupa todos los elementos y los manda al del cross axis.

> center: Agrupa todos los elementos y los manda al los alinea al centro del cross axis

> space-between: separa los elementos y los manda a las esquinas del cross axis, repartiendo el espacio equitativamente.

> space-around: Todos los elementos se distrubuyen equitativamente en ambos lados de los elemento, cuando hay dos elementos juntos se suman los espacios que distrubuyen a los elementos en el cross axis.

> space-evenly: Este igual distrubuye equitativamente los espacios, sin importar si hay elementos uno al lado del otro, y lo distruye equitativamente.


***TODAS LAS PROPIEDADES ANTERIORES SON APLICADAS EN EL CONTENEDOR QUE OCUPARA LAS VECES DE (FLEX-CONTAINER)***


Para los elementos o (flex-item) tambien tiene propiedades que podemos utilizar para modificar su ubicacion.

Una de estas propiedades es (order), esta propiedad la contienen todos los elementos y su valor por defecto es de (0). Esta propiedad permite cambiar el orden de los (flex-item), mientras mayor sea el valor de (order) se pondra al final de los elementos. Si el numero es negativo por ende seria menor que (0) esto lo posicionaria por delante.

````
.container {
    width: 90%;
    max-width: 800px;
    min-height: 600px;
    margin: 80px auto;
    border: 3px solid #000;

    display: flex;
}
.element {
    width: 100px;
    height: 100px;
}
.element2 {
    background-color: purple;
    order: 1;
}
````


Otra de estas propiedades es (flex-grow), define el factor de crecimiento de todos los elementos, por defecto viene en (0). flex-grow detecta el espacio que hay disponible en el flex-container y estira los elementos hasta cubrir el espacio vacio. 

````
.element {
    color: #FFF;
    font-size: 2rem;
    text-align: center;
    line-height: 100px;
    background-color: salmon;
    width: 100px;
    height: 100px;
    flex-grow: 1; /*Toma todo el espacio*/
}

.element1 {
    background-color: crimson;
    flex-grow: 2; /* Tomara lo que ocupe un solo elemento dos veces */
}
.element2 {
    background-color: purple;
}
.element3 {
    background-color: steelblue;
}
````


Tambien tenemos (flex-shrink), que es todo lo contrario a (flex-grow), hace que los elementos se pongan mas pequeños, si colocamos el valor de esta propiedad en (0) deshabilitamos la capacidad de que los elementos se achiquen. Su valor por defecto es (1) y hace que todos se hagan pequeños por igual.

Si colocamos algun otro valor que no sea (0) o (1), por ejemplo (3) ese elemento se hara mas pequeño que los demas.

````
.element {
    
    width: 300px;
    height: 100px;

    flex-shrink: 1;
}

.element1 {
    background-color: crimson;
}
.element2 {
    background-color: purple;
}
.element3 {
    background-color: steelblue;
    flex-shrink: 3;
}
````


Despues tenemos (flex-basis), esta propiedad nos permite indicar el tamaño de los elementos en el main axis por defecto seria sutituria al width. Recuerda que si cambia el main axis a column. EL flex-basis seria el heigth.



Tambien contamos con (align-self), que nos permite alinerar solamente al elemeto que estamos seleccionando, y permite modificarlo a traves del cross axis. Y posee los mismo valores que align-items
