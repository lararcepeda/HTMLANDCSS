# HTML

![imagen1](https://64.media.tumblr.com/55de8fd6e52bf27f996a93aa1c24f8ef/625a9ef2916d3807-9d/s640x960/d1da6fe32d2cf68f032362279b2725a6b2bf8166.jpg)

Es el corazon, es un lenguaje muy sencillo compuesto de elementos, que se pueden aplicar a piezas de texto para darles un significado diferente en un documento, estructura un documento en secciones lógicas, e incrusta contenido como imágenes y vídeos en una página. 

Vamos a hacer un recorrido chiquito de HTML y si encuentro cosas interesantes la voy agregar como un block de hojas. 

- El HTML ("Hypertext Markup Language") no es un lenguaje de programación. Es un *lenguaje de marcado* que le dice a los navegadores web cómo estructurar las páginas web que estás visitando. Puede ser tan complejo o tan simple como desee el desarrollador web. 
- El HTML consiste en una serie de elementos, que puedes utilizar para encerrar, delimitar o marcar diferentes partes del contenido para hacer que aparezcan de una cierta manera, o actúen de determinada forma. Las etiquetas que delimitan un fragmento de contenido pueden hacer que dicho contenido enlace con otra página, ponga una palabra en cursiva, etcétera.

```html
<p>Mi gato es muy gruñón</p>
```

- La etiqueta de apertura: consiste en el nombre del elemento (en este caso, p), encerrado entre paréntesis angulares de apertura y cierre. Esta etiqueta de apertura marca dónde comienza el elemento o comienza a tener efecto. En este ejemplo, precede al comienzo del texto del párrafo.
- El contenido: Este es el contenido del elemento. En este ejemplo, es el texto del párrafo.
- La etiqueta de cierre: Es lo mismo que la etiqueta de apertura, excepto que incluye una barra diagonal antes del nombre del elemento. Esto indica dónde termina el elemento; en este caso, dónde finaliza el párrafo. No incluir una etiqueta de cierre es un error común de principiante, y puede conducir a extraños resultados.
El elemento lo conforman la etiqueta de apertura, seguida del contenido, seguido de la etiqueta de cierre.

## Head 

El elemento head de un documento HTML es la parte que no se muestra en el navegador cuando se carga la página. Contiene información como el título (<title>) de la página, enlaces al CSS (si quieres aplicar estilo a tu contenido HTML con CSS), enlaces para personalizar favicon, y otros metadatos (datos sobre el HTML, como quién lo escribió y palabras claves importantes que describen el documento). En este artículo abarcaremos todo esto y más, para darte bases sólidas en el manejo del marcado y otro código que debería estar presente en tu cabecera.

![imagen2](https://akus.b-cdn.net/imagenes/articulos/estructura-basica-de-una-pagina-web-en-html.jpg)

## Metadatos: el elemento < meta >

Los metadatos son datos que describen datos, y HTML tiene una forma «oficial» de introducir metadatos en un documento — el elemento < meta >. Hay diferentes tipos de elemento < meta > que se pueden incluir en el < head > de tu página.

Meta/Link | Significado
-------|------------
< meta charset="utf-8" /> | es un conjunto de caracteres universal que incluye casi todos los caracteres de casi cualquier idioma humano. Esto significa que tu página web podrá gestionar la visualización de cualquier idioma.
< meta name="twitter:title" content="Mozilla Developer Network" /> | Twitter también tiene sus metadatos propios, las Twitter Cards, que tienen un efecto similar cuando la URL del sitio se muestra en twitter.com. 
< link rel="shortcut icon" href="favicon.ico" type="image/x-icon" /> | Para agregar Iconos a tu pagina.

--------------------------------------------

En este codigo, en el html tenemos las siguientes etiquetas en el head. 

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">

<head>
    <meta charset="UTF-8">
    <title> Product Card</title>
    <link rel="stylesheet" href="card.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.2/css/all.min.css" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

- Tenemos el meta charset para el idioma. 
- Despues seguimos con el titulo, que viene a ser el nombre de la pestaña.
- La conexion entre el CSS y el HTML.
- Aca tenemos la conexion para los iconos y formatos. 
- El viewport es una etiqueta meta de HTML5 que indica el tamaño de la ventana o área visible de una pantalla, generalmente, de dispositivos móviles como smartphones o tablets, por lo que juega un rol crucial en la optimización móvil.

