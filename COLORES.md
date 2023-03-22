# Fondos y Colores en CSS

## Color
La propiedad (color) de CSS hace referencia o nos permite asignar el color que queremos que tenga el texto. 

Existen muchas formas de asignar color en CSS:

### Palabra clave
Escribiendo el nombre del color en ingles, este debe existir en los colores permitidos por el navegador.

REF: [https://developer.mozilla.org/es/docs/Web/CSS/color_value]

````
.title {
    color: red;
}
.title {
    color: saddlebrown;
}
````

### RGB
Es un valor de tipo funcion que nos permite definir un color, en base a 3 colores primarios, (rojo, verde, azul). El minimo de valores que recibe son 3 separados por (,).

Los valores permitidos para cada parametro es de 0 - 255. 

En este valor tipo funcion existe un 4 parametro que por defecto viene en (1), lo que representa la opacidad del color. Se le conoce tambien como (alpha).

````
/* rgb(red, green, blue) */
.title {
    color: rgb(0, 0, 0);
}
.title {
    color: rgb(24, 104, 87);
}

/* rgb(red, green, blue, alpha) */
.title {
    color: rgb(252, 240, 50, .5);
}


````

### Hexadecimal
Se basa en el sistema de numeracion hexadecimal. Este de obtiene anteponiendo una almoadilla o gato (#) antes del numero hexadecimal. Que parte desde el cero hasta la letra (F). 0 - F. Por ejemplo (#FF0000), Como se ve el numero se componen de 6 caracteres, aunque se puede representar con 3 caracteres, de esta forma (#F00), serian el mismo color.

En el ejemplo anterior con 6 caracteres los 2 primeros despues de la almoadilla(#) representan al color (rojo), los siguientes dos al color (verde), y los ultimos dos al color (azul). Equivalen a lo mismo con tres caracteres representan uno rojo, uno verde y uno azul.. En ese orden.

Tambien se puede agregar la opacidad con dos caracteres adicionals.

````
.title {
    font-size: 42px;
    color: #fcee32;
}

/*Opacidad*/
.title {
    font-size: 42px;
    color: #fcee328d;
}
````

### HSL
Es otro valor tipo funcion, es muy similar a (RGB), porque igual recibe 3 parametros. Pero a diferencia de RGB cada valor representa algo distinto a un color.

**El primer valor es (hue)** conocido como tono o matiz del color. Estos valores estan representados en el (Circulo Cromatico) y se representan desde el 0 al 360 grados.

**El segundo valor (saturation)** esta se representa con porcentajes que van del 0 al 100%. Cuando esta al 100% el color esta totalmente saturado, cuando esta al 0% esta insaturado.

**El tercer valor (lightness)** o luminosidad, de igual manera se utilizan porcentajes del 0 al 100%. El 100% representa una luminosidad completamente blanca, y al contrario 0% una luminosidad totalmente negra. Es recomendado utilizarla al 50%.

Al igual que RGB, HSL tambien permite un 4 valor que de igual forma representa a (alpha) de 0 a 1 (.1,.2,.3 ... ) y asi sucecibamente hasta el 1 


````
/** hsl(hue, saturation, lightness) **/
.title {
    font-size: 42px;
    color: hsl(210, 100%, 50%);
}

/** hsl(hue, saturation, lightness, alpha) **/
.title {
    font-size: 42px;
    color: hsl(310, 60%, 50%, .8);
}
````
