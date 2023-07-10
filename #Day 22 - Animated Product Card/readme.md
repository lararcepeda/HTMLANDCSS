# Explicando un poquito.

Hay una pagina en que se puede ver como quedaria un efecto en neumorphism. Que se llama neumorphis.io

![imagen](https://i.pinimg.com/564x/66/11/f6/6611f6fa444611e0900428396f559ae4.jpg)

## El elemento <video>

El elemento < video > nos permite incrustar video fácilmente. Un ejemplo muy simple luce como lo siguiente:

```HTML
<video src="rabbit320.webm" controls>
  <p>Tu navegador no soporta HTML5 video. Aquí está el <a href="rabbit320.webm">enlace del video</a>.</p>
</video>
```

Las características a notar son:

- src
De la misma manera que para el elemento < img >, el atributo src (source) contiene una ruta al video que deseas incrustar. Funciona de la misma manera.

- controls
Los usuarios deben ser capaces de controlar la reproducción de video y audio (esto es especialmente crítico en personas que padecen epilepsia). Se debe utilizar el atributo controls para incluir la interfaz de control del browser, o construir la nuestra utilizando la JavaScript API apropiada. Como mínimo la interfaz debe incluir una manera de empezar y terminar la reproducción, y ajustar el volumen.

## El párrafo dentro de la etiqueta < video >

Se lo llama fallback content (contenido de reserva) — y será mostrado si el browser desde el que se está accediendo a la página no soporta el elemento < video >, permitiéndonos proveer un fallback para browsers más antiguos. Puede ser de la manera que se quiera; en este caso proporcionamos un link directo al archivo de video, por lo que el usuario puede al menos acceder de alguna manera, independientemente del browser que esté usando.

## Otras características de la etiqueta < video >

Hay varias otras características que puede incluir en un vídeo HTML5. Eche un vistazo a nuestro tercer ejemplo, a continuación.

```html
<video controls width="400" height="400"
       autoplay loop muted
       poster="poster.png">
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>Su navegador no soporta vídeo HTML5. Este es un <a href="rabbit320.mp4">enlace al vídeo</a> alternativo.</p>
</video>
```

Las nuevas características son:

- width y height
Puede controlar el tamanño con estos atributos o con CSS. En ambos casos, los vídeos mantienen su relación anchura - altura nativa. Si la relación de aspecto no se mantiene con los tamañis establecidos, el vídeo crecerá para rellenar el espacio horizontalmente y el el espacio sin rellenar sólo recibirá un color de fondo sólido de forma predeterminada.

- autoplay
Hace que el audio o el vídeo empiece a reproducirse de inmediato, mientras se carga el resto de la página. Le aconsejamos que no utilice vídeo (o audio) de reproducción automática en sus sitios, ya que los usuarios pueden encontralo molesto.

- loop
Hace que el vídeo (o audio) comience a reproducirse cada vez que finaliza.Esto puede en ocasiones resultar molesto, así que utilizalo solo si es realmente necesario.

- muted
Hace que los medios se reproduzcan con el sonido apagado de forma predeterminada.

- poster
La URL de una imagen que se mostrará antes de reproducir el vídeo. Está destinado a ser utilizado para una pantalla de presentación o pantalla publicitaria (miniatura del vídeo).

- preload
Se utiliza para almacenar en búfer archivos grandes; Puede tomar uno de estos tres valores:

"none" no almacena el archivo en el búfer
"auto" almacena el archivo multimedia
"metadata" almacena solo los metadatos del archivo
Puedes encontrar el ejemplo anterior disponible en reproducir en directo en Github (también vea el código fuente.) Tenga en cuenta que hemos incluido el atributo autoplay en la versión en vivo — Si el vídeo comienza a reproducirse tan pronto como se cargue la página no podrá ver la miniatura!

## El elemento < audio >

El elemento < audio > funciona exactamente de la misma forma que el elemento <video>, con algunas pequeñas diferencias como se describe a continuación. Un ejemplo típico podría ser así:

```js
<audio controls>
  <source src="viper.mp3" type="audio/mp3">
  <source src="viper.ogg" type="audio/ogg">
  <p>Su navegador no es compatible con audio HTML5. Aquí hay un <a href="viper.mp3">enlace al audio</a> en su lugar.</p>
</audio>
```

Esto ocupa menos espacio que un reproductor de video, ya que no hay un componente visual; solo necesita mostrar los controles para reproducir el audio. Otras diferencias con respecto al video HTML5 son las siguentes:

El elemento < audio > no soporta los atributos width/height — de nuevo, no hay un componente visual,por no que no hay nada a lo que asignar un width o height (ancho o alto).
Tampoco es compatible con el atributo poster — de nuevo , no hay componente visual.
Además de esto, < audio > admite las mismas características que <video> — revisa las secciones anteriores para obtener más información sobre ellas.

Reinicio de la reproducción multimedia
En cualquier momento, puede restablecer los medios al principio—incluyendo el proceso de selección de la mejor fuente de medios, si se especifica más de una usando < source > elementos—llamando al elemento load() (en-US) method:

```js
var mediaElem = document.getElementById("my-media-element");
mediaElem.load();
```

## Detección de la adición y eliminación de pistas

Puede monitorear las listas de pistas dentro de un elemento multimedia para detectar cuando se añaden o eliminan pistas del elemento multimedia. Por ejemplo, puede ver si se activa el evento addtrack en el objeto AudioTrackList (en-US) asociado (recuperado a través de HTMLMediaElement.audioTracks (en-US)) para saber cuándo se añaden pistas de audio al contenido multimedia:

```js
var mediaElem = document.querySelector("video");
mediaElem.audioTracks.onaddtrack = function(event) {
  audioTrackAdded(event.track);
}
```

Encontraras mas documentación acerca de esto en nuestra TrackEvent (en-US) documentación.

## Visualización de pistas de texto en vídeo

Ahora hablaremos de un concepto un poco más avanzado que es realmente útil conocer. Muchas personas no pueden o no quieren escuchar el contenido de audio/vídeo que encuentran en la Web, al menos en determinados momentos. Por ejemplo:

Muchas personas tienen deficiencias auditivas (más comúnmente conocidas como sordos o con dificultades auditivas), por lo que no pueden oír el audio.
Otras no pueden oír el audio porque se encuentran en ambientes ruidosos (como un bar abarrotado cuando se retransmite un partido deportivo) o porque no quieren molestar a los demás si están en un lugar tranquilo (como una biblioteca).
Las personas que no hablan el idioma del vídeo pueden querer una transcripción de texto o incluso una traducción que les ayude a entender el contenido multimedia.
¿No estaría bien poder ofrecer a estas personas una transcripción de las palabras que se pronuncian en el audio/vídeo? Pues bien, gracias al vídeo HTML5 se puede, con el formato WebVTT (en-US) y el elemento < track >.

Nota: "Transcribir" significa "escribir palabras habladas como texto". El texto resultante es una "transcripción".

WebVTT es un formato para escribir archivos de texto que contienen múltiples cadenas de texto junto con metadatos tales como en qué momento del vídeo desea que se muestre cada cadena de texto, e incluso información limitada de estilo/posicionamiento. Estas cadenas de texto se llaman cues, y se pueden mostrar diferentes tipos para diferentes propósitos, siendo los más comunes:

- subtítulos

Traducciones de material extranjero, para personas que no entienden las palabras pronunciadas en el audio.

- leyendas

transcripciones sincronizadas de diálogos o descripciones de sonidos significativos, para que las personas que no pueden oír el audio entiendan lo que está pasando.

- descripciones temporizadas

Texto para convertir en audio, al servicio de las personas con deficiencias visuales.

Un archivo WebVTT típico tendrá este aspecto:

WEBVTT

1
00:00:22.230 --> 00:00:24.606
Este es el primer subtítulo.

2
00:00:30.739 --> 00:00:34.074
Este es el segundo.

...
Para que esto se muestre junto con la reproducción multimedia HTML, es necesario:

## Guárdelo como archivo .vtt en un lugar adecuado.

Enlace el archivo .vtt con el elemento <track>. <track> debe colocarse dentro de <audio> o <video>, pero después de todos los elementos <source>. Utilice el atributo kind para especificar si las pistas son "subtítulos", " leyendas" o "descripciones". Además, utilice srclang para indicar al navegador en qué idioma ha escrito los subtítulos.
He aquí un ejemplo:

```html
<video controls>
    <source src="example.mp4" type="video/mp4">
    <source src="example.webm" type="video/webm">
    <track kind="subtitles" src="subtitles_en.vtt" srclang="en">
</video>
```

## Explicando el codigo de JavaScript.

La primera línea de código utiliza el método "querySelector()" para seleccionar el elemento HTML con la clase "color-option" y lo asigna a la variable "circle".

Luego, se agrega un event listener al elemento "circle" para el evento "click". Cuando se hace clic en el elemento, se ejecuta una función que toma el evento como argumento.

Dentro de la función, se utiliza la propiedad "target" del evento para seleccionar el elemento que se hizo clic. Si el elemento tiene la clase "circle", se ejecutan una serie de acciones.

Primero, se selecciona el elemento con la clase "active" dentro del elemento "circle" y se le quita la clase "active". Luego, se le agrega la clase "active" al elemento que se hizo clic.

A continuación, se selecciona el elemento de imagen que tiene la clase "active" dentro del elemento con la clase "main-images" y se le quita la clase "active". Finalmente, se selecciona el elemento de imagen que tiene una clase igual al ID del elemento que se hizo clic y se le agrega la clase "active".

En resumen, este código cambia la imagen que se muestra en la página cuando se hace clic en uno de los círculos de color.
