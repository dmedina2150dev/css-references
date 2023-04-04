# MEDIA QUERIES
Los media queries en CSS nos permiten modificar nuestra web, o nuestras propiedades CSS en funcion del tipo de dispositivo, la orientacion de la pantalla o el ancho del viewport, a demas de otros casos.

Lo que quiere decir que nuestros diseños pueden ser adaptables a dispositivos moviles u otros.

Debemos comprender que las media queries son un tipo de condicional, en las que podemos, declarar estilos. Donde estos estilos se aplicaran en caso de que la media query cumpla la condicion. Y para eso tenemos (Max-width) y (Min-width).

Los media queries igual respetan la cascada de CSS. Y es importante que siempre esten declarados despues de los selectores que se modificaran en el mediaquerie, ya que si se hace al contrario los estilos no se modificaran.

## Max-width
En un mediaquerie indica cual sera el valor maximo que debe tener el viewport para que se aplique el CSS que esta dentro de el, es decdir si tenemos un max-width de 600px, significa que el mediaquerie entrara siempre y cuando el viewport sea menor a 600px porque max-width define el tamaño maximo que se requiere para que se cumpla la condicion.

## Min-width 
En un mediaquerie indica cual sera el valor minimo que debe tener el viewport para que se aplique el CSS que esta dentro de el, es decir si tenemos un min.width de 600px, significa que el mediquerie entrara suempre y cuando el viewport sea mayor a 600px porque min-width define el tamaño minimo que que se necesita para que cumpla la condicion.


````
@media (max-width: 600px) {
    body {
        background-color: black;
    }
}

@media (min-width: 600px) {
    body {
        background-color: #FFF;
    }
}
````

**Dentro de los mediaqueries se puede utilizar cualquier selector**

Cuando se usan mediaqueries con max-width y tienes diferentes tamaños o valores, es recomendable hacerlos en forma decendente, el primero media query debe ser el del valor mayor.

````
@media (max-width: 800px) {
    body {
        background-color: black;
    }
}

@media (max-width: 600px) {
    body {
        background-color: #FFF;
    }
}
````

Aunque esto cambia cuando utilizamos el min-width, se recomiendo hacerlo de forma creciente, de menor a mayor valor.

````
@media (min-width: 600px) {
    body {
        background-color: black;
    }
}

@media (min-width: 800px) {
    body {
        background-color: #FFF;
    }
}
````

## Tecnicas de diseño adaptable (responsive design)
Adpatar nuestras paginas a cualquier dispositivo se ha vuelto impresindible en una epoca de diversos dispositivos con acceso a internte, para eso tenemos 2 tecnicas para adaptar a dispositivos, la primera mobile firts y la segunda desktop firts.

### Desktop Firts
La tecnica desktop firts se basa en maquetar primero el sitio pensando en un tamaño de escritorio, para despues adaptarlo a tamaños mas pequeños.

### Mobile Firts
La tecnica mobile firts se basa en maquetar primero el sitio pensando en dispositivos moviles, y posteriormente agregar media queries para adaptarlo a un tamaño mas grande. Esta es la mejor opcion debido a que es mas facil adaptar un diseño de mobile a desktop, que de desktop a mobile.