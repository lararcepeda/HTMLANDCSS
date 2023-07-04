# Explicando un poquito. 

        Datito: Hay una pagina en la cual encontras 
        cualquier tipo de documentación de algun idioma 
        de programación especifico. 
        Se llama overapi.com

![imagen](https://i.pinimg.com/736x/8f/2f/b2/8f2fb26ffb0cf5d290350683c1aa493f.jpg)


## Estructura web y documentación

**Encabezado:**

Normalmente formado por una gran franja que cruza la parte superior de la página con un gran título, un logotipo y quizás un lema. Esta parte suele permanecer invariable mientras navegas entre las páginas de un mismo sitio web.

**Barra de navegación:**

Son los enlaces a las secciones principales del sitio web. Normalmente está formada por un menú con botones, enlaces o pestañas. Al igual que el encabezado, este contenido suele permanecer invariable en las diferentes páginas del sitio; tener un menú inconsistente en tu página web conducirá a los usuarios a la confusión y frustración. Muchos diseñadores web consideran que el menú de navegación forma parte del encabezado y que no posee un componente individual, aunque no es necesario que sea así; de hecho, algunos argumentan que tener ambos componentes por separado es mejor por motivos de accesibilidad porque los lectores de pantalla pueden leer mejor ambos elementos si están separados.

**Contenido principal:**

Es la gran parte central de la página y contiene la mayor parte del contenido particular de una página web concreta; por ejemplo, el video que quieres ver, la narración que quieres leer, el mapa que quieres consultar, los titulares de las noticias, etc. ¡Esta es la parte que definitivamente debe variar mucho de una página a otra de tu sitio web!

**Barra lateral:**

Suele incluir algún tipo de información adicional, enlaces, citas, publicidad, etc. Normalmente está relacionada con el contenido principal de la página (por ejemplo, en una página de noticias, la barra lateral podría contener la biografía del autor o enlaces a artículos relacionados), pero en otras ocasiones encontraras elementos recurrentes como un menú de navegación secundario.

**Pie de página:**

Es la parte inferior de la página, que generalmente contiene la letra pequeña, el copyright o la información de contacto. Es el sitio donde se coloca la información común (al igual que en el encabezado), pero esta información no suele ser tan importante o es secundaria con respecto a la página en sí misma. El pie también se suele usar para propósitos SEO, e incluye enlaces de acceso rápido al contenido más popular.

- encabezado: < header >.
- menú de navegación : < nav >.
- contenido principal: < main >, con varias subsecciones (además de la barra lateral) representadas por los elementos < article >, < section >, y < div >.
- barra lateral: < aside >; a menudo colocada dentro de < main >.
- pie de página: < footer >.

## Elementos de diseño HTML en detalle

Es bueno entender el significado global de todos los elementos definitorios de las secciones HTML en detalle; es algo en que trabajarás gradualmente a medida que comiences a tener más experiencia en el desarrollo web. 

- < main > encierra el contenido particular a esta página. Utilizaremos < main > solamente una vez para cada página y lo situaremos directamente dentro del elemento < body >. Es mejor que no lo anidemos en otros elementos.

- < article > encuadra un bloque de contenido que tiene sentido por sí mismo aparte del resto de la página (por ejemplo una entrada en un blog).

- < section > es parecido al elemento < article >, pero se usa más para agrupar cada parte de la página que, por su funcionalidad, constituye una sección en sí misma (por ejemplo un minimapa o un conjunto de titulares y resúmenes). Se considera una buena práctica comenzar cada una de estas secciones con un título de encabezado (heading); observa que podemos subdividir artículos (< article >) en distintas secciones (< section >), o también secciones en distintos artículos, dependiendo del contexto.

- < aside > incluye contenido que no está directamente relacionado con el contenido principal, pero que puede aportar información adicional relacionada indirectamente con él (resúmenes, biografías del autor, enlaces relacionados, etc.).

- < header > representa un grupo de contenido introductorio. Si este es «hijo» de un elemento < body >, se convertirá en el encabezado principal del sitio web, pero si es hijo de un elemento < article > o un elemento < section >, entonces simplemente será el encabezado particular de cada sección (por favor, no lo confundas con títulos y encabezados).

- < nav > contiene la funcionalidad de navegación principal de la página. Los enlaces secundarios, etc., no entrarán en la navegación.

- < footer > representa un grupo de contenido al final de una página.

## Envolturas no semánticas

A veces hay situaciones en las que no encuentras un elemento semántico adecuado para agrupar ciertos elementos o englobar cierto contenido. Para casos como esos, HTML dispone del elemento < div > y del elemento < span >. Preferentemente estos elementos se deberán utilizar con sus atributos (class), para conferirles algún tipo de etiquetado que permita determinarlos con facilidad.

- < span > es un elemento no-semántico que se utiliza en el interior de una línea. Se utiliza cuando no se nos ocurre el uso de ningún otro elemento semántico de texto en el que incluir el contenido, o si no se desea añadir ningún significado específico. 

- < div > es un elemento de bloque no-semántico; lo utilizaras cuando no se te ocurra el uso de otro elemento semántico mejor, o si no deseas añadir ningún significado concreto. 


## Cosas para mejorar del codigo.

- Agregarle cositas. 
- Mejorar el diseño. 
- Cambiar la plaleta de colores. 
- Buscar en donde puede encajar en otro codigo.
- Agregarle JavaScript. 
