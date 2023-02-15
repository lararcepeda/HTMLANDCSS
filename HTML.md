## ¿QUÉ ES EL FRONTEND Y BACKEND? ¿Y FULLSTACK?

Básicamente, cuando hablamos de **"detrás de escena"**, es decir, el servidor y la base de datos que ayudan a entregar información del usuario desde una interfaz, hablamos del **back-end.** Es la parte del sitio con la que los usuarios no tienen contacto. El **back-end** es una parte fundamental de cualquier sitio web o aplicación web.
Si el **back-end** es el desarrollo del elemento web que no vemos, el** front-end** es toda la parte visible de las aplicaciones y sitios web. Esta área no trata directamente con bases de datos, servidores y todas las aplicaciones de** back-end ** complejas, pero aborda la usabilidad, los efectos visuales y la velocidad de carga, entre otros detalles.
Más directamente, el **Desarrollador Front End** es responsable de la interacción directa del usuario, por lo que se desarrolla cuidando el lado más visual de las aplicaciones, como el cuidado de los colores, botones, enlaces, menús y todo lo que vemos. En una página cuando estamos accediendo.
El **Desarrollador Full Stack** es un profesional capacitado para desarrollar distintas etapas de un proyecto web. Trabaja tanto en el back-end como en el front-end.

[![Foto de diferencia de Back End y Front End](https://profile.es/wp-content/media/frontend-backend-dos-caras-500x389.png "Foto de diferencia de Back End y Front End")](http://https://profile.es/wp-content/media/frontend-backend-dos-caras-500x389.png "Foto de diferencia de Back End y Front End")

## PAGINAS ESTATICAS VS DINAMICAS.

Las **webs estáticas** son básicamente paginas informativas que tienen sus secciones y contenido fijo. Obviamente se pueden actualizar, pero no de una forma sencilla para el usuario que no tenga algún conocimiento de HTML. En las páginas web estáticas no se utilizan bases de datos ni se requiere programación. Este tipo de webs son más económicas ya que el tiempo de programación es mucho menor que en las páginas dinámicas.

Las** webs dinámicas** son páginas en las que su contenido es fácilmente y frecuentemente modificado. Se construyen usando lenguajes de programación que permite programar aplicaciones de todo tipo: blogs, foros, tiendas, etc. Requiere base de datos para almacenar la información.

## HTML: ANATOMÍA DE UNA PÁGINA WEB

[![Composición del HTML](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQiK_z1318XXK2EHxyfzocrDy6nqa5FF1hhcLYSvKfXo32iUn_i8k50ebK6rDtrlEzMluA&usqp=CAU "Composición del HTML")](http://https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQiK_z1318XXK2EHxyfzocrDy6nqa5FF1hhcLYSvKfXo32iUn_i8k50ebK6rDtrlEzMluA&usqp=CAU "Composición del HTML")

•	**Las capas o contenedores** son unos recuadros o espacios rectangulares que pueden colocarse en cualquier parte de la página. En ellas, podemos insertar contenido HTML. Su utilidad principal es visual, permitiendo organizar y dar estructura y diseño a las páginas HTML. 

•	**El header o cabecera** de una página web es el término que hace referencia a la parte superior de un sitio web. Al ser lo primero que el usuario visualiza, debes tener en cuenta dos cosas. *Primero, que los usuarios puedan navegar fácilmente por él. y, segundo, ofrecer información relevante sobre tu identidad para conectar lo antes posible con tus visitantes.*

A grandes rasgos, estos son los elementos que habitualmente forman la cabecera de una web. Algunos de estos son opcionales, pero otros son obligatorios: Elementos de tu identidad corporativa. Estos son el logo, el eslogan y el nombre de la empresa. Un menú. Gracias a este, el usuario podrá navegar por la web para encontrar lo que busca. Aquí deberán estar todas las secciones de la web. Iconos de las redes sociales. Aquellas donde tengas presencia. Algunas marcas ponen estos botones en el footer. Información de contacto. Puede ser un icono de teléfono o correo electrónico. Un buscador. A través de este el usuario puede introducir una palabra clave o relacionada a tu negocio para encontrar rápidamente algo en tu web.

•	**El elemento HTML ** < main > representa el contenido principal del < body > de un documento o aplicación. 
El área principal del contenido consiste en el contenido que está directamente relacionado, o se expande sobre el tema central de un documento o la funcionalidad central de una aplicación. Este contenido debe ser único al documento, excluyendo cualquier contenido que se repita a través de un conjunto de documentos como barras laterales, enlaces de navegación, información de derechos de autor, logos del sitio y formularios de búsqueda (a menos, claro, que la función principal del documento sea un formulario de búsqueda).

•	**El elemento HTML** < aside > representa una sección de una página que consiste en contenido que está indirectamente relacionado con el contenido principal del documento. Estas secciones son a menudo representadas como barras laterales o como inserciones y contienen una explicación al margen como una definición de glosario, elementos relacionados indirectamente, como publicidad, la biografía del autor, o en aplicaciones web, la información de perfil o enlaces a blogs relacionados.

•	**El Elemento HTML Footer** (< footer >) representa un pie de página para el contenido de sección más cercano o el elemento raíz de sección (p.e, su ancestro mas cercano < article >, < aside >, < nav >, < section >, < blockquote >, < body >, < details >, < fieldset >, < figure >, < td >). Un pie de página típicamente contiene información acerca del autor de la sección, datos de derechos de autor o enlaces a documentos relacionados.

**INDEX Y SU ESTRUCTURA BÁSICA**

Cada página comienza con: < HTML >
El nombre INDEX se debe que es el comienzo, o la pagina inicial en la que ingresa el usuario. 
A continuación viene la cabecera, delimitada por < HEAD > y < /HEAD > .
Después, el comando < BODY >, que indica el comienzo del cuerpo de la página. Las instrucciones HTML se escribirán a continuación, y finalizarán con < /BODY >.
La página acabará con < /HTML > 
Hay ciertas etiquetas que no tienen un cierre, es decir, que no tiene el < /> por ende una buena practica es cerrarla vos haciendo />, al final. Ya que esto es por si otro programador lee el código y entiende que finaliza la acción. 

**•	DOCTYPE**
**<!DOCTYPE html>:** La etiqueta doctype declara el tipo de documento, por lo que esta está señalando que este es un documento HTML.

•	**HTML**
< html ></ htm l>: Delimita el documento HTML.

**•	LANG**
< html lang="es"></ html >: Indica el lenguaje de contenido del código. 

**•	HEAD**
< head ></ head >: El elemento head delimita la cabecera del documento, entre sus etiquetas contiene información como scripts, metadatos, estilos, ubicación de documentos de estilos, título de la página, etc.

•**	META**
< meta name="description" content="Descripción de la WEB">: Las meta etiquetas se utilizan para identificar propiedades del documento como por ejemplo el autor, el título y la descripción que mostrarán los buscadores, etc. La longitud de la meta descripcion no debe de superar los 155 caracteres.

**•	META CHARSET**
< meta charset="UTF-8" >: Establece el tipo de codificación del documento. Esto codifica tildes, ñs y emojis. Entre tantos otros. A pesar de que la pagina vaya a ser en inglés, se tiene que agregar igual. 

**•	META TITLE**
< meta name="tittle" content="Título de la WEB" >: Contiene el título que se mostrará en los buscadores.

**•	META NAME**
< meta name= “robots” content=”index, follow”/>: Es para autorizar el robots de los buscadores encuentren tu página. 

**•	META NAME**
< meta name="viewport" content="width=device-width, initial-scale=1.0">: Es para que se ajuste a la pantalla la página web, sin importar donde se abra.
También esta esté código si queres ser más específico
< meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">

**•	LINK **
< link href="http://dominio.com/hoja-de-estilos.css" rel="stylesheet" type="text/css"/>: Esta etiqueta contiene un link a una hoja de estilos externa, la cual se utilizará en este documento.

**•	HREF**
Especifica la url donde se localiza la hoja de estilo.

**•	BODY**
< body></ body>: La etiqueta body delimita el cuerpo del documento y contiene todo aquello que podremos ver en nuestro navegador. Imágenes, textos, enlaces, video, etc…

**•	HEADER**
< header></ header>: El contenido de esta etiqueta debe ser la cabecera de nuestra página donde se suele encontrar el título, el logotipo y poco más.

**•	NAV**
< nav></ nav>: Esta etiqueta sirve para delimitar el menú de la página, donde colocaremos los enlaces internos para movernos entre nuestras diferentes secciones del sitio web.

**•	A **
< a href="http://dominio.com/seccion2.html">IR SECCIÓN 2</ a>: Representa un enlace o hipervínculo. 

**•	HREF**
Dirección URL hacia la que apunta el enlace.

**•	H1, H2, H3, H4, H5, H6**

# < h1>Título de la WEB</ h1> 
## < h2>CONTENIDO PRINCIPAL</ h2>
### < h3>Testimonios</ h3> 
#### < h4>Avisos legales</ h4>

Estas etiquetas establecen los encabezados. Se organizan por niveles siendo H1 el más importante y H6 el menos importante. Con el H1 como el tamaño más grande, los tamaños vienen determinados por el html y vos lo cambias con el css. 

**•	SECTION**

< section></ section>: La etiqueta section engloba una sección de texto, imágenes y otros elementos que guardan cierta relación entre ellos. Normalmente siempre le podremos poner un título o encabezado.

**•	ARTICLE**

< article></ article>: La etiqueta article se suele encontrar dentro de una etiqueta section y sirve para dividir y ordenar los contenidos en su interior.

**•	DIV**
< div></ div>: Otra forma de dividir contenido para posteriormente aplicarle clases y modificar su estilo.

**•	P**
< p></ p>: Entre las etiquetas P colocaremos un párrafo de texto.

**•	IMG**
< img src="http://dominio.com/imagen.jpg" alt="paisaje">: Esta etiqueta coloca una imagen en el documento mediante un enlace.

**•	ALT**
Representa el texto alternativo, muy importante para que los buscadores puedan obtener información de la imagen.

**•	SRC**
URL donde se encuentra la imagen.

**•	ASIDE**
< aside></ aside>: Contiene información no vital o que no está estrechamente relacionada con el contenido principal de la página como podrían ser banners de anuncios, citas o enlaces externos.

**•	FOOTER**
< footer></ footer>: Aquí encontraríamos el código perteneciente al pie de página, donde se suelen colocar los enlaces a textos legales, el copyright, etc

