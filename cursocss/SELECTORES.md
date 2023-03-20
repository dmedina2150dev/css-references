# SELECTORES CSS

## ¿Qué es un selector?
Los selectores CSS son la primera parte de una regla CSS. Estos nos ayudan a definir que elementos del documento HTML seran modificados. Todos los elementos HTML que coincidad con el selector se veran afectados por los estilos que se declaren. 

## Tipos de selecctores

### Selector de tipo
El selector de tipo, o selector de nombre o tambien conocido como selector de etiqueta. Se conoce de esta forma porque selecciona el elemento HTML directo por el nombre de la etiqueta que queremos modificar.

No es buena practica utilizar en demacia este selector.

````
body {
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

h2 {
    color: crimson;
    font-size: 40px;
}
````

### Selector de clase
Es el selector mas usado, incluso existen metodologias para escribir clases de una mejor manera. El selector de clase selecciona los elementos por el nombre dentro del atributo (class) en las etiquetas HTML. 

Un elemento puede tener mas de una clase en su atributo (class).

> Para utilizar este selector se debe anteponer un (.) sobre el nombre de la clase

````
.peliculas {
    color: crimson;
}
.series {
    font-size: 40px;
}
````

### Selector de ID
El selector de ID selecciona los elementos por el nombre dentro del atributo (id) en las etiquetas HTML. No son los mas aconsejables de usar por el tema de especificidad y porque es de suponer que solo exista uno.

> Para utilizar este selector se debe anteponer un (#) sobre el nombre de la clase

````
#spidermanNoWayHome {
    color: crimson;
}
#temporada3 {
    font-size: 40px;
}
````

### Selector Universal
Permite seleccionar a todos los elementos en el documento HTML. El selector universal tiene una especificidad de 0, no cuenta tanto.

````
* {
    font-size: 16px;
}
````
> Nota: El selector universal viene implicito en el restro de reglas CSS. Ya que selecciona a todas las considencias del selector que estemos utilizando sea clase, ID, o de tipo. Es decir en cada selector viene un selector universal por defecto


````
*.peliculas {
    color: crimson;
}
````

### Selectores combinadores
Se llaman asi porque estos selectores combinan mas de un selector basico, permiten ser mas especificos sobre que elementos queremos seleccionar. Se ocupan mas de un selector

#### Combinador de desencientes
Este selector es representado por un espacio en blanco. Combina dos selectores donde el primero debe ser el ancestro del segundo. Es decir que el segundo elemento o selector debe estar dentro del primer elemento o selector.

````
<!-- CSS -->
ul .lista {
    text-decoration: underline;
}

O

.todo .lista {
    list-style: decimal;
}

<!-- HTML -->
<ul class="todo listas">
    <li class="lista primera">Programar</li>
    <ul class="sublista">
        <li class="lista">Javascritpt</li>
        <li class="lista">PHP</li>
    </ul>
    <li class="lista">Correr</li>
    <li class="lista">Suscribirme</li>
</ul>

<li class="lista">Estoy fuera del UL</li>
````
#### Combinador de hijos directos
Este combinador es similar al anterior, pero este se representa con el simbolo (mayor que >). Combina dos selectores donde el primero debe ser el padre directo del segundo.
````
<!-- CSS -->
.listas > .lista {
    list-style: upper-roman;
}

<!-- HTML -->
<ul class="todo listas">
    <li class="lista primera">Programar</li>
    <ul class="sublista">
        <li class="lista">Javascritpt</li>
        <li class="lista">PHP</li>
    </ul>
    <li class="lista">Correr</li>
    <li class="lista">Suscribirme</li>
</ul>

<li class="lista">Estoy fuera del UL</li>
````

> ESTOS COMBINADORES ANTERIORES AÑADEN MUCHA ESPECIFICIDAD, NO SON MUY RECOMENDABLES

#### Combinador de hermano adyacente
Estos combinadores son mas recomendables, ya que nos pueden ayudar a crear animaciones con CSS. Este combinador es representado por el simbolo de suma (+). Combina dos elementos o selector, donde el segundo selector debe ser hermano adyacente del primer selecor. 

Es decir debe ser el siguiente hermano del primer selector y solamente se selecciona a ese siguiente hermano.

````
<!-- CSS -->
.subtitulo + .parrafo{
    background-color: yellow;
    opacity: 0;
    height: 0;
    overflow: hidden;
    transition: 1s;
}

.parrafo {
    background-color: red;
}

.subtitulo:hover + .parrafo{
    height: 50px;
    opacity: 1;
}

<!-- HTML -->
<article>
    <h2 class="subtitulo">¿Qué es un registro de hábitos?</h2>

    <p class="parrafo">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam vero expedita voluptatum?</p>

    <p class="parrafo">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam vero expedita voluptatum?</p>
</article>
````

#### Combinador de hermanos generales
Este combinador es representado por el simbolo de (~) virgulilla. Combina dos selectores donde el segundo selector debe ser hermano siguiente al primer selector. Es similar al anterior pero este seleccionara los hermanos siguientes del primer selector.

````
<!-- CSS -->
.subtitulo ~ .parrafo {
    background-color: tomato;
}

<!-- HTML -->
<article>
    <p class="parrafo">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam vero expedita voluptatum?</p>

    <h2 class="subtitulo">¿Qué es un registro de hábitos?</h2>

    <p class="parrafo">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam vero expedita voluptatum?</p>

    <p class="parrafo">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam vero expedita voluptatum?</p>
    
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam vero expedita voluptatum?</p>
</article>
````

### Selectores de atributos
En css es posible seleccionar elementos HTML por los artibutos que estos elementos tengan. Y esto se logra colocando el nombre del atributo entre corchetes ([]). Tambien podemos utilizar caracteres especiles para filtrar el selector

````
[class] {
    background-color: yellow;
}

[type] {
    background-color: aqua;
}

[value] {
    display: block;
    width: 90%;
    margin-top: 20px;
}

[type="text"] {
    background-color: blue;
}
````
> Para filtrar el selector y encontrar algun caracter o palabra que buscamos etc.. Se utiliza la virgulilla (~) antes del igual.

````
[value~="cursocss.com"] {
    background-color: blue;
}
````

> Con el signo de acento circunflejo (^), este nos permite seleccion lo que contenga como prefijo (Que comience) el valor que indicamos luego del igual
````
[value^="Aquí"] {
    background-color: black;
    color: whitesmoke;
}
````

> Con el signo de ($), este todo lo contrario nos permite seleccion lo que contenga como sufijo (Que termine) el valor que indicamos luego del igual
````
[value$="cursocss.com"] {
    background-color: gray;
    color: whitesmoke;
}
````

> Con el signo de (*), es parecido al selector universal y se comporta casi de las misma forma. Sin importar donde se encuentre la palabra o si esta alterada si se encuentra se selecciona.
````
[value*="cursocss.com"] {
    background-color: gray;
    color: whitesmoke;
}
````
