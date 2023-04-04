# CURSO CSS

## ¿Qué es y para qué sirve CSS?
CSS (Cascading Style Sheets) es un lenguaje de estilos en cascada, este lenguaje nos permite darle estilos a nuestro código HTML por medio de una regla de estilos, que involucran lo siguiente (selector, propiedad y valor). En pocas palabras, servirá para darle estilos a nuestro código HTML.

````
elemento {
    propiedad: valor;
}
````

## Cómo funciona CSS
Extrapolaremos con un ejemplo de un cuadrado, este cuadrado tiene un borde negro, si queremos darle estilos a esté cuadrado basados en la definición anterior, sería algo como lo siguiente:

````
cuadrado {
    fondo: negro;
    borde: azul;
}
````
> Se define el selector. En este ejemplo es [cuadrado]
> Se abre llaves, dentro se definen las propiedades.
> Nota cada propiedad siempre debe terminar con (;) y luego definir la siguiente propiedad.

## ¿Cuál es la estructura de CSS?
CSS es muy sencillo, trabaja con bloques de estilos que definen a que elementos se les aplicarán los estilos de dicho bloque. Esto se hace con un selector, propiedad y valor.

````
selector {
    propiedad: valor;
    propiedad: valor;
}
````

## Formas de añadir CSS a un archivo HTML

#### En linea
Se le aplican los estilos directo al elemento HTML, utilizando la propiedad (style) que viene disponible para todos elemento HTML.
````
<div style="color: red;">Hola Mundo</div>
````
**Desventaja**
> Si necesitas replicar el mísmo estito en otro elemento o contenedor se debe repetir en cada uno de ellos. Ademas actualmente es una mala practica.
**Ventaja**
> La especificidad. Es que tiene mayor preferencia a la hora de que el navegador aplica los estilos.

#### Interno
Utilizando la etiqueta HTML (<style></style>) esta va dentro del archivo HTML. Aunque se puede insertar o declarar dentro del <body>, lo más recomendado al usar esta tecnica es dentro del <head>

`````
<head>
    <style>
        selector {
            propiedad: valor;
        }
    </style>
</head>
`````
**Desventaja** (Opinion personal)
> Estilos solo disponibles para ese archivo HTML

**Ventaja**
> Poder replicar estilos en diferentes elementos HTML, donde los necesitemos.

#### Externo
Creamos un archivo, en algún directorio del proyecto al que este tenga acceso. Se declaran todos los estilos CSS. Y con la etiqueta <link> los enlazamos a los archivos HTML donde lo necesitemos. Esta etuqueta tiene un atributo [rel="stylesheet"] que simboliza la relación que tendra con el archivo. Y otro atributo [href=".../archivo.css"] donde indicaremos la ruta donde se encuentra el archivo.

````
<link rel="stylesheet" href="./archivo.css">
````

## Referenciar un elemento HTML con una clase CSS

````
// HTML
<div class="cuadrado">Hola Mundo</div>

// CSS - archivo
.cuadrado {
    height: 10cm;
    width: 10cm;
    background: steelblue;
}

````

## Cascada
Es una caracteristica de CSS, es la forma en la que se determina que selectores aplicaran los estilos, en caso de que exista más de un selector que cambie los estilos de un mismo elemento HTML.

````
h1 {
    color: royalblue;
    font-family: Arial, Helvetica, sans-serif;
}

/* Este predomina al anterior */
h1 {
    color: crimson;
    font-family: cursive;
}

/* Este predomina al anterior */
h1 {
    color: greenyellow;
    color: black;
}
````
> Se aplicara al elemento HTML el ultimo estilo declarado en la hoja de estilos.

> LA CASCADA ES EL SEGUNDO METODO QUE UTILIZA CSS PARA DETERMINAR QUE ESTILOS SE APLICARAN A LOS ELEMENTOS, EN CASO DE EXISTIR MAS DE UN SELECTOR PARA EL MISMO ELEMENTO.

> EL PRIMER METODO ES LA ESPECIFICIDAD


## Especificidad CSS
Es el metodo primordial que define que estilos se aplicaran, tiene mayor importancia que la cascada. La especificidad es el valor que se le da a los selectores en CSS. Cada selector tiene un valor diferente a otro, El selector con mayor especificidad es el selector del cual se mostraran los estilos.

### Valores de la especificidad

### Especificidad (1)
> Los selectores de tipo y pseudoelementos son los selectores que tienen una especificidad de (1), es el selector con menos especificidad.

### Especificidad (10)
> Los selectores de clase, atributo y pseudoclases son los selectores que tienen una especificidad de (10)

### Especificidad (100)
> Los selectores de id son los selectores que tienen una especificidad de (100)


> JUNTAR SELECTORES DE TIPO Y DE CLASE SUMA LOS VALORES DE ESPECIFICIDAD.
> EN VSCODE PASAS EL MOUSE SOBRE EL SELECTOR Y YE DICE QUE ESPECIFICIDAD TIENE

````
/* Especificidad (10) */
.title {
    color: pink;
}
/* Especificidad (1) */
h1 {
    color: red;
}

/* Especificidad (11) */
h1.title {
    color: black;
}
````

> Aunque es una mala practica existe un flag o un comodin que le podemos añadir a las propiedades que rompe la especificidad. (!important), no se recomienda utilizarlo porque puede causar problemas a largo plazo en proyectos mas grandes.
`````
h1 {
    color: crimson!important;
}
`````


## Herencia CSS

Como dice la palabra nos permite heredar estilos, de los elementos padres. Oh dicho de otra forma es la caracteristica de CSS que permite heredarle estilos a los hijos de un contenedor.

Tambien cabe aclarar que no todos los estilos son heredados por los hijos. Esto se puede ver al final del inspector de codigo del navegador.

Se debe estar al pendiente, ya que esto nos serviria para reducir el codigo CSS, pero tambien podria causar problemas. Se debe estar muy pendiente de esto.

> Para los estilos que no se hereden por defecto, pero aun asi los queremos utilizar podemos user como (valor) de la propiedad la palabra (inherit).

````
<body>
    <h1 class="title" id="title">Hola, soy un titulo</h1>
</body>

body {
    border: 3px solid orange;
    font-family: sans-serif;
    color: steelblue;
}

.title {
    border: inherit;
}
````
En el ejemplo anterior si inspeccionas en el navegador se vera como el (h1) hereda por defecto de (body) los estilos del color y la fuente, no asi el (border), utilizando el valor explicado podriamos usar esa propiedad heredada.


## Tipos de elementos en CSS
En CSS y HTML existen dos tipos de cajas o elementos. Las cajas o elementos en Bloque y las cajas o elemento en lines.

### Cajas en bloque
Estas por defecto tienen como valor de la propiedad (display) en (block). 

Caracteristicas para identificar cajas en bloque, por sus atributos por defecto, ya que estos pueden ser modificados:

- Generan un saldo de linea, debido a que toma el 100% de su contenedor.
- Pueden utilizar todas las propiedades del Box Model (Padding, width, border, height)

### Cajas en linea

Estas por defecto tienen como valor de la propiedad (display) en (inline).

Caracteristicas para identificar cajas en linea, por sus atributos por defecto, ya que estos pueden ser modificados:

- Se toman con texto. Y no generan salto de linea.
- Ocupan solamente el espacio de su contenido.
- Y no se le pueden aplicar propiedades del box model.
- Se puede modificar.

> **Nota**: Existe un valor para la propiedad (display) que es un ibrido entre (block) e (inline), que permite que los elementos sigan siendo en linea, pero se le puedan aplicar las propiedades del box model. Y es (inline-block)


## Unidades de medida
En CSS tenemos dos tipos de unidades de medida.

### Absolutas
Se llama de esta forma porque tiene un valor definido y ese valor no depende de nada más. Siempre sera el mismo por lo que nunca va a cambiar. Entre estas tenemos los pixeles (px), los centimetros (cm), los puntos (pt) y tambien los milimeros (mm).

````
.title {
    font-size: 50px;
}
.title {
    font-size: 50cm;
}
.title {
    font-size: 50pt;
}
.title {
    font-size: 50mm;
}
````

### De longitud relativa
Se llaman de esta forma porque su tamaño depende de algo externo a ellas. Significa que ese valor puede cambiar dependiendo el contexto. 

Entre ellas tenemos la unidad (rem) esta es relativa al tamaño de la fuente o font-size de la raiz del documento, se puede visualizar en el selector (html) y por defecto 1rem es igual a 16px. Puede llegar a variar por el tamaño de fuente o letra que agreges en el navegador en sus configuraciones.

````
/** 1rem = 20px **/
.title {
    font-size: 3rem;
}
````

Tambien tenemos la unidad (em), la diferencia con (rem) es que rem es relativo al tamaño de la fuente del navegador y (em) es relativo al tamaño de fuente del padre o de un ansestro superior que tenga declarado un font-size. Pero para propiedades que que no sean font-size, como width igual toma el valor relativo del padre mas cercano, pero si el selector donde esta declarado tiene un font-size declarado el valor relativo lo toma de este.

````
.container-child {
    font-size: 10px;
}

/** 1em = 10px **/
.title {
    font-size: 3em; /** 10*3 = 30px **/

    /** 30*5 = 150px **/
    width: 5em;
}
````

### Las viewport
Estas unidades son relativas al viewport del navegador. El viewport es el area visible que podemos observar en el navegador. Estas se utilizan anteponiendo la (v) y luego la medida sea width(vw) o heigth(vh). Tenemos disponible valores desde 0 a 100.

````
.container {

    background-color: aquamarine;
    width: 80vw;
    height: 80vh;
}
````

### Los porcentajes
Son relativos al tamaño del padre del elemento al que estamos dando el porcentaje (%). Que por defecto todos los elementos en bloque tienen un width de 100%.

Pasa algo parecido con el el height, si el padre del elemento no tiene definido un height este no funcionara.
````
.container-child {
    width: 50%;
    background-color: black;
    color: antiquewhite;
}
````
