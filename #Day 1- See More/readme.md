# Explicando el codigo. 

Proximamente la aplicacion va a esta en ingles. 

En los archivos vas a encontrar un gif e imagenes.

![imagen](https://64.media.tumblr.com/a2e96a774b3405f936f903fdcc55ecc7/fbf932208ec0076a-0c/s540x810/57692e1d992b21d930fe38f86c4955ceb26bf0f4.jpg)

## HTML y CSS

El HTML es sencillo de entender, voy a pasar directamente al CSS. 

```css
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family:'Poppins', sans-serif;
}
```
Obviamente, al principio esta escrito el import para la tipografia. 

El pequeño fragmente de css recientemente marcado, selecciona todos los elementos de la pagina y aplica las siguientes reglas. 
- Establece el margen (margin: 0) exterior de todos los elementos en 0. Esto asegura que no haya ningun espacio en blanco adicional alrededor de los elementos. 
- Establece el relleno interno de todos los elementos en 0 (padding: 0). Esto asegura que no haya ningún espacio en blanco adicional dentro de los elementos.
- Cambia el modelo de caja de todos los elementos a border- box, esto significa que el ancho y la altura especificados para un elemento incluiran el relleno y el borde, en lugar de agregarlos al ancho y la altura totales del elemento. Esto facilita el calculo y el control del tamaño real de los elementos. 
- Por ultimo establece la fuente principal para todos los elementos de la pagina. En este caso, se establece la fuente Poppins. 

```css
body{
    background: #fff;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Despues empezamos a darle estilo al elemento Body, y se establece las siguientes reglas. 
- Establece el color del fondo del cuerpo de la pagina en blanco (#fff), lo que significa que el fondo sera de color blanco (background).
- Establece la altura minima del cuerpo de la pagina en al menos el 100% de la altura de la ventana (vh significa viesport height o en español, altura de la ventana). Esto asegura que el cuerpo ocupe al menos toda la altura visible de la ventana del navegador, lo que evita que el contenido se recorte o se solape con otros elementos. 
- Establece el cuerpo de la pagina como un contedor flexible, lo que permite aplicar propiedades de flexibilidad a sus elementos secundarios (display: flex).
- Centra los elementos secundarios horizontalmente (justify-content: center) dentro del cuerpo de la pagina. Los elementos se distribuiran de manera uniforme a lo largo del eje princiapl (horizontal) y se centraran en relacion con el eje transversal (verticalmente).
- Centra los elementos secundarios verticalmente (align-items: center) dentro del cuerpo de la pagina. Los elementos se alinearan en el centro eje transversal (verticalmente) y se distribuiran de manera uniforme a lo largo del eje princiapal (horizontalmente).

```css
.card-container{
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 30px;
    flex-wrap: wrap;
    margin: 30px;
}
```

Los selectores en CSS se emplean cuando el elemento de HTML tiene una clase. Aca tenemos los estilos para la clase card-container. Los estilos que se aplican son los siguientes.
- Hace que los elementos hijos directos del contenedor sean elementos flexibles (display: flex).
- Centra los elementos flexibles horizontalmente dentro del contenedor (justify-content: center).
- Centra los elementos flexibles verticalmente dentro del contenedor (align-items: center).
- Establece un espacio de separacion de 30px entre los elementos flexibles dentro del contenedor (gap: 30px).
- Permite que los elementos flexibles se envuelven en varias lineas si no caben en una sola linea (flex-wrap: wrap).
- Establece un margen exterior de 30px alrededor del contendor (margin: 30px).

```css
.card{
    position: relative;
    background: #fff;
    width: 350px;
    box-shadow: 0 5px 25px rgba(2, 2, 2, 0.25);
    border-radius: 10px;
    overflow: hidden;
}
```

Para el elemento que tiene la clase card, le pusieron los siguientes estilos
- Establece la posicion relativa para las tarjetas. Esto permite controlar la posicion de los elementos secundarios dentro de la tarjeta utilizando propiedades de posicion absoluta o relativa (position: relative).
- Lo mismo explicado arriba, solamente que para este elemento. 
- Con el Width establece el ancho de las tarjetas en 350px.
- Agrega una sombra alrededor de las tarjetas (box-shadow). La sombra se compone de una sombra horizontal de desplazamiento de 0px, una sombra vertical de desplazamiento de 5px, un desenfoque de 25px y un color de sombra especificado en rgba (2, 2, 2, 0.25).
- Establece un radio de borde (border-radius) de 10px para las tarjetas, lo que hace que los bordes de las tarjetas sean redondeados. 
- Oculta cualquier contenido que se desborde de las tarjetas (overflow: hidden). Esto es útil si deseas recortar el contenido que excede el tamaño de la tarjeta y no deseas que se muestre fuera de los límites de la tarjeta.

```css
.card .card-img{
    position: relative;
    width: 350px;
    height: 200px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.card .card-img img {
    width: 102%;
    height: 102%;
}

.card-content{
    position: relative;
    text-align: center;
    margin: 15px;
}
``` 

La unica gran diferencia es en los width y los height colocamos procentaje y no numeros exactos, esto se aplica en una imagen, en la imagen en si. Se coloca de esta manera haciendo la cuenta con el div donde colocamos la imagen, nuestro div tiene de alto 200px y de ancho 350, bueno nosotros estamos usando el 102% de eso. 

```css
.card-content .text {
    position: relative;
    font-size: .9em;
    text-align: left;
    height: 100px;
    overflow: hidden;
    transition: height 0.3s ease;
}

.card-content .text:before{
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(to top, #fff, transparent);
    display: none;
}
.card.gradient .card-content .text:before{
    display: block;
}

.card-content .see-more-btn{
    font-size: .85em;
    color: #fff;
    user-select: none;
    cursor: pointer;
    transition: color 0.3s ease;
}

.card-content .see-more-btn:hover{
    color: #111;
}

```

Las cosas que no estan mencionadas anteriormente, serian
- El font-size que vendria a especificar el tamaño de la letra.

Cuando algun elemento le agregamos un pseudo- elemento (:) se va a mostrar antes o despues de su contenido real. 
El :before se utiliza para insertar estilo antes del contenido real de un elemento seleccionado, en este caso agregamos.

- El content: "", se utiliza ra especificar el contenido que se debe insertar antes del contenido real del elemento seleccionado. Esta propiedad es obligatoria cuando se utliza :before y :after, incluso si no se especifica ningun valor para content. Se especificada para que no se agrege ningun contenido adicional antes del contenido real del elemento. 
- Bottom y left se pueden utilizar porque esta position: absolute, indica lo que mueve de abajo y de izquierda de la pantalla.
- Despues, background: linear-gradient(to top, #fff, transparent), se utiiza asi de largo cuando el fondo es gradado lineal, el to top indica que el degradado se aplicara de abajo hacia arriba, hay muchas paginas que te dan el codigo y vos solocas los colores y como y donde queres que comience. 
- Display: none, significa que esto no aparece hasta que sea pedido. Es decir que en el codigo con javascript cambiamos el estado a visible, cuando el usuario haga algo especifico. 

Vamos a los estilos en donde no se haya explicado, tenemos 
- user-select: none, es decir que no dejamos que el usuario seleccione eso.
- Cursor: pointer, viene a hacer que cada vez que se posicione el mouse ahi arriba se ponga en forma de mano para apretar.
- transition: color 0.3s ease; se utiliza para definir una transicion suave entre diferentes estados de un elemento, permitiendo que los cambios de estilo ocurran de manera gradual en lugar de instantanea. 

```css
@media screen and (max-width: 450px){
    .card-container {
        margin: 15px;
    }

    .card {
        width: 100%;
    }

    .card .card-img {
        width: 100%;
        max-width: 800px;
        height: auto;
    }
}
```

Aca es un codigo para cuando la el maximo de pantalla sea de 450px, ciertos elementos van a tener esos estilos para mejorar la experiencia de usuario.


--------------------

## CODIGO JAVASCRIPT

```JS
const cards = document.querySelectorAll(".card");

//Disable see more function from the text contents that the height is less the minium visible height of a text content on page lead.

window.onload = function(){
    cards.forEach((card) => {
        let seeMoreBtn = card.querySelector(".see-more-btn");
        let textContent = card.querySelector(".card-content .text");

        if(textContent.scrollHeight == textContent.clientHeight){
            seeMoreBtn.style.display = "none";
            textContent.style.height = "fit-content";
        }
        else{
            card.classList.add("gradient");
        }
    })
}


```

1. Empezamos declarando una constante llamada cards que almacena una lista de elementos HTML con la clase "card". Los elementos HTML deben tener una clase de CSS llamada "card" para que sean seleccionados. Esto pasa ya que tiene el metodo querySelectorAll de la variable "document".

2. Window.onload viene a ser una funcion que se ejecutara cuando se cargue completamente la ventana. Se recorre cada elemento de la lista card utilizando forEach.

3. Dentro del bucle forEach se obtienen dos elementos especificos de cada tarjeta: el boton "See More" y el contenido de texto de la tarjeta. Estos elementos se seleccionan utilizando el metodo querySelector en el contexto de la tarjeta actual. 

4. Luego, se verifica si la altura del contenido de texto (textContent) es igual a la altura visible del contenido de texto (clientHeight). Si son iguales, significa que el contenido de texto no se desborda y el botón "See More" no es necesario. En ese caso, se oculta el botón estableciendo su estilo display en "none" y se ajusta la altura del contenido de texto para que se ajuste al contenido real utilizando textContent.style.height = "fit-content".

```js
//See more function on click the see more button on each card

cards.forEach((card) => {
    let seeMoreBtn = card.querySelector(".see-more-btn");
    let textContent = card.querySelector(".card-content .text");

    seeMoreBtn.addEventListener("click", () => {
        card.classList.toggle("active");
        card.classList.toggle("gradient");

        if(card.classList.contains("active")){
            seeMoreBtn.innerHTML = "See Less"
            textContent.style.height = textContent.scrollHeight + "px";
        }
        else{
            seeMoreBtn.innerHTML = "See More";
            textContent.style.height = "100px";
        }
    });
});
```

5. Si la altura del contenido de texto es mayor que la altura visible, se agrega la clase CSS "gradient" a la tarjeta. Esto se hace mediante card.classList.add("gradient"). Esto podría aplicar un estilo de fondo degradado a la tarjeta, por ejemplo.

6. A continuación, hay otro bloque de código fuera de la función window.onload que también itera sobre la lista de tarjetas utilizando forEach. Este bloque de código maneja la funcionalidad "See More" cuando se hace clic en el botón.

7. Dentro del bucle forEach, se obtienen nuevamente el botón "See More" y el contenido de texto de cada tarjeta.

8. Luego, se agrega un evento de escucha de clic (addEventListener) al botón "See More". Cuando se hace clic en el botón, se ejecuta una función anónima.

9. En la función de clic, se alterna la presencia de las clases CSS "active" y "gradient" en la tarjeta actual. Esto significa que si la tarjeta no tiene la clase "active", se le agregará, y si la tiene, se eliminará. Lo mismo ocurre con la clase "gradient".

10. Después de cambiar las clases, se verifica si la tarjeta actual tiene la clase "active". Si la tiene, se cambia el texto del botón a "See Less" y se ajusta la altura del contenido de texto para mostrar todo el contenido (textContent.style.height = textContent.scrollHeight + "px").

11. Si la tarjeta no tiene la clase "active", se cambia el texto del botón a "See More" y se establece la altura del contenido de texto en un valor específico, en este caso, "100px" (textContent.style.height = "100px").

## Cosas que podes hacer con el codigo para seguir aprendiendo. 

- Podes mejorar el JavaScript.
- Podes agrandar el diseño.
- Podes jugar con la paleta de colores. 
- Podes usar distintas partes en otro codigo.
- Podes mejorarlo. 
- Cambiar el diseño. 
 