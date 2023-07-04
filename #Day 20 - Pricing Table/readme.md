# Explicando un poquito. 

Volvemos un ratito al HTML

![imagen](https://i.pinimg.com/564x/11/a4/6e/11a46ef36bcb5df6f8df7cf817272f52.jpg)

## Código permisivo

¿Qué queremos decir con permisivo? Bien, normalmente cuando hacemos algo mal al codificar, suele haber dos tipos de error:

- Errores sintácticos: Son errores de escritura en el código que impiden que el programa funcione, como el error en Rust de arriba. Suelen ser fáciles de arreglar si estamos familiarizados con las herramientas adecuadas y sabemos el significado de los mensajes de error.

- Errores lógicos: En estos errores la sintaxis es correcta, pero el código no hace lo que debería, por lo que el programa funciona de forma incorrecta. Estos errores son, por lo general, más difíciles de solucionar que los sintácticos, porque no hay mensajes de error que nos avisen de ellos.

## Interpretación de los mensajes de error

La lista de mensajes de error que nos presenta el validador suele ayudar, pero a veces, no resultan muy útiles; con un poco de práctica aprenderemos a interpretar la lista para arreglar nuestro código. Veamos los mensajes de error y su significado. Observamos que cada mensaje se presenta con un número de línea y de columna, para ayudar a localizar el error más fácilmente.

- "Consider adding a lang attribute to the html start tag to declare the language of this document.": No se trata de un error, sino de una advertencia (warning). La recomendación es definir siempre un idioma, y este "warning" explica cómo hacerlo..

- "End tag li implied, but there were open elements" (2 instancias): Estos mensajes indican que un elemento que ha sido abierto debe ser cerrado. La etiqueta de cierre se supone, pero no está ahí. La información de la línea/columna apunta a la primera línea después de donde debería estar la etiqueta de cierre; es una buena pista para ver qué pasa.

- "Unclosed element strong": Un elemento < strong > no ha sido cerrado, y la línea/columna apunta directamente al lugar del error.

- "End tag strong violates nesting rules": Este apunta a elementos que están incorrectamente anidados, y la línea/columna nos indica donde están.

- "End of file reached when inside an attribute value. Ignoring tag": Esta es bastante enigmática; se refiere al hecho de que el valor de un atributo no ha sido bien construido, posiblemente cerca del final del archivo porque el final aparece dentro del valor del atributo. El hecho de que el navegador no muestre el enlace nos debería dar una buena pista de qué elemento es el erróneo.

- "End of file seen and there were open elements": Este es un poco ambiguo, pero básicamente se refiere al hecho de que hay elementos abiertos que necesitan ser cerrados adecuadamente. Los números de línea apuntan a las últimas líneas del archivo, y este mensaje de error viene con una línea de código que indica un ejemplo de un elemento abierto.

- Unclosed element ul: Este no ayuda mucho, porque el elemento < ul > está cerrado correctamente. Este error se debe a que el elemento < a > no ha sido cerrado, ya que faltan las comillas de cierre.
