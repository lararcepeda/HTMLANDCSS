# Explicando el codigo. 

Tenemos un HTML con una lista ordenada para colocar el menu. Este proyecto es más de practica acentuando en el HTML y un CSS bastante rapido, que despues puede ser componente de una pagina más grande, y sirve como para ir aplicando cosas. 

![imagen](https://64.media.tumblr.com/f6c7af30a7be720fddb66410f8a7ed8d/6fc4b20f68ffffc4-f0/s400x600/6c739bb7529efdc28db7a408b91de11392b52493.pnj)

## CSS

```css
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
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
  background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(21,92,166,1) 58%, rgba(0,212,255,1) 100%);
}
```

Al principio tenemos el import para la tipografia de la pagina. 

- El asterisco va a marcar toda la pagina y va a colocar las reglas en general para todos los fragmentos de nuestra pagina. Va a aclarar las siguientes reglas.
- Establece el margen (margin: 0) exterior de todos los elementos en 0. Esto asegura que no haya ningun espacio en blanco adicional alrededor de los elementos.
- Establece el relleno interno de todos los elementos en 0 (padding: 0). Esto asegura que no haya ningún espacio en blanco adicional dentro de los elementos.
- Cambia el modelo de caja de todos los elementos a border- box, esto significa que el ancho y la altura especificados para un elemento incluiran el relleno y el borde, en lugar de agregarlos al ancho y la altura totales del elemento. Esto facilita el calculo y el control del tamaño real de los elementos.
- Por ultimo establece la fuente principal para todos los elementos de la pagina. En este caso, se establece la fuente Poppins. 

En el body colocamos reglas que son las siguientes. 
- Establece el fondo de la pagina, con background, que este caso lo coloque en gradiente. 
- Establecemos una altura 
- Centramos los items de forma vertical (align-item) y horizontal (justify-content).
- Colocamos un display, como un contedor flexible, lo que permite aplicar propiedades de flexibilidad a sus elementos secundarios (display: flex).

```css
.nav-links{
  display: flex;
  align-items: center;
  background: #fff;
  padding: 20px 15px;
  border-radius: 12px;
  box-shadow: 0 5px 10px rgba(0,0,0,0.2);
}
.nav-links li{
  list-style: none;
  margin: 0 12px;
}
.nav-links li a{
  position: relative;
  color: #333;
  font-size: 20px;
  font-weight: 500;
  padding: 6px 0;
  text-decoration: none;
}
.nav-links li a:before{
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3px;
  width: 0%;
  background: #34efdf;
  border-radius: 12px;
  transition: all 0.4s ease;
}
```
Voy a explicar algunos estilos que antes no se explicaron. 

- Padding: La propiedad abreviada de CSS padding establece el área de relleno en los cuatro lados de un elemento a la vez. Es el área de relleno de un elemento es el espacio entre su contenido y su borde.
- Border-radius: Establece un radio de borde (border-radius) para las tarjetas, lo que hace que los bordes de las tarjetas sean redondeados.
- Box-shadow: Establece un radio de borde (border-radius) de 10px para las tarjetas, lo que hace que los bordes de las tarjetas sean redondeados.
- List-Style: La propiedad de estilo de lista (list-style) permite definir de golpe todos los parámetros: list-style-type, list-style-image, y list-style-position. Saca los puntos negros que aparecen prederterminados en li
- Margin: La propiedad CSS margin establece el margen para los cuatro lados. Es una abreviación para evitar tener que establecer cada lado por separado con las otras propiedades de margen: margin-top (en-US), margin-right, margin-bottom y margin-left (en-US). Recordar que primero (desde adentro hacia afuera) viene primero el contenido, el padding y despues el margin. 
- Establece la posicion relativa para las tarjetas. Esto permite controlar la posicion de los elementos secundarios dentro de la tarjeta utilizando propiedades de posicion absoluta o relativa (position: relative).
- Font size viene a ser el tamaño de la letra y font weight viene a ser el grosor de esa letra.
- Text-decoration: La propiedad CSS text-decoration se usa para establecer el formato de texto a subrayado (underline) y suprarrayado (overline), tachado (line-through) o parpadeo (blink). El subrayado y el suprarrayado son posicionados bajo el texto, mientras la línea a través de éste se posiciona por encima.
- El content: "", se utiliza ra especificar el contenido que se debe insertar antes del contenido real del elemento seleccionado. Esta propiedad es obligatoria cuando se utliza :before y :after, incluso si no se especifica ningun valor para content. Se especificada para que no se agrege ningun contenido adicional antes del contenido real del elemento.
- Transition se utiliza para definir una transicion suave entre diferentes estados de un elemento, permitiendo que los cambios de estilo ocurran de manera gradual en lugar de instantanea.

```css
.nav-links li a:hover:before{
  width: 100%;
}
.nav-links li.center a:before{
  left: 50%;
  transform: translateX(-50%);
}
.nav-links li.upward a:before{
  width: 100%;
  bottom: -5px;
  opacity: 0;
}
.nav-links li.upward a:hover:before{
  bottom: 0px;
  opacity: 1;
}
.nav-links li.forward a:before{
  width: 100%;
  transform: scaleX(0);
  transform-origin: right;
  transition: transform 0.4s ease;
}
.nav-links li.forward a:hover:before{
  transform: scaleX(1);
  transform-origin: left;
}
```

- En CSS, :before crea un pseudoelemento que es el primer hijo del elemento seleccionado. Es usado normalmente para añadir contenido estético a un elemento, usando la propiedad content. Este elemento se muestra en línea con el texto de forma predeterminada.
- La pseudo-clase :hover de CSS coincide cuando el usuario interactúa con un elemento con un dispositivo señalador, pero no necesariamente lo activa. Generalmente se activa cuando el usuario se desplaza sobre un elemento con el cursor (puntero del mouse).

