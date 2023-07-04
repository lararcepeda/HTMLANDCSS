# Explicando el codigo. 

Codigo sin javascript para principiantes en CSS y HTML. Es más un trabajo interactivo. Y siempre hay que pensar en como las cosas se pueden usar en otros proyectos, y como hacer una pagina más grande de cada cosita. 

![imagen](https://64.media.tumblr.com/ade6d61dc23416ad50bdea256a8b4d9d/da23f9d2e6984f63-a0/s400x600/e141ad80097565285beb18c45ae9a323d2dab210.jpg)

# CSS

```css
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}
body{
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #0A3A40;
}
.wrapper{
  position: relative;
  height: 330px;
  width: 620px;
  perspective: 1000px;
}
```

El asterisco (*) es el selector universal en CSS. De forma automática, el asterisco selecciona todos los elementos en un documento. Este selector puede utilizarse en combinación con espacios de nombres (namespace).
- Establece el margen (margin: 0) exterior de todos los elementos en 0. Esto asegura que no haya ningun espacio en blanco adicional alrededor de los elementos.
- Establece el relleno interno de todos los elementos en 0 (padding: 0). Esto asegura que no haya ningún espacio en blanco adicional dentro de los elementos.
- Cambia el modelo de caja de todos los elementos a border- box, esto significa que el ancho y la altura especificados para un elemento incluiran el relleno y el borde, en lugar de agregarlos al ancho y la altura totales del elemento. Esto facilita el calculo y el control del tamaño real de los elementos.
- Por ultimo establece la fuente principal para todos los elementos de la pagina. En este caso, se establece la fuente Poppins.

En el body establece:
- Establece la altura. 
- Establece el cuerpo de la pagina como un contedor flexible, lo que permite aplicar propiedades de flexibilidad a sus elementos secundarios (display: flex).
- Centra los elementos secundarios horizontalmente (justify-content: center) dentro del cuerpo de la pagina. Los elementos se distribuiran de manera uniforme a lo largo del eje princiapl (horizontal) y se centraran en relacion con el eje transversal (verticalmente).
- Centra los elementos secundarios verticalmente (align-items: center) dentro del cuerpo de la pagina. Los elementos se alinearan en el centro eje transversal (verticalmente) y se distribuiran de manera uniforme a lo largo del eje princiapal (horizontalmente).
- Y por ultimo el fondo.

Al componente con la clase wrapper tenemos
- Establece la posicion relativa para las tarjetas. Esto permite controlar la posicion de los elementos secundarios dentro de la tarjeta utilizando propiedades de posicion absoluta o relativa (position: relative).
- Altura y Ancho.
- "perspective: 1000px;" es una propiedad CSS que se utiliza para aplicar un efecto de perspectiva a un elemento y a sus descendientes. En este caso, "1000px" es el valor de la distancia en píxeles que se supone que el elemento está del punto de vista del observador. Esto significa que los elementos más cercanos al punto de vista del observador aparecerán más grandes que los elementos más lejanos. Es una técnica de diseño comúnmente utilizada en la creación de diseños 3D y efectos de profundidad en la web.

```css
.wrapper .flip-card{
  position: relative;
  height: 100%;
  width: 100%;
  background: #107361;
  transform-style: preserve-3d;
  transition: all 1s ease-in-out;
}
.wrapper:hover .flip-card{
  transform: rotateY(180deg);
}
.flip-card .card{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  width: 100%;
  background: #107361;
  border-top: 2px solid #107361;
  border-left: 2px solid #107361;
  box-shadow: 0 5px 10px rgba(0,0,0,0.2);
  backface-visibility: hidden;
  position: absolute;
}
.card span.circle,
.card span.square{
  height: 110px;
  width: 110px;
  border: 10px solid #4d2600;
}
```

Adentro del div principal adentro tenemos a flip-card que le colocamos los siguientes estilos
- transform-style: preserve-3d; es una propiedad CSS que se utiliza para especificar si los elementos hijos de un elemento 3D deben ser renderizados en 3D o en 2D. En este caso, "preserve-3d" indica que los elementos hijos deben ser renderizados en 3D, preservando así la perspectiva y la profundidad del elemento padre.
- transition: all 1s ease-in-out; es una propiedad CSS que se utiliza para crear una transición suave entre dos estados de un elemento. En este caso, "all" indica que se aplicará una transición a todas las propiedades CSS que cambien, "1s" indica la duración de la transición (1 segundo), y "ease-in-out" indica el tipo de curva de aceleración que se utilizará para la transición. Esto significa que cualquier cambio en las propiedades CSS de este elemento se animará durante 1 segundo con una curva de aceleración suave.

El hover, es cuando se haga click en la tarjeta se va a transformar en una rotacion sobre el eje y de 180grados. 

Estilos en la carta 
- Aclaramos un border de arriba y de abajo. Despues una sombra para dar el efecto de sobresalido. 
- backface-visibility: hidden; determina si la cara posterior de un elemento es visible de frente al usuario. La cara posterior de un elemento siempre es un fondo transparente, permitiendo, cuando es visible, que se muestre una imagen de espejo de la cara frontal. 

Hay casos en los que no queremos que la cara frontal de un elemento sea visible a través de la cara posterior, como cuando se hace el efecto de voltear una tarjeta (estableciendo dos elementos lado a lado).

Esta propiedad no tiene efecto en transformaciones 2D, pues estos no tienen perspectiva.

```css
.card span.circle{
  border-radius: 50%;
}
.card span.triangle{
  position: relative;
  height: 0;
  width: 0;
  border-right: 60px solid transparent;
  border-left: 60px solid transparent;
  border-bottom: 110px solid #4d2600;
  margin-right: 16px;
}
.card span.triangle::before{
  content: "";
  position: absolute;
  height: 0;
  width: 0;
  left: -40px;
  top: 20px;
  border-right: 40px solid transparent;
  border-left: 40px solid transparent;
  border-bottom: 80px solid #107361;
}
.back.card{
  transform: rotateY(180deg);
}
.back.card .home-logo{
  position: relative;
  height: 65px;
  width: 65px;
  border: 5px solid #4d2600;
  border-radius: 50%;
  margin-right: 16px;
}
.home-logo .icon{
  position: relative;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) translateY(6px);
  display: inline-block;
  height: 15px;
  width: 25px;
  background: #4d2600;
}
.home-logo .icon::before{
  content: "";
  position: absolute;
  top: -15px;
  height: 25px;
  width: 25px;
  background: #4d2600;
  transform: rotate(45deg);
}
.back.card .num{
  font-size: 25px;
  font-weight: 600;
  color: #4d2600;
}
```

No hay mucho más, solo repetición de la mismas. 

## Cosas que podes hacer con el codigo para seguir aprendiendo. 

- Podes agregar el JavaScript.
- Podes agrandar el diseño.
- Podes jugar con la paleta de colores. 
- Podes usar distintas partes en otro codigo.
- Podes mejorarlo. 
- Cambiar el diseño. 
