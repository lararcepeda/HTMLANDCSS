# Analizando el codigo. 

Es un codigo chico y basico, como para implementar más adelante en otros proyectos, ahi habria que implementar más codigo. 

## HTML y CSS.

Es un CSS chiquto entonces, me voy a explicar un poco más el ajavascript que en los otros archivos.

```css
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  font-family: "Segoe UI", sans-serif;
  background: url(bg.png)no-repeat;
  background-size: cover;
  height: 100vh;
}

.container{
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}
```

En el primer fragmento, selecciona todos los elementos de la pagina y aplica las siguientes reglas. 
- Establece el margen (margin: 0) exterior de todos los elementos en 0. Esto asegura que no haya ningun espacio en blanco adicional alrededor de los elementos. 
- Establece el relleno interno de todos los elementos en 0 (padding: 0). Esto asegura que no haya ningún espacio en blanco adicional dentro de los elementos.
- Cambia el modelo de caja de todos los elementos a border- box, esto significa que el ancho y la altura especificados para un elemento incluiran el relleno y el borde, en lugar de agregarlos al ancho y la altura totales del elemento. Esto facilita el calculo y el control del tamaño real de los elementos.

En el segundo fragmento, en el body generalmente hace especificaciones como la letra con el font-family, el background que especifico con una imagen, el tamaño de ese background, es decir si cubre uno todo el body, aca le especificamos que lo cubra.Y la altura

En la clase conteiner tenemos
- Establece la posicion relativa para las tarjetas. Esto permite controlar la posicion de los elementos secundarios dentro de la tarjeta utilizando propiedades de posicion absoluta o relativa (position: relative).
- La altura y el ancho de ese componenete.
- Establece el cuerpo de la pagina como un contedor flexible, lo que permite aplicar propiedades de flexibilidad a sus elementos secundarios (display: flex).
- Centra los elementos secundarios horizontalmente (justify-content: center) dentro del cuerpo de la pagina. Los elementos se distribuiran de manera uniforme a lo largo del eje princiapl (horizontal) y se centraran en relacion con el eje transversal (verticalmente).
- Centra los elementos secundarios verticalmente (align-items: center) dentro del cuerpo de la pagina. Los elementos se alinearan en el centro eje transversal (verticalmente) y se distribuiran de manera uniforme a lo largo del eje princiapal (horizontalmente).
- Oculta cualquier contenido que se desborde de las tarjetas (overflow: hidden). Esto es útil si deseas recortar el contenido que excede el tamaño de la tarjeta y no deseas que se muestre fuera de los límites de la tarjeta.

```css
.container img{
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  object-fit: contain;
}

.container h2{
  z-index: 1;
  position: relative;
  color: #fff;
  font-size: 90px;
  text-transform: uppercase;
  font-weight: 900;
  letter-spacing: 32px;
  line-height: 60px;
}

.container h2 span{
  font-size: 48px;
  font-weight: 500;
  letter-spacing: 10px;
}

@media (max-width:800px){
  .container h2{
    font-size: 60px;
    letter-spacing: 19px;
    line-height: 35px;
  }

  .container h2 span{
    font-size: 26px;
  }
}

```
A las imagenes le agregamos un par de estilos generales. 

- Position: absolute, se utiliza para controlar el posicionamiento de un elemento en relacion con su elemento primario posicionado (es decir, un elemento primaro que tenga un valor diferente a static en su propiedad position). Cuando colocamos absolute a un elemento se eliminan del flujo normal del documento, lo que significa que no ocuparan espacio en la pagina y no afectaran la posicion de otros elemetos. En su lugar, se posicionan en relacion con su elemento primario posicionado o, si no hay ninguno, en relación con el elemento raíz.
- Despues tenemos la altura y el ancho del componenete.
- Luego, donde lo quiere posicionado especificamente.
- object-fit: contain: es para especificar un elemento de imagen o video debe ajustarse dentro de su contenedor. el contenido (imagen o video) se escala para caber completamente dentro del contenedor sin distorsión, manteniendo su relación de aspecto original. Esto significa que el contenido se ajustará para que se muestre por completo sin recortar ningún borde, pero es posible que pueda haber espacios vacíos en el contenedor si el contenido no llena todo el espacio disponible.

Despues tenemos un par de estilos al titulo el peso y el tamaño de la letra. Y el line-height se utiliza para establecer la altura de línea de un elemento de texto. Controla el espacio vertical entre líneas de texto y afecta la altura total de una línea.

Despues especificaciones de cuando la pantalla se haga más chica, en que escala ver las cosas. 

## JAVASCRIPT

```JS
 document.addEventListener("mousemove", parallax);
    function parallax(e){
      document.querySelectorAll(".object").forEach(function(move){

        var moving_value = move.getAttribute("data-value");
        var x = (e.clientX * moving_value) / 250;
        var y = (e.clientY * moving_value) / 250;

        move.style.transform = "translateX(" + x + "px) translateY(" + y + "px)";
      });
    }
```

1. document.addEventListener("mousemove", parallax);: Agrega un event listener al documento que se activa cuando se mueve el mouse. Cuando se activa, llama a la función parallax.

2. function parallax(e) {: Declara la función parallax que se ejecutará cuando se mueva el mouse. Toma un parámetro "e" que representa el evento del mouse.

3. document.querySelectorAll(".object").forEach(function(move) {: Selecciona todos los elementos con la clase "object" utilizando querySelectorAll. Luego, itera sobre cada elemento utilizando forEach y asigna el elemento actual a la variable move.

4. var moving_value = move.getAttribute("data-value");: Obtiene el valor del atributo "data-value" del elemento actual. Este valor se utiliza para determinar la velocidad de movimiento del elemento durante el efecto de paralaje.

5. var x = (e.clientX * moving_value) / 250;: Calcula la posición horizontal del elemento en función de la posición del cursor del mouse (e.clientX) y el valor de movimiento. Multiplica el valor de movimiento por la posición del cursor y luego divide por 250.

6. var y = (e.clientY * moving_value) / 250;: Calcula la posición vertical del elemento de manera similar a la línea anterior, pero utilizando e.clientY para la posición vertical del cursor.

7. move.style.transform = "translateX(" + x + "px) translateY(" + y + "px)";: Aplica una transformación CSS al elemento actual utilizando la propiedad transform del estilo. La transformación se realiza mediante la función translateX y translateY, que mueve el elemento horizontalmente y verticalmente según los valores calculados en las variables x e y, respectivamente.
