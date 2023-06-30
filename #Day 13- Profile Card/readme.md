# Explicando el Codigo.

Sigo con el modelo anterior. 

## Display 

La propiedad CSS display especifica si un elemento es tratado como block or inline element y el diseño usado por sus hijos, como **flow layout (Diseño de Flujo)**, **grid (Cuadricula)** o **flex (Flexible)**.

Formalmente la propiedad display establece los tipos de visualización interna y externa de un elemento. La externa establece la participacion de un elemento en **flow layout**; en cambio la interna establece el **layout(Diseño)** de los hijos. Algunos valores de display estan totalmente definidos con sus especificaciones propias; por ejemplo el detalle de que pasa cuando display: flex es declarado y definido en la especificacion de Modelo Flexible de Caja (Flexible Box Model specification) de CSS. 

### Valores

Valor |	Descripción
------------- | -------------
*block* |	El elemento genera un cuadro de elemento de bloque.
*inline* | El elemento genera uno o más cuadros de elemento en línea.
*flow*  |	El elemento expone su contenido utilizando el diseño de flujo (diseño en bloque y en línea). 
*flow-root* | El elemento genera un cuadro de elemento de bloque que establece un nuevo contexto de formato de bloque .
*table* |	Estos elementos se comportan como elementos HTML < table>. Define un cuadro de nivel de bloque.
*flex* |	El elemento se comporta como un elemento de bloque y establece su contenido de acuerdo con el modelo de flexbox .
*grid* |	El elemento se comporta como un elemento de bloque y establece su contenido de acuerdo con el modelo de cuadrícula.

## Inline vs block

Cada elemento de HTML tiene un valor display CSS por defecto. 
- Los elementos de tipo div, encabezados, formularios, secciones o párrafos son elementos que tienen por defecto el valor block. 
- Los elementos como span, cursiva, negrita, enlace e imagen tienen por defecto el valor inline. Estos valores afectarán la forma en la que se comporta el elemento en relación al viewport y a la línea de texto.

## Display CSS: block

Cuando usamos este valor, el elemento empezará en una nueva línea al lado izquierdo de nuestro viewport y ocupará hacia la derecha, en el eje horizontal, tanto espacio como sea posible. Este bloque seguirá creciendo hacia abajo cuanto sea necesario y siempre intentará ocupar el ancho máximo de su contenedor, que en la mayoría de casos es el mismo viewport (espacio visible de la página web en pantalla).


## Display CSS: inline

El valor inline en la propiedad display en CSS representa elementos que continúan en la misma línea que el resto del contenido y es otro de los tipos de display css. Los elementos inline pueden verse como una letra dentro de la propia línea del flujo del texto en vez de un bloque aparte. Estos elementos no respetan ni márgenes ni paddings top/bottom ni propiedades de width y height. Es decir, si les aplicas un relleno o margen, solo afectarán a los lados del elemento, no su espaciado arriba y abajo. Esto se vería como un gran espacio a la izquierda y derecha del texto que no afecta el alto de la línea, pues su prioridad es mantenerla.

## Display: inline-block

Hay una opción que está en medio de los dos niveles de propiedad display en css anteriores. El inline-block se comporta igual que un elemento inline, ya que sigue el flujo de la línea del texto a la hora de situarse. Sin embargo, esta variedad se comporta como un elemento block, porque respeta las propiedades de width y height, así como los márgenes y paddings a cualquier lado del bloque.

Si quieres que un elemento esté en línea pero siga nuestros requerimientos de margen, relleno, alto y ancho, lo más fácil es cambiar el propiedad display en css del elemento a inline-block. A diferencia de los otros niveles, este no es un nivel por defecto, por lo que debes especificarlo en tu código.

## Display: none

Esta opción de propiedad display en cs, de los tipos de display css, oculta el elemento sin dejar espacio en el sitio que debería ocupar. Cuando agregues esta opción verás la página web sin ningún rastro del elemento. Esta opción permite crear estados en los que el elemento se oculte o se revele.

Un ejemplo de display: flex, estaria en este codigo. 