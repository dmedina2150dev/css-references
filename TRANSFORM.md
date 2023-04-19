# TRANSFORMACIONES
La propiedad (transform) nos permiten crear transformaciones en CSS. Tales como rotar, escalar, transladar y cesgar un elemento. 

Para esto usamos esta propiedad (transform) con distintos metodos CSS:

````
.element {
    margin: 60px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    transform: /**metodo**/;
}
````

## Metodo Translate
Permite trasladar un elemento por medio de coordenadas (X) y coordenadas (Y)

Si le colocamos un solo valor positivo transladara el elemento hacia la derecha.

````
.element {
    width: 200px;
    height: 200px;
    background-color: tomato;

    transform: translate(100px);
}
````

Si le colocamos un solo valor negativo transladara el elemento hacia la izquierda.

````
.element {
    width: 200px;
    height: 200px;
    background-color: tomato;

    transform: translate(-100px);
}
````

**NOTA: Aunque el funcionamiento es parecido al uso de (position:relative) y las propiedades offset (top, left, bottom, right), el uso de (translate) se recomienda cuando creamos animaciones, debido a que utilizar estas propiedades offset en animaciones consumen más recursos**

Debido a lo anterior la propiedad (transform) con su valor (translate) se usa cuando realizamos animaciones o transiciones.

Y (translate) el el [shorthand](https://developer.mozilla.org/es/docs/Web/CSS/Shorthand_properties) para (translateX), (translateY). Como otros shorthand en CSS si utilizamos (translate) con dos valores el primero se usa como (translateX) y el segundo para (translateY).

````
.element {
    width: 200px;
    height: 200px;
    background-color: tomato;

    transform: translate(100px, 40px);
}
````

**NOTA: Tambien se puede utilizar otras unidades con este metodo**

O podriamos utilizar ambos valores (translateX) y (translateY) en la misma propiedad (transform).

````
.element {
    width: 200px;
    height: 200px;
    background-color: tomato;

    transform: translateX(200px) translateY(100px);
}
````


## Metodo rotate
Este metodo nos sirve para rotar elementos, con este metodo usamos valores angulares. Tenemos grados que van de (0 a 360 los cuales se indican con **(deg)**), tenemos los [radianes](https://es.khanacademy.org/computing/computer-programming/programming-natural-simulations/programming-angular-movement/a/angles-and-units#:~:text=Un%20radi%C3%A1n%20es%20una%20unidad,PI%2F2%20radianes%2C%20etc.) que van de (0 a 400 y los indicamos con **(grad)**), tambien radiales que van de (0 a 6.28319 y los indicamos con **(rad)**) y tenemos vueltas que van de (0 a 1 vuelta y se indican con **(turn)**).

````
.element {
    margin: 60px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    transition: .5s;/* Recordando que (transform) es utilizado en animaciones o transiciones */
}

.element:hover {
    transform: rotate(90deg);
}
.element:hover {
    transform: rotate(200grad);
}
.element:hover {
    transform: rotate(2rad);
}
.element:hover {
    transform: rotate(1turn);
}
````

## Metodo Scale
Permite escalar un elemento, agrandar o disminuir su tamaño aceptando valores positivos, negativos y decimales. Es decir no podriamos utilizar valores de las unidades como (px, %, em o rem). Por defecto el valor de (scale) es (1) que indica que no se va a incrementar. (scale) tambien es un shorthand para (scaleX) y (scaleY). 

Funcion multiplica el número indicado por el tamaño del alto o el ancho dependendiendo de el (scale) usado.

````
.element {
    margin: 60px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    transition: .5s;/* Recordando que (transform) es utilizado en animaciones o transiciones */
}

.element:hover {
    transform: scaleX(2);
    /* 
        Significa que  multiplicara
        200*2 = 400
    */
}
.element:hover {
    transform: scaleX(1.5);
    /* 
        Significa que  multiplicara
        200*1.5 = 300
    */
}

````

El caso contrario para disminuir el tamaño o para valores negativos, o mejor dicho valores mas bajos que el (1), lo que hara sera dividir el ancho o el alto por el número.

````
.element {
    margin: 60px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    transition: .5s;/* Recordando que (transform) es utilizado en animaciones o transiciones */
}

.element:hover {
    transform: scaleX(2);
    /* 
        Significa que  divide
        200*2 = 400
    */
}
.element:hover {
    transform: scaleX(1.5);
    /* 
        Significa que  divide
        200*1.5 = 300
    */
}

````

## Metodo skew
Este metodo nos permite sesgar(Cortar o partir una cosa en diagonal) un elemento. Y al igual que la propiedad (rotate) acepta valores angulares. Tenemos grados que van de (0 a 360 los cuales se indican con **(deg)**), tenemos los [radianes](https://es.khanacademy.org/computing/computer-programming/programming-natural-simulations/programming-angular-movement/a/angles-and-units#:~:text=Un%20radi%C3%A1n%20es%20una%20unidad,PI%2F2%20radianes%2C%20etc.) que van de (0 a 400 y los indicamos con **(grad)**), tambien radiales que van de (0 a 6.28319 y los indicamos con **(rad)**) y tenemos vueltas que van de (0 a 1 vuelta y se indican con **(turn)**).

**NOTA: POR RECOMENDACIÓN DE MDN EL METODO (skew) YA NO DEBERIA USARSE, EN SU LUGAR DEBEMOS UTILIZAR LAS PROPIEDADES POR EJE (skewX) Y (skewY)**

````
.element {
    margin: 60px;
    width: 200px;
    height: 200px;
    background-color: tomato;

    transition: .5s;
}

.element:hover {
    transform: skewX(10deg);
}
.element:hover {
    transform: skewY(30deg);
}
.element:hover {
    transform: skewX(10deg) skewY(30deg);
}

````


***COMODIN***
> Existe una propiedad llamada **(transform-origin)** con la cual podemos indicar desde donde queremos que empiece la transformacion de (transform).

````
.element {
    margin: 60px;
    width: 200px;
    height: 200px;
    background-color: tomato;
    
    transition: .5s;
}

.element:hover {
    transform: scale(1.6);
    
    transform-origin: left;
}
````


> Todas las propiedades que se mencionan se pueden utilizar juntas en el mismo (transform), No es posible declarar varios (transform) en un mismo selector, ya que estos se solaparian por que esta propiedad respeta la cascada de CSS.

````
.element {
    margin: 60px;
    width: 200px;
    height: 200px;
    background-color: tomato;
    
    transition: .5s;
}

.element:hover {
    transform: scale(1.6) rotate(20deg) skewX(10deg) skewY(30deg);
}
````

**NOTA: El orden de como colocamos los metodos afecta el resultado de la animacion o transcion**



