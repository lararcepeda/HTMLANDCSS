# Explicando el Codigo.

![imagen](https://i.pinimg.com/564x/00/c0/50/00c050a2e29a8956a5c15d3ed4a81c24.jpg)

```css
.container {
  position: relative;
  /*especifica cómo un elemento es posicionado en el documento. Las propiedades top, right, bottom, y left determinan la ubicación final de los elementos posicionados. */
  background-image: url("images/bg.png");
  background-size: cover;
  /*especifica el tamaño de las imágenes de fondo.
  cover Escala la imagen al mayor tamaño posible sin estirarla. Si las proporciones de la imagen difieren de las del elemento, es recortada vertical u horizontalmente para que no quede un espacio vacío.*/
  padding: 25px;
  /*establece el área de relleno en los cuatro lados de un elemento a la vez.*/
  border-radius: 28px;
  /*Establece el borde de un contenido, lo hace ver más redondo*/
  max-width: 380px;
  /*El maximo ancho*/
  width: 100%;
  /*El ancho*/
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
  /*Sombra de la caja*/
}
header,
.logo {
  display: flex;
  align-items: center;
  justify-content: space-between;
  /*Centro el logo*/
}
.logo img {
  width: 48px;
  margin-right: 10px;
  /*de costado separa el contenido de los demas*/
}
h5 {
  font-size: 16px;
  font-weight: 400;
  color: #fff;
  /*tamaño de la letra, el peso de la letra y el color de la letra*/
}
header .chip {
  width: 60px;
  /*ancho*/
}
h6 {
  color: #fff;
  font-size: 10px;
  font-weight: 400;
  /*Color de letra, tamaño de letra, y peso de letra*/
}
h5.number {
  margin-top: 4px;
  font-size: 18px;
  letter-spacing: 1px;
  /*De arriba, separamos el contenido. Tamaño de letra, espacio de las letras*/
}
h5.name {
  margin-top: 20px;
  /*De arriba, separamos el contenido*/
}
.container .card-details {
  margin-top: 40px;
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  /*De arriba separamos el contenido. Flexibilidad en el contenido. Y abajo voy a especificar algunas cositas más de este */
}
```

Cuando hablamos de Justify-content: space-between nos referimos a los items flex se distribuyen uniformemente sobre la línea. El espaciamiento se hace de tal manera que el espacio adyacente entre dos items es el mismo. El borde del comienzo principal y el borde del final principal se alinean al ras con el borde del primer y último item respectivamente.
Y cuando hablamos de flex-end alinea los elementos con el borde final del eje secundario. 



