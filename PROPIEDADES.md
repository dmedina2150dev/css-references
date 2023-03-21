# PROPIEDADES CSS

### color
>Define el color del texto del contenedor o selector al que se le aplique la propiedad.

### font-size
>Define el tamaño de las fuentes (texto) del contenedor o selector al que se le aplique la propiedad.

### height
>Representa el alto que tendra el contenido del contenedor o selector al que se le aplica esta propiedad.

### width
>Representa el ancho que tendra el contenido del contenedor o selector al que se le aplica esta propiedad.

### background (Shorthand)
>Representa las propiedades del fondo del contenido o contenedor o selector al que se le aplica esta propiedad.

### border (Shorthand)
>Representa el border del contenido, contenedor o selector al que se le aplique esta propiedad.

### border-radius (Shorthand)
> Permite redondear las esquinas de los elementos o contenedores HTML. Esto nos permite generar diversos estilos entre formas levemente redondeadas, circulos o figuras ovaladas. Se puede utilizar valores de medidas como (px) o (%) y otras como (em), (rem), etc..
- border-top-left-radius
- border-top-right-radius
- border-bottom-right-radius
- border-bottom-left-radius

> Asi se usaria el ShortHand
- border-radius: top-left | top-right | bottom-right | bottom-left;
  
### box-shadow
> Nos permimte agregar sombra a los elementos o contendores, las sombras en CSS es la copia exacta del elemento, tanto en forma como en tamaño. Por defecto esta propiedad admite dos valores.

> El color de la sombra se toma del elemento, exactamente de la propiedad (color).

> Se pueden crear mas de una sombra, separandolas por (,)

````
box-shadow: offset-x offset-y blur spread color;

/*Varias sombras*/
box-shadow: 
5px 10px rgba(0, 0, 0, 0.3),
100px 250px 10px,
250px 480px plum;
````

- **offset-x**: Permite el movimiento de la sombra, de derecha e izquierda. Si colocamos el valor en positivo se mueve a la derecha, si son negativos a la izquierda.
- **offset-y**: Permite el movimiento de la sombra, de arriba y abajo. Si colocamos el valor en positivo se mueve a hacia abajo, si son negativos hacia arriba.
- **blur**: Esto permite difuminar la sombra. 
- **spread**: Esta hace referencia a la manera en como se esparcira la sombra
