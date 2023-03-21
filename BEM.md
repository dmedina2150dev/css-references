# Metodologia BEM

## ¿Que es y para que sirve BEM?
BEM (Block Element Modifier) es una metodologia que nos proporciona una manera de nombrar nuestras clases en HTMl para posteriormente poder usarlo en CSS, BEM nos ayudarea a mantener nuestro codigo flexible, modular y sencillo. Sobre todo a lidiar con problemas de especificidad.

BEM significa Block(bloque) Element(elemento) Modifier(modificador), esto es debido a que todas las clases que escribimos se regiran por estar 3 partes.

### Block (Bloque)
Es una parte independiento en nuestro HTML, no necesita de otros elementos para existir. Por ejemplo, una galeria de imagenes o un menu.

Los bloques tienen el nombre de lo que representara, ejemplo "header, menu, galeria, section, footer"

````
<section class="galery">
    ...
</section>
````

### Element (Elemento)
Un elemento siempre estar dentro de un bloque, debido a que es parte de él y es dependiente del bloque, por ejemplo una imagen necesita una galeria de imagenes para existir, o un enlace necesita un menu para existir.

Los elementos tendran el nombre primero del bloque al que pertenece, dos guiones bajos y despues el nombre de lo que representara, ejemplo: "header__title, menu__item, galeria__img, footer__img".
````
<section class="galery">
    <img src="..." alt="" class="galery__img">
</section>
````

### Modifier (Modificador)
Los modificadores son usados en elementos o bloques, se usan para representar una caracteristica diferente que tendra el modificador o elemento.

Los modificadores tendran el nombre del bloque o del elemento, despues otra vez el nombre del elemento, dos guiones medios y la caracteristica diferente que tendra este bloque o elemento.

Ejemplo: "boton--active" "header--wave"

````
<button class="btn">Click</button>
<button class="btn btn--active">Click</button>
````