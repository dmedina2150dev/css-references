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
