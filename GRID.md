# GRID
CSS Grid Layout es un sistema de cuadriculas, el cual es el sistema mas poderoso en CSS para diseñar sitios web. Esto es gracias a su sistema bi-dimensional, lo que significa que utiliza tanto columnas (columns) que son verticales, como filas (rows) que son horizontales de izquierda a derecha. Diferenciandolo de Flexbox que solo podiamos manipular al main axis.

![](https://github.com/dmedina2150dev/css-references/blob/main/14-grid/img/grid1.png)
 
Por eso se llama grid o cuadricula, porque se utilizan filas y columnas creando una cudaricula. Cada fila y columna estar formada por dos lineas (Grid-lines). Cuando estas lineas y columnas se interceptan forman una cuadricula. 

Tanto las filas como las columnas tiene una linea de inicio y una linea final. Es decir que por cada fila o columna que tengamos hay una linea extra.

![](https://github.com/dmedina2150dev/css-references/blob/main/14-grid/img/grid2.png)

Una vez que se crea la grid que es la suma de filas y columnas, se crean celdas que es la parte más pequeña en Grid y al principio todos los elementos que esten dentro de la grid ocuparan una celda por defecto. 

![](https://github.com/dmedina2150dev/css-references/blob/main/14-grid/img/grid3.png)

Para empezar a entender mejor GRID, se debe ver como una cuadricula compuesta de muchas celdas, al principio los grid-items ocuparan celda por cada grid-item.


![](https://github.com/dmedina2150dev/css-references/blob/main/14-grid/img/grid4.png)

> Lineas verticales (column grid lines) 
> Lineas horizontales (row grid lines)

Nosotros podemos definir areas en ela grid, podemos elegir cierto numero de celdas y darles un nombre, para posteriormente posicionar a los elementos en base a este nombre que le dimos al area. 

Las areas siempre tienen que ser rectangulares o cuadradas, lo minimo para que exista un area debe de haber una celda.

![](https://github.com/dmedina2150dev/css-references/blob/main/14-grid/img/grid5.png)


**NOTAS**
> Usando display: grid; por defecto los elementos se estiran hasta cubrir el contenedor.

`````
.container {
    display: grid;

    width: 90%;
    height: 600px;    
}
`````

> grid-template-columns: Nos permite crear columnas. Como valor podemos utilizar cualquier unidad de medida. Si colocamos medidas del mismo tipo de unidad o diferente separadas con un espacio iremos creando columnas en la grid.

`````
.container {
    display: grid;

    grid-template-columns: 30% 50px 100px;

    width: 90%;
    height: 600px;
}
`````

> **NOTA** las filas se van creando automaticamente si no se definen aun.. Esto sucede porque la propiedad **grid-auto-rows** Tiene su valor por defecto que es **auto**.

`````
.container {
    display: grid;

    grid-template-columns: 30% 50px 100px;

    grid-auto-rows: auto;

    width: 90%;
    height: 600px;
}
`````

> grid-auto-rows: Define que todas las filas que se creen automaticamente van a tomar un espacio automatico. 

> grid-template-rows: Nos permite definir o crear las filas que queremos en nuestra grid. Se utiliza tal cual como la contraparte grid-template-columns. Si se utiliza con un solo valor, los demas filas se autogeneran con el grid-auto-rows en auto..
> 
`````
.container {
    display: grid;

    grid-template-rows: 100px 200px  20%;

    width: 90%;
    height: 600px;
}
`````

Pero crear las columnas y las filas de esta forma no es la mas recomendada o por decirlo de otro modo, existe una funcion de CSS Grid que nos ayuda a reducir las lineas de código.

> **repeat()** Esta funcion recibe dos parametros el primero es el valor del numero de veces que se repetira o se creara una columna o una fila, y el segundo valor hace referencia a la unidad que tendra cada una de las filas o columnas.

````
.container {
    width: 90%;
    height: 600px;
    
    display: grid;
 
    grid-template-columns: repeat(5, 20%);
    grid-template-rows: repeat(10, 10%);
}
````

En CSS grid, tambien tenemos una unidad de medida que se llama (fr) si se coloca (1fr) como medida de valor de una columna o fila, estamos diciendo que el espacio disponible se divida en fracciones. Ejemplo de 3 columnas de 1fr

````
.container {
    width: 90%;
    height: 600px;
    
    display: grid;
 
    grid-template-columns: 1fr 1fr 1fr;
    /*O tambien usando la funcion repeat()*/
    grid-template-columns: repeat(3, 1fr);
}
````
> **NOTA** este tipo de valor con fraccion es utilizado para evitar problemas de que sobren espacios cuando dividimos el espacio disponible para filas y columnas.

Tenemos tambien en CSS grid una propiedad que nos permite dar espaciado entre filas.

> row-gap: Esta propiedad permite dar un espaciado equitativo entre las filas creadas
````
.container {
    width: 90%;
    height: 600px;
    
    display: grid;

    grid-template-rows: repeat(3, 1fr);
    
     row-gap: 1em;
}
````

Y para dar espacio entre columnas tenemos.

> column-gap: Esta propiedad permite dar un espaciado equitativo entre las columnas creadas
````
.container {
    width: 90%;
    height: 600px;
    
    display: grid;

    grid-template-columns: repeat(3, 1fr);

    column-gap: 1.5em;
}
````

Para dar espacio entre columnas y filas al mismo tiempo tenemos.

> gap: Esta propiedad permite dar un espaciado equitativo entre las columnas y filas creadas al mismo tiempo cuando lo utilizamos con un solo valor, si colocamos dos valores el primero es para las filas y el segundo para las columnas.
````
.container {
    width: 90%;
    height: 600px;
    
    display: grid;

    grid-template-rows: repeat(3, 1fr);
    grid-template-columns: repeat(3, 1fr);

    gap: 10px; // Ambos

    gap: 10px 20px; // Filas Columnas
}
````

### Ubicar elementos o items dentro de la Grid
Para poder ubicar en cualquier lugar de la grid un elemento o item se puede utilizar la propiedad (grid-column) y tambien tenemos (grid-row).

> grid-column: Permite ubicar items en la grid entre las lineas que se generan de las columnas, recibe dos valores separados por (/) 

````
$ grid-column: linea-inicial / linea-final;
````

> grid-row: Permite ubicar items en la grid entre las lineas que se generan de las filas, recibe dos valores separados por (/) 

````
$ grid-row: linea-inicial / linea-final;
````

>**NOTA** Cuando el valor de linea-final es (-1) asi se agrande la grid terminara en el final, ya que eso es lo que indica el (-1).

````
 <section class="container">
    <div class="item item1">#1</div>
    <div class="item item2">#2</div>
    <div class="item item3">#3</div>
    <div class="item item4">#4</div>
</section>

.container {
    width: 90%;
    height: 600px;
    outline: 2px solid;
    margin: 40px auto;
    
    display: grid;

    grid-template-columns: repeat(5, 1fr);
    grid-template-rows: repeat(5, 1fr);
    
    gap: 10px;
}

.item {
    color: #FFF;
    font-size: 2em;
    display: flex;
    align-items: center;
    justify-content: center;
}

.item1 {
    background-color: steelblue; 
    grid-column: 1 / 4;
    grid-row: 1 / 3;
}
.item2 {
    background-color: deeppink;
    grid-column: 4 / 6;
    grid-row: 1 / 5;
}
.item3 {
    background-color: seagreen;
    grid-column: 1 / 4;
    grid-row: 3 / 5;
}
.item4 {
    background-color: brown;
    grid-column: 1 / -1;
    grid-row: 5 / -1;
}
````


Existe otra forma de ubicar los item entre las lineas de la grid, y es utilizando la propiedad (grid-template-areas) Y (grid-area), para esto se debe tener definidas las filas y las columnas que tendra la grid

> grid-template-areas: nos ayuda a crear una grid con espacios de nombre entre las celadas o lineas de nuestra grid. Para el siguiente ejemplo tenemos una grid de 5 x 5

````
.container {
    width: 90%;
    height: 600px;
    outline: 2px solid;
    margin: 40px auto;
    
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-template-rows: repeat(5, 1fr);
    gap: 10px;

    /*De esta forma definimos los espacios*/
    grid-template-areas:
    "elem1 elem1 elem1 elem2 elem2"
    "elem1 elem1 elem1 elem2 elem2"
    "elem3 elem3 elem3 elem2 elem2"
    "elem3 elem3 elem3 elem2 elem2"
    "elem4 elem4 elem4 elem4 elem4"
    ;
}

````

> grid-area: Esta propiedad nos ayuda a asignarle el area que deseamos que ocupe el elemento y esta se acomodara dependiendo del template de grid-template-areas.

````
.item4 {
    background-color: brown;
    grid-area: elem4;
}
````

Con esta facilidad igual podriamos cambiar la disposicion del template si lo necesitamos con un media query. Siguiendo con el ejemplo anterior en el media query se modifica el template para que el elemento 2 (elem2) ocupe toda la grid cuando la pantalla es mayor a 700px

````
@media (min-width:700px) {
    .container {
        grid-template-areas:
            "elem1 elem1 elem1 elem2 elem2"
            "elem1 elem1 elem1 elem2 elem2"
            "elem3 elem3 elem3 elem2 elem2"
            "elem3 elem3 elem3 elem2 elem2"
            "elem4 elem4 elem4 elem2 elem2"
        ;
    }
}
````

> **NOTA** Sirve como nota o tip, si queremos dejar alguna celda de la grid vacia, no podemos dejarle el nombre en el template sin nombre, en su lugar debemos cambiarlo por un punto.

````
@media (min-width:700px) {
    .container {
        grid-template-areas:
            "elem1 elem1 elem1 elem2 elem2"
            "elem1 elem1 elem1 elem2 elem2"
            "elem3 elem3 elem3 elem2 elem2"
            "elem3 elem3 elem3 elem2 elem2"
            "elem4 elem4 elem4 elem2 ."
        ;
    }
}
````


Tambien podemos crear filas y columnas dinamicamente, es decir que su tamaño cambie dependiendo del contexto. Para eso podemos utiliza la funcion repeat() y como primer parametro un valor definido **(auto-fit)** que nos permite crear columnas dimanicamente, se ajusta a diversos tamaños.

> Por ejemplo si tengo 900px de espacio disponible y 3 elementos de 300px solamente creara 3 filas porque solamente entrar 3 columnas de 300px. Si cambia el tamaño a 1200px entrarian 4 columnas. Eso es lo que hace auto-fit crea columnas dinamicamente.

Como segundo parametro la funcion **minmax()** el primer parametro es el valor minimos que deberia tener nuestro elemento y separado por (,) el segundo parametro que es el valor maximo.

````
.container {
    display: grid;

    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
}
````