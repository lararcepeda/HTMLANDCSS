# Explicando un poquito. 

Paginas importantes para acordarnos para nuestros proyectos. 
- Animista: animaciones personalizables. 
- Cattocss: te da el css preparado.
- Animate.css: importa la libreria y usa sus clases facilmente. 
- Hover.css: perfecto para botones. 
- Animatopy: colección inmensa.
- 

![imagen](https://i.pinimg.com/564x/59/c3/1f/59c31ff9738022a8428d97cba0fce552.jpg)

## ¿Qué hay que escribir exactamente en el atributo alt?

- Decoración. Para las imágenes decorativas deberían utilizarse imágenes de fondo CSS. Pero si es inevitable usar HTML, la mejor forma de hacerlo es con alt="". Si la imagen no es parte del contenido, el lector de pantalla no debería malgastar el tiempo en leerla.
- Contenido. Si tu imagen proporciona información significativa, proporciona la misma información en un texto alternativo (alt) breve. O mejor aún, en el texto principal que todos pueden ver. No escribas texto alternativo redundante. ¿Acaso no resultaría molesto para un usuario con visión ordinaria si todos los párrafos se escribieran dos veces en el contenido principal? Si la imagen se describe en el cuerpo principal del texto de modo adecuado, puedes simplemente usar alt="".
- Enlace. Al poner una imagen dentro de una etiqueta < a > para convertirla en un enlace, aun debes proporcionar texto de enlace accesible. En tal caso podrías escribirlo dentro del mismo elemento < a >, o dentro del atributo alt de la imagen. Lo que mejor funcione en tu caso.
- Texto. No deberías poner tu texto en imágenes. Si tu título de encabezado principal necesita, por ejemplo, un sombreado paralelo, usa CSS para ello en vez de poner el texto en una imagen. Pero, si realmente no puedes evitarlo, deberías proporcionar el texto en el atributo alt.

## Anchura y altura

Puedes usar los atributos ancho (width) y alto (height) para especificar la anchura y altura de tu imagen. Puedes encontrar el ancho y el alto de tu imagen de diversas maneras. Por ejemplo, en Mac puedes usar Cmd + I para mostrar información del archivo de imagen. Volviendo a nuestro ejemplo, podríamos hacer esto:

```html
<img src="images/dinosaur.jpg"
     alt="La cabeza y el torso de un esqueleto de dinosaurio;
           tiene una cabeza grande con dientes largos y afilados"
     width="400"
     height="341">
```

## Título de imágenes

Al igual que con los enlaces, también puedes añadir atributos title a las imágenes para proporcionar más información de ayuda si es necesario. En nuestro ejemplo, podríamos hacer esto:

```html
<img src="images/dinosaur.jpg"
     alt="La cabeza y el torso de un esqueleto de dinosaurio;
           tiene una cabeza grande con dientes largos y afilados"
     width="400"
     height="341"
     title="Exposición de un T-Rex en el museo de la Universidad de Manchester.">
```

## Comentar imágenes con figure y figcaption
Hay varias formas en que puedes añadir un pie a tu imagen. Por ejemplo, nada te impediría hacer esto:

```html
<div class="figure">
  <img src="images/dinosaur.jpg"
       alt="La cabeza y el torso de un esqueleto de dinosaurio;
           tiene una cabeza grande con dientes largos y afilados"
       width="400"
       height="341">

  <p>Exposición de un T-Rex en el museo de la Universidad de Manchester.</p>
</div>
```

Esto está bien. Incluye el contenido que se necesita y es muy personalizable con CSS. Pero hay un problema: no hay nada que vincule semánticamente la imagen con su título, lo que puede causar problemas a los lectores de pantalla. Por ejemplo, cuando hay 50 imágenes y leyendas, ¿qué leyenda se corresponde con cada imagen?

Una solución mejor es utilizar los elementos HTML5 < figure > y < figcaption >. Estos se crearon exactamente para este propósito: proporcionar un contenedor semántico para las figuras y vincular claramente la figura con el pie. Nuestro ejemplo anterior, podría reescribirse así:

```html
<figure>
  <img src="images/dinosaur.jpg"
        alt="La cabeza y el torso de un esqueleto de dinosaurio;
            tiene una cabeza grande con dientes largos y afilados" width="400"
        height="341">

  <figcaption>Exposición de un T-Rex en el museo de la Universidad de Manchester.</figcaption>
</figure>
```

El elemento < figcaption > dice al navegador, o a alguna tecnología de apoyo, que el texto que contiene describe la imagen que está contenida en el elemento < figure >.


## Explicando el JavaScript. 

Voy a explicar el archivo que se llama landingp.js

Los primeros dos bloques de código están creando dos nuevas instancias de Swiper. La primera instancia, llamada "swiper", está apuntando a un elemento con una clase de "bg-slider-thumbs", mientras que la segunda instancia, llamada "swiper2", está apuntando a un elemento con una clase de "bg-slider". Ambas instancias tienen la opción "loop" establecida en true, lo que significa que se repetirán infinitamente.

La opción "slidesPerView" está establecida en 0, lo que significa que el número de diapositivas visibles al mismo tiempo se determinará automáticamente en función del ancho del elemento contenedor.

La segunda instancia, "swiper2", tiene una opción adicional llamada "thumbs", que se utiliza para especificar que la instancia "swiper" se debe utilizar como navegación para la instancia "swiper2".

El siguiente bloque de código agrega un event listener al objeto "window" para el evento "scroll". Cuando el usuario se desplaza, comprueba si la posición de desplazamiento es mayor que 0 y agrega o elimina la clase "sticky" del elemento "header" en consecuencia. Esta es una técnica común utilizada para crear un encabezado pegajoso.

Finalmente, hay dos event listeners para el botón de menú y el botón de cerrar. Cuando se hace clic en el botón de menú, agrega la clase "active" al elemento "navigation", lo que revelará el menú de navegación. Por el contrario, cuando se hace clic en el botón de cerrar, elimina la clase "active" del elemento "navigation", lo que ocultará el menú de navegación.
