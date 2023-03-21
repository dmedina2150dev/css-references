# BOX MODEL
Todo los elementos en CSS son tratados como Cajas o rectangulos o en su defecto cuadrados, estas cajas tienen propiedades con las cuales podremos cambiar el tamaño de los elementos, su posicionamiento y mejorar su diseño. Todos los elementos en el HTML seran tratados como cajas.

El Box model es la manera o la estructura que compone una caja o un elemento en CSS, el cual se divide en capas.

## Propiedades del Box Model
Las propiedades que nos ayudan a modificar el diseño de las cajas en CSS estan compuestos por el Content(Contenido), Padding(Relleno), Border(Borde), Margin(Margen). Van en ese orden de adentro hacia afuera de la caja.

Las primeras 3 capas modifican el tamaño de la caja.

### Propiedades por Capa
**Content(Contenido)**
- width
- max-width
- min-width
- height
- max-height
- min-height
**Padding(Relleno)** 
- padding (Shorthand)
- padding-top
- padding-right
- padding-bottom
- padding-left
**Border(Borde)** 
- border (Shorthand)
- border-top  (Shorthand)
- border-right (Shorthand)
- border-bottom (Shorthand)
- border-left (Shorthand)
- border-width (Shorthand)
- border-top-width
- border-right-width
- border-bottom-width
- border-left-width
- border-style (Shorthand)
- border-top-style
- border-right-style
- border-bottom-style
- border-left-style
- border-color (Shorthand)
- border-top-color
- border-right-color
- border-bottom-color
- border-left-color

La utlima capa (Margin) permite establecer un margen o una separación en 4 direcciones del elemento. Esta es la unica capa del Box Model que no afecta el tamaño de la caja.
**Margin(Margen)** 
- margin
- margin-top
- margin-right
- margin-bottom
- margin-left

> **Nota:** El color del borde por defecto es del color del texto.

> **Nota:** Significa que son propiedades abreviadas. Las propiedades abreviadas son propiedades CSS que le permiten establecer los valores de varias otras propiedades CSS simultáneamente. Usando una propiedad abreviada, puede escribir hojas de estilo más concisas (y a menudo más legibles), ahorrando tiempo y energía.

> **Nota:** En los margin el valor (auto) de la propiedad solo funciona de forma horizontal.. Aunque existen execepciones. 

> **Nota:** Y solo podemos usar margin con su valor (auto) cuando se cumplen dos condiciones. Cuando el elemento tiene un display block y cuando el elemento tiene un width definido.

## Colapso de margenes
Es un tema sumamente importante, es un comportamiento que sucede cuando dos margenes se combinan y se vuelven uno solo, esto solo pasa con los margenes verticales. Lo que sucede es que los margenes se fucionaran, no se sumaran, y predominara el margen mayor.
````
<main class="main">
        <h1 class="main__title">Hola Mundo</h1>
</main>
<footer class="footer">
    <h2 class="footer__title">Footer</h2>
</footer>


.main {
    background-color: steelblue;
    color: white;
    margin-bottom: 100px;
}

.footer {
    background-color: slateblue;
    color: white;
    margin-top: 50px;
}
````

El mas peligros es el colapso de los elementos hijos, ya que es muy dificil de persivir... Cuando pasa esto podemos solucionarlo agregando un pequeño padding al padre.

## Box Sizing
Box Sizing es la propiedad de CSS que permite modificar como afectan el padding y el border a los elementos HTML. Por defecto el valor de (box-sizing) es (content-box).

El problema de que esta propiedad se mantenga con su valor por defecto es que si por ejemplo tenemos un (card) que tiene definido un width y un height de 200px, mas un padding de 20px y border de 5px. El tamaño final de esta (card) sera de 250px. Esto muchas veces ocaciona que se distorcione el diseño y no entendamos el porque esta descuadrado.

Para solventar este problema y que el contendor mida lo que nosotros indicamos en el width y el height cambiamos el valor de la propiedad (box-sizing) a (border-box). Pero como todos los elementos vienen con esa propiedad por defecto en (content-box), lo asignamos en el selector universal. Asi si necesita de casualidad volverlo a (content-box) lo hariamos solo en el elemento que necesitamos.
````
* {
    box-sizing: border-box;
}
````