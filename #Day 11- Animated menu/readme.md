# Explicando el codigo.

![imagen](https://i.pinimg.com/564x/67/f4/c3/67f4c394df2914e3f6275ebb3d450b79.jpg)

```css
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700&display=swap');
/*La letra*/
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins',sans-serif;
  /*El asterisco (*) es el selector universal en CSS. De forma automática, el asterisco selecciona todos los elementos en un documento. Este selector puede utilizarse en combinación con espacios de nombres (namespace).

- Establece el margen (margin: 0) exterior de todos los elementos en 0. Esto asegura que no haya ningun espacio en blanco adicional alrededor de los elementos.
- Establece el relleno interno de todos los elementos en 0 (padding: 0). Esto asegura que no haya ningún espacio en blanco adicional dentro de los elementos.
- Cambia el modelo de caja de todos los elementos a border- box, esto significa que el ancho y la altura especificados para un elemento incluiran el relleno y el borde, en lugar de agregarlos al ancho y la altura totales del elemento. Esto facilita el calculo y el control del tamaño real de los elementos.
- Por ultimo establece la fuente principal para todos los elementos de la pagina. En este caso, se establece la fuente Poppins.*/
}

body{
  height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #f2f2f2;
/*Establece la altura.
Establece el cuerpo de la pagina como un contedor flexible, lo que permite aplicar propiedades de flexibilidad a sus elementos secundarios (display: flex).
Centra los elementos secundarios horizontalmente (justify-content: center) dentro del cuerpo de la pagina. Los elementos se distribuiran de manera uniforme a lo largo del eje princiapl (horizontal) y se centraran en relacion con el eje transversal (verticalmente).
Centra los elementos secundarios verticalmente (align-items: center) dentro del cuerpo de la pagina. Los elementos se alinearan en el centro eje transversal (verticalmente) y se distribuiran de manera uniforme a lo largo del eje princiapal (horizontalmente).
Y por ultimo el fondo.*/
}
nav{
  width: 600px;
  height: 60px;
  border-radius: 5px;
  display: flex;
  text-align: center;
  position: relative;
  background: #fff;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.25);
  /*Colocamos el ancho y la altura. 
  El borde del nav. Disponemos flexibilidad, y centramos. Y colocamos sombra*/
}
nav label{
  width: 100%;
  height: 100%;
  line-height: 60px;
  font-size: 18px;
  font-weight: 400;
  border-radius: 5px;
  margin: 0 5px;
  color: #706513;
  position: relative;
  z-index: 1;
  cursor: pointer;
  transition: all 0.3s ease;
  /*s una propiedad CSS que se utiliza para crear una transición suave entre dos estados de un elemento. En este caso, "all" indica que se aplicará una transición a todas las propiedades CSS que cambien, "1s" indica la duración de la transición (1 segundo), y ease significa empezar lento, despues rapido y despues despacio */
}
nav label:hover{
background: #08403E;
}
nav label i{
  margin-right: 4px;
}
nav .slider{
  position: absolute;
  height: 100%;
  width: 20%;
  background: #520120;
  left: 0;
  top: 0;
  border-radius: 5px;
  transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
  z-index: 1;
}
#home:checked ~ nav label.home,
#blog:checked ~ nav label.blog,
#code:checked ~ nav label.code,
#help:checked ~ nav label.help,
#about:checked ~ nav label.about{
  color: #fff;
}
#blog:checked ~ nav .slider{
left: 20%;
}
#code:checked ~ nav .slider{
left: 40%;
}
#help:checked ~ nav .slider{
left: 60%;
}
#about:checked ~ nav .slider{
left: 80%;
}
input[type=radio]{
  display: none;
}
```

#home:checked ~ nav label.home: Lo coloco a parte ya que es algo más especifico, utilizando el selector :checked y el selector de hermanos adyacentes (~): Selecciona todos los elementos hermanos adyacentes que siguen al elemento seleccionado en la jerarquía del DOM. 