# Explicando un poqutio. 

Seguimos un poco en el HTML. 

![imagen](https://i.pinimg.com/564x/ae/0c/a7/ae0ca714f4d7b6b1f627ed9757da6465.jpg)

## Énfasis e importancia. 

En HTML usamos el elemento < em > *(emphasis)* para marcar estos casos. El documento logra entonces transmitir una lectura más interesante y además así lo reconocen los lectores de pantalla, que lo expresan con un diferente tono de voz. El navegador, de manera predeterminada, aplica el estilo de letra itálica, pero no debes utilizar esta etiqueta solamente para establecer el estilo de letra itálica. Para usar ese estilo, debes utilizar únicamente la etiqueta del elemento < span > y algo de CSS u otra etiqueta con el elemento < i >.

```html
<p>Me <em>alegro</em> de que no llegues <em>tarde</em>.</p>
```

### En negrita.

En HTML usamos el elemento < strong > (importancia fuerte) para marcar tales expresiones. El documento resulta entonces más útil. El estilo negrita es el que aplican los navegadores por omisión, pero no debes usar esta etiqueta solamente para aplicar este estilo. Para hacer eso usa el elemento < span > y CSS, o un elemento < b >

```html
<p>Este líquido es <strong>altamente tóxico</strong>.</p>

<p>Cuento contigo. <strong>¡No llegues tarde!</strong></p>
```

## Cursiva, negrita, subrayado...

Los elementos que hemos comentado hasta ahora tienen asociada una semántica clara. La situación con < b > (negrita o «bold»), < i > (cursiva o «italic») y < u > (subrayado o «underline») es algo más complicada. 

HTML5 redefinió los elementos < b >, < i > y < u > con roles semánticos nuevos un tanto confusos.

Esta es la regla de oro: el uso de < b >, < i > o < u > resulta adecuado cuando transmiten el significado que suele transmitir el uso tradicional de las negritas, itálicas o el subrayado, si no hay ningún otro elemento que resulte más adecuado. Sin embargo, siempre resulta crítico mantener una actitud orientada a la accesibilidad. El concepto de itálica no es demasiado útil para las personas que usan lectores de pantalla o para las personas que utilizan un sistema de escritura distinto del alfabeto latino.

- < i > se usa para transmitir el significado que tradicionalmente transmite la itálica: extranjerismos, clasificaciones taxonómicas, conceptos técnicos, un pensamiento...
- < b > se usa para transmitir el significado que tradicionalmente transmite la negrita: palabras clave, nombres de productos, frases principales...
- < u > se usa para transmitir el significado que tradicionalmente conlleva el subrayado: nombres propios, errores ortográficos...

## Crear hipervínculos

Los hipervínculos (o enlaces) son elementos que hacen que la web sea web. Los hipervínculos nos permiten vincular documentos a otros documentos o recursos, vincular a partes específicas de documentos o hacer que las aplicaciones estén disponibles en una dirección web.

### Anatomía de un enlace

Un enlace básico se crea incluyendo el texto que queramos convertir en un enlace usando un elemento ancla < a >, dándole un atributo href (también conocido como «Hypertext Reference», «target» u objetivo) que contendrá la dirección web hacia dónde queremos que apunte el enlace.

```html
<p>
  Crea un enlace a
  <a href="https://www.mozilla.org/es-ES/">la página de inicio de Mozilla</a>.
</p>
```

### Añadir información de asistencia con el atributo title

Otro atributo que posiblemente quieras agregar a tus enlaces es title. El título contiene información adicional sobre el enlace, como qué tipo de información contiene la página o cosas que debes tener en cuenta en el sitio web.

```html
<p>
  Crea un enlace a
  <a
    href="https://www.mozilla.org/es-ES/"
    title="El mejor lugar para encontrar más información acerca de la misión de Mozilla
          y cómo contribuir"
    >la página de inicio de Mozilla</a
  >.
</p>
```

## URLs absolutas y relativas

Dos términos que encontrarás en la Web son **URL absoluta** y **URL relativa**:

- URL absoluta: Hace referencia a una dirección definida por su ubicación absoluta en la web, esta incluye el protocolo y el nombre del dominio. Una URL absoluta siempre apuntará a la misma dirección, sin importar desde dónde se utilice.

- Una URL relativa: Hace referencia a una dirección que depende de la posición del archivo desde donde se utiliza. 

### Buenas prácticas en el uso de los enlaces

Hay algunas buenas prácticas que debemos respetar cuando escribimos enlaces. 

### Redacción clara del enlace

- Los usuarios de lectores de pantalla suelen saltar de enlace a enlace en la página y los leen todos sin contexto.
- No repetir la URL como parte del texto — Las URLs suenan horrible, y todavía suenan peor si las lee un lector de pantalla, letra por letra.
- No escribir «link» o «link a» o «enlace» o «enlace a» en el texto del enlace porque es redundante. Los lectores automáticos indican que hay un enlace al encontrarlo. Los usuarios también saben que hay un enlace, porque normalmente se suele cambiar el color del texto y se subraya (no hay que romper esta convención, porque los usuarios están acostumbrados a ella).
- Redacta la etiqueta del enlace de la manera más breve y concisa posible — los textos de enlace largos son especialmente molestos para los usuarios que utilizan lectores automáticos, porque tienen que escuchar todo el texto del enlace.
- Minimiza los casos en los que varias copias del mismo texto están vinculadas a diferentes lugares. Esto puede causar problemas a los usuarios de lectores de pantalla, si hay una lista de enlaces fuera de contexto que están etiquetados como "haz clic aquí", "haz clic aquí", "haz clic aquí".
- Utiliza enlaces relativos siempre que sea posible
- Utiliza el atributo download al enlazar una descarga

### Enlace a correo electrónico

Es posible crear enlaces o botones que, cuando se pulsan, abren un nuevo correo saliente en lugar de enlazar a un recurso o página. Esto se consigue con el elemento ancla < a > y el elemento mailto: seguido del esquema de la URL.

En su forma más básica, un enlace mailto: simplemente contiene la dirección de correo electrónico de los destinatarios. Por ejemplo:

```html
<a href="mailto:nowhere@mozilla.org"
  >Enviar correo electrónico a ninguna parte</a
>
```

De hecho, incluso el atributo con la dirección de correo electrónico es opcional. Si lo omites y tu (href simplemente es "mailto:", aparecerá una nueva ventana de correo saliente en el gestor de correo sin la dirección del destinatario. Esto es útil cuando queremos compartir enlaces que los usuarios puedan pulsar para enviar un correo electrónico y elegir un destinatario posteriormente.

### Especificar detalles

Además de la dirección de correo electrónico, puedes proporcionar otra información. De hecho, puedes incluir cualquier campo estándar contenido en el encabezado de cualquier mensaje en la URL mailto que proporciones. Los más utilizados son el «subject» (asunto), «cc» (con copia a) o «bcc» (copia oculta), y «body» (cuerpo del mensaje, que no es realmente un campo de la cabecera, pero permite especificar un mensaje breve para el nuevo correo electrónico). Cada campo y su valor se especifican como un argumento de la consulta.

```html
<a
  href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&subject=The%20subject%20of%20the%20email&body=The%20body%20of%20the%20email"
>
  Enviar un correo electrónico cc, bcc, asunto y cuerpo
</a>
```

## Cosas que podes mejorar en este codigo. 

- Podes agregarle JavaScript.
- Podes agrandar el diseño.
- Podes jugar con la paleta de colores. 
- Podes usar distintas partes en otro codigo.
- Podes mejorarlo. 
- Cambiar el diseño. 
 

