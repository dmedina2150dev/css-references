# Fondos (backgrounds)

En CSS podemos agregar fondo a los elementos y esto se hace a traves de la propiedad (background) esta propiedad es un Shorthand de varias propiedades que permiten modificar los fondos en CSS.

## background-color
Permite agregar un color de fonde a los elementos.

````
.container {
    background-color: steelblue;
}
````
> Se puede utilizar cualquier valor de (color) que se explican en el apartado de color.

## background-image
Permite agregar imagenes de fondo a los elementos. Para agregar una imagen de fondo usamos la funcion (url()) y entre comillas indicamos la ruta de la imagen.

````
.container {
    background-color: steelblue;
    background-image: url('img/spiderman.png');
    width: 90%;
    height: 500px;
}
````
> Si la imagen es mas pequeña que el elemento se repetira las veces que sea necesario para cubrir el espacio que ocupa el elemento.

## background-repeat
Permite repetir o inpedir que las imagenes que usamos de fondo se repitan por defecto esta viene con el valor de (repeat). Para evitar el comportamiento de repeticion usamos el valor (no-repeat).

Tambien cuenta con otros dos valores que son (repeat-x) y (repeat-y), que haran que la imagen se repita solo en el eje que se asigne en la propiedad.

````
.container {
    background-image: url('img/spiderman.png');
    background-repeat: no-repeat;
    width: 90%;
    height: 500px;
}
````
## background-position
Permite posicionar a la imagen con valores como (top, left, right, bottom, center). Se puede juagar asignando dos de estos valores.

````
.container {
    background-color: #723CD6;
    background-image: url('img/spiderman.png');
    background-repeat: no-repeat;
    background-position: bottom left;
    width: 90%;
    height: 500px;
}
````

## background-size
Permite darle un tamaño a la imagen, se pueden utilizar medidas como (px) o (%) etc... O palabras reservadas como (cover) o (contain).

````
.container {
    background-color: #723CD6;
    background-image: url('img/spiderman.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    width: 90%;
    height: 500px;
}
````


Tambien es posible utilizar con (background) la funcion gradient (linear-gradient):

````
.container {   
    background-image: linear-gradient(#000, #00F);
    width: 90%;
    height: 500px;
}
````

Otro ejemplo es que tambien se puede convinar el gradient con la funcion url separadas por (,)

````
.container {
    margin: 50px auto;
    background-image: linear-gradient(#000000aa, rgba(0, 0, 255, 0.629)), url('imagen.jpg');
    width: 90%;
    height: 500px;
    color: #FFF;
    text-align: center;
    padding-top: 200px;
    font-size: 50px;
}

````

Usando las propiedades explicadas arriba

````

.container {
    margin: 50px auto;
    background-image: linear-gradient(#000000aa, rgba(0, 0, 255, 0.629)), url('imagen.jpg');
    width: 90%;
    height: 500px;
    color: #FFF;
    text-align: center;
    padding-top: 200px;
    font-size: 50px;
    background-size: cover;
    background-position: center;
}
````

