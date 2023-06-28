# Explicando el Codigo.

Un HTML chico y sin clases, solamente apuntando a la caja, estoy intentando no usar tanto las clases y rebuscar para que sea lo más especifico posible.

```css
div {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 300px;
  width: 300px;
  border-radius: 50%;
  box-shadow: inset -10px -10px 15px rgba(255, 255, 255, 1),
    inset 10px 10px 10px rgba(0, 0, 0, 0.1);
}
div::before {
  content: "";
  position: absolute;
  height: 172px;
  width: 177px;
  border-radius: 50%;
  box-shadow: -10px -10px 15px rgba(255, 255, 255, 1),
    10px 10px 10px rgba(0, 0, 0, 0.1);
}
span {
  height: 186px;
  width: 220px;
  position: absolute;
  animation: rotate 5s linear infinite;
}
@keyframes rotate {
  100% {
    transform: rotate(360deg);
  }
}
span::before {
  content: "";
  position: absolute;
  height: 30px;
  border-radius: 50%;
  width: 30px;
  background: linear-gradient(45deg, #B4BEC9, #B4BEC9);
  box-shadow: 0 5px 10px rgb(0 0 0 / 30%);
}
```

Al principio esta el import y despues coloca las especificaciones de la caja. Que en otros documentos esta explicado varias veces.

Voy a cambiar un toque la manera de explicación. En vez de explicar cada linea de codigo en chiquito. Voy agarrar un temas y lo voy a explicar a fondo. 

## Position 

La propiedad especifica cómo un elemento es posicionado en el documento. Las propiedades top, right, bottom y left determinan la ubicación la ubicación final de los elementos posicionados. 

### Tipos de posicionamiento

- Un elemento posicionado es un elemento cuyo valor de position es relative, absolute, fixed, o sticky. (En otras palabras, cualquiera excepto static).
- Un elemento posicionado relativamente es un elemento cuyo valor de position es relative. Las propiedades top y bottom especifican el desplazamiento vertical desde su posición original; las propiedades left y right especifican su desplazamiento horizontal.
- Un elemento posicionado absolutamente es un elemento cuyo valor de position es absolute o fixed. Las propiedades top, right, bottom, y left especifican el desplazamiento desde los bordes del bloque contenedor (en-US) del elemento. (El bloque contenedor es el ancestro relativo al cual el elemento está posicionado). Si el elemento tiene márgenes, se agregarán al desplazamiento. El elemento establece un nuevo contexto de formato de bloque para su contenido.
- Un elemento posicionado fijamente es un elemento cuyo valor de position es sticky. Es tratado como un elemento posicionado relativamente hasta que su bloque contenedor (en-US) cruza un límite establecido (como por ejemplo dando a top cualquier valor distinto de auto), dentro de su flujo principal (o el contenedor dentro del cual se mueve), desde el cual es tratado como "fijo" hasta que alcance el borde opuesto de su bloque contenedor (en-US).

        La mayoría de las veces, los elementos absolutamente posicionados que tienen su height y width establecidos en auto son ajustados hasta acomodarse a su contenido. Sin embargo, elementos non-replaced y absolutamente posicionados se pueden crear para llenar el espacio vertical disponible, especificando tanto top como bottom, y dejando height sin especificar (es decir, auto). De igual manera se pueden utilizar para llenar el espacio horizontal disponible especificando tanto left como right, y dando a width el valor de auto.

A excepción del caso anteriormente descrito (de elementos posicionados absolutamente rellenando el espacio disponible):

- Si ambos, top y bottom están especificados (técnicamente, no auto), top gana.
- Si ambos, left y right, están especificados, left gana cuando es ltr (Inglés, japonés horizontal, etc.) y right gana cuando direction es rtl (Persa, árabe, hebreo, etc.).

### Valores

- static

El elemento es posicionado de acuerdo al flujo normal del documento. Las propiedades top, right, bottom, left, and z-index no tienen efecto. Este es el valor por defecto.

- relative

El elemento es posicionado de acuerdo al flujo normal del documento, y luego es desplazado con relación a sí mismo, con base en los valores de top, right, bottom, and left. El desplazamiento no afecta la posición de ningún otro elemento; por lo que, el espacio que se le da al elemento en el esquema de la página es el mismo como si la posición fuera static. Este valor crea un nuevo contexto de apilamiento, donde el valor de z-index no es auto. El efecto que tiene relative sobre los elementos table-*-group, table-row, table-column, table-cell, y table-caption no está definido.

- absolute

El elemento es removido del flujo normal del documento, sin crearse espacio alguno para el elemento en el esquema de la página. Es posicionado relativo a su ancestro posicionado más cercano, si lo hay; de lo contrario, se ubica relativo al bloque contenedor (en-US) inicial. Su posición final está determinada por los valores de top, right, bottom, y left.

Este valor crea un nuevo contexto de apilamiento cuando el valor de z-index no es auto. Elementos absolutamente posicionados pueden tener margen, y no colapsan con ningún otro margen.

- fixed

El elemento es removido del flujo normal del documento, sin crearse espacio alguno para el elemento en el esquema de la página. Es posicionado con relación al bloque contenedor (en-US) inicial establecido por el viewport, excepto cuando uno de sus ancestros tiene una propiedad transform, perspective, o filter establecida en algo que no sea none (ver CSS Transforms Spec), en cuyo caso ese ancestro se comporta como el bloque contenedor. (Notar que hay inconsistencias del navegador con perspective y filter contribuyendo a la formación del bloque contenedor.) Su posición final es determinada por los valores de top, right, bottom, y left.

Estos valores siempre crean un nuevo contexto de apilamiento. En documentos impresos, el elemento se coloca en la misma posición en cada página.

- sticky Experimental

El elemento es posicionado de acuerdo al flujo normal del documento, y luego es desplazado con relación a su ancestro que se desplace más cercano y su bloque contenedor (en-US) (ancestro en nivel de bloque más cercano) incluyendo elementos relacionados a tablas, basados en los valores de top, right, bottom, y left. El desplazamiento no afecta la posición de ningún otro elmento.

Estos valores siempre crean un nuevo contexto de apilamiento. Nótese que un elemento sticky se "adhiere" a su ancestro más cercano que tiene un "mecanismo de desplazamiento" (creado cuando el overflow es hidden, scroll, auto, o bien overlay), aún si ese ancestro no es el ancestro con desplazamiento más cercano. Esto inhibe efectivamente el comportamiento "sticky" (ver el Github issue en W3C CSSWG).