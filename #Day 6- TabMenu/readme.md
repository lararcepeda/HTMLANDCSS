# Explicando el Codigo

En el HTML tenemos secciones que vienen a formar divs para separar cada seccion de la pagina, para colocar las imagenes, el nombre del lugar de la foto, Y el texto, que en este caso yo copie directamente lo que decia en Wikipedia, pero puede ser lo que ustedes vayan colocando. 

![imagen](https://64.media.tumblr.com/159254671637b4d3fe32c521270376ee/0d8fcb98e63afd42-ea/s400x600/3f303322988ef9adcf1373d804d5a77cc3db7fee.jpg)

## HTML y CSS

En el root guardamos información importante que vamos a reutilizar a lo largo del codigo, como los colares y el tema de la sombra. Colocamos la maximación de la pagina en si. Y despues el color de fondo del Body. Y de forma general le damos estilos a la seccion, como la posicion, el margen y la transicion posterior cuando el usuario pase de pais a pais. 

```css
.tab-menu{
    color: var(--text-color);
    list-style: none;
    background: var(--third-color);
    max-width: 800px;
    padding: 10px;
    white-space: nowrap;
    border-bottom: 1px solid var(--third-color);
    border-radius: 50px;
    box-shadow: var(--box-shadow);
    overflow-x: auto;
    user-select: none;
    scroll-behavior: smooth;
}

.tab-menu .dragging{
    scroll-behavior: unset;
    cursor: grab;
}

.tab-menu::-webkit-scrollbar{
    display: none;
}

.tab-nav-bar{
    position: relative;
    margin: 65px 10px 40px 10px;

}

.tab-navigation{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    max-width: fit-content;
    margin: 0 auto;
}

.tab-btn{
    color: var(--text-color);
    display: inline;
    font-size: 1em;
    font-weight: 400;
    margin: 0 2px;
    padding: 10px 20px;
    border-radius: 30px;
    cursor: pointer;
    user-select: none;
    transition: 0.3s ease;
    background: var(--second-color);
}
```

Para el menu tenemos los siguientes estilos 
- Establece en lineas generales el color de la letra, ya que usamos una estiqueta de lista desordenada, comunmente tiene puntos, entonces ponemos list-style: none, para sacar esos puntitos. Coloca el color del fondo. Colocamos un maximo de alto. Colocamos el espacio entre cada componente, es decir un padding, de todos los lados por igual. 
- white-space: nowrap; se utiliza para controlar el manejo del espacio en blanco dentro de un elemento. Se evita que el texto se divida en varias lineas y se obliga a que se muestre en una sola linea sin importar su longitud. 
- El border-radius es para redondear los bordes. 
- border-bottom: 1px solid var(--third-color); se utiliza para establecer un borde en la parte inferior de un elemento. Con las especificaciones que se hicieron ahi se esta configurando un borde de 1 pixel de grosor, de tipo solido y con el color definido en la variable que colocamos en el root. 
- Colocamos la sombra del elemento con box-shadow.
- overflow-x: auto; esta propiedad se utiliza para controlar el comportamiento del desbordamiento horizontal en un elemento. Con el valor auto, se muestra una barra de desplazamiento horizontal solo cuando el contenido del elemento desborda su ancho. Esto permite al usuario desplazarse horizontalmente para ver el contenido oculto.
- user-select: none; Esta propiedad se utiliza para controlar la seleccion de texto por parte del usuario en un elemento. Con el valor none, se desactiva la seleccion del texto, lo que significa que el usuario no podra seleccionar ni resaltar el texto dentro del elemento. 
- scroll-behavior: smooth; esta propiedad se utiliza para controlar la animacion de desplazamiento suave en los enlaces y los metodos de desplazamiento. Con el valor smooth, los desplazamientos hacia los destinos especificados se realizaran de forma suave y animada. 

Vamos con dos estilos importantes para resaltar su significado
- scroll-behavior: unset; Esta propiedad se utiliza para establecer el comportamiento de desplazamiento predeterminado en un elemento. Con el valor unset se restablece el comportamiento de desplazamiento a su valor por defecto, que puede variar segun el navegador. Por lo general, esto implica un desplazamiento instantaneo y sin animación. 
- cursor: grab; Esta propiedad se utiliza para cambiar el cursor del mouse cuando se coloca sobre un elemento. Con el valor grab, el cursor se muestra como una mano cerrada, lo que indica que el usuario puede agarrar y arrastrar el elemento.

Pasemos directamente al tab-navigation y al tab-btn 
- position: relative;: Esta propiedad se utiliza para establecer el posicionamiento de un elemento relativo a su posición original en el flujo normal del documento. Con position: relative;, el elemento se posiciona de acuerdo con las propiedades top, right, bottom y left, pero sin salir del flujo normal del documento.
- display: flex;: Esta propiedad se utiliza para establecer un contenedor de elementos flexibles. Con display: flex;, los elementos hijos dentro del contenedor se distribuyen y se alinean de manera flexible, según las propiedades de flexibilidad y alineación establecidas en el contenedor.
- justify-content: center;: Esta propiedad se utiliza en un contenedor flex para alinear los elementos hijos horizontalmente a lo largo del eje principal. Con justify-content: center;, los elementos se distribuyen de manera equitativa a lo largo del eje principal y se colocan en el centro del contenedor.
- align-items: center;: Esta propiedad se utiliza en un contenedor flex para alinear los elementos hijos verticalmente a lo largo del eje transversal. Con align-items: center;, los elementos se colocan en el centro del eje transversal del contenedor.
- max-width: fit-content;: Esta propiedad se utiliza para establecer el ancho máximo de un elemento en función de su contenido. Con max-width: fit-content;, el ancho máximo del elemento se ajustará al ancho de su contenido, lo que evita que se extienda más allá de lo necesario.
- margin: 0 auto;: Esta propiedad se utiliza para establecer los márgenes de un elemento. Con margin: 0 auto;, se establece un margen superior e inferior de 0 y un margen izquierdo y derecho automáticos, lo que centra horizontalmente el elemento dentro de su contenedor.
- transition: 0.3s ease;: Esta propiedad se utiliza para establecer una transición suave entre los cambios de estilo del elemento. Con transition: 0.3s ease;, se establece una duración de transición de 0.3 segundos y una función de aceleración suave.

```css
.tab-menu .dragging .tab-btn{
    pointer-events: none;
}

.tab-btn:hover{
    background: var(--first-color);
}

.tab-btn.active{
    background: var(--second-color);
    content-visibility: hidden;
}

.left-btn, .right-btn{
    position: absolute;
    color: var(--text-color);
    font-size: 1.8em;
    padding: 10px;
    cursor: pointer;
}

.left-btn{
    left: 0;
    background: linear-gradient(to left, transparent, var(--first-color) 80%);
    border-top-left-radius: 30px;
    border-bottom-left-radius: 30px;
    display: none;
}

.right-btn{
    right: 0;
    background: linear-gradient(to right, transparent, var(--first-color) 80%);
    border-top-right-radius: 30px;
    border-bottom-right-radius: 30px;
}

.tab-content{
    position: relative;
    display: flex;
    justify-content: center;
    width: 100%;
}
```

- El contenido de la visibilidad esta en escondido ya que con javascript hacemos que eso se cambie a visible.
- Despues todo lo demas, esta explicado más arriba, o los encontras en mds para antiguos. 

```css
.tab{
    position: absolute;
    top: 0;
    right: auto;
    bottom: 0;
    left: auto;
    max-width: 1100px;
    padding: 15px 50px;
    transform: translateX(25px);
    content-visibility: hidden;
    opacity: 0;
}

.tab.active{
    transform: translateX(0);
    content-visibility: visible;
    opacity: 1;
    transition: 1s ease;

}

.tab .row{
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 50px 0;
    gap: 30px;
}


.tab .img-card{
    position: relative;
    width: 450px;
    max-width: 450px;
    border-radius: 20px;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: var(--box-shadow);
}

.tab .img-card img {
    width: 100%;
}

.right-column{
    max-width: 800px;
}

.info .city .info .description p{
    color: var(--text-color);
    margin-bottom: 10px;
}

.info .city {
    font-size: 2em;
}

.country{
    color: var(--third-color);
    font-size: 5em;
    font-weight: 700;
    text-align: center;
    text-shadow: var(--text-shadow);

}

@media screen and (max-width: 1050px) {
    section{
        margin: 0 0px;
    }
    .tab-nav-bar{
        margin: 65px 20px 40px 25px;
    }
    .tab{
        padding: 15px 25px;
    }
    .tab .row{
        flex-direction: column;
    }
    .tab .img-card{
        width: auto;
        max-width: 600px;
    }
    .country{
        font-size: 10vw;
        padding-bottom: 50px;
    }
}
```

- Lo unico que hay más adelante serian las medidas de cuando la pantalla se vuelva más chica. 

## JAVASCRIPT

```js
const btnLeft = document.querySelector(".left-btn");
const btnRight = document.querySelector(".right-btn"); 
const tabMenu = document.querySelector(".tab-menu");

const InconVisibility = () => {
    let scrollLeftValue = Math.ceil(tabMenu.scrollLeft);
    console.log( "1.", scrollLeftValue);

    let scrollableWidth = tabMenu.scrollWidth - tabMenu.clientWidth; 
    console.log( "2.", scrollableWidth);

    btnLeft.style.display = scrollLeftValue > 0 ? "block" : "none";
    btnRight.style.display = scrollableWidth > scrollLeftValue ? "block" : "none";
};

btnRight.addEventListener("click", () => {
    tabMenu.scrollLeft += 150;
    InconVisibility();

    setTimeout(() => InconVisibility(), 50);
});

btnLeft.addEventListener("click", () => {
    tabMenu.scrollLeft -= 150;
    InconVisibility();

    setTimeout(() => InconVisibility(), 50);
});

window.onload = function(){
    btnRight.style.display = tabMenu.scrollWidth > tabMenu.clientWidth || 
    tabMenu.scrollWidth >= window.innerWidth ? "block" : "none";
    btnLeft.style.display = tabMenu.scrollWidth >= window.innerWidth ? "" : "none";
};

window.onresize = function(){
    btnRight.style.display = tabMenu.scrollWidth > tabMenu.clientWidth || 
    tabMenu.scrollWidth >= window.innerWidth ? "block" : "none";
    btnLeft.style.display = tabMenu.scrollWidth >= window.innerWidth ? "" : "none";

    let scrollLeftValue = Math.round(tabMenu.scrollLeft);

    btnLeft.style.display = scrollLeftValue > 0 ? "block" : "none"; 
};

let activeDrag = false;

tabMenu.addEventListener ("mousemove", (drag) => {
    if(!activeDrag) return;
    tabMenu.scrollLeft -= drag.movementX;
    InconVisibility();
    tabMenu.classList.add("dragging");
}); 

document.addEventListener("mouseup", () => {
    activeDrag = false;
    tabMenu.classList.remove("dragging");
});

tabMenu.addEventListener ("mousedown", () => {
    activeDrag = true;
});

//JavaScript to view tab contents on click tab buttons

const tabs = document.querySelectorAll(".tab");
const tabBtns = document.querySelectorAll(".tab-btn");

const tab_Nav = function(tabBtnClick){
    tabBtns.forEach((tabBtn) => {
        tabBtn.classList.remove("active");
    });

    tabs.forEach((tab) => {
        tab.classList.remove("active");
    });

    tabBtns[tabBtnClick].classList.add("active");
    tabs[tabBtnClick].classList.add("active");

};

tabBtns.forEach((tabBtn, i) => {
    tabBtn.addEventListener("click", () => {
        tab_Nav(i);
    }); 
});
```

Primero, el código define tres constantes utilizando la función *querySelector* de JavaScript para seleccionar elementos HTML específicos en la página. Uno de estos elementos es la lista de pestañas que se desplazará, y los otros dos son los botones *"izquierda"* y *"derecha"* que se utilizan para desplazarse por la lista.

Luego, se define una función llamada *InconVisibility*, que se utiliza para determinar si los botones de desplazamiento deben estar visibles en función de la posición actual de la lista. La función establece la *propiedad display* de los botones en *"block"* o *"none"* dependiendo de si es posible desplazarse más a la izquierda o la derecha de la lista.

Después, se agregan dos escuchadores de eventos a los botones de desplazamiento. Cuando se hace clic en uno de los botones, se utiliza la propiedad *scrollLeft* de la lista para desplazarse a la izquierda o a la derecha. La función *InconVisibility* también se llama para asegurarse de que los botones de desplazamiento estén visibles después de hacer clic en un botón.

Además, se agrega un escuchador de eventos a la ventana, que detecta cuando se carga la página y ajusta el estado visible de los botones de desplazamiento en consecuencia. También se agrega un escuchador de eventos que detecta cuando se cambia el tamaño de la ventana y ajusta el estado visible de los botones de desplazamiento en consecuencia.

Finalmente, el código define una función para cambiar el contenido de la pestaña cuando se hace clic en uno de los botones de pestaña. La función agrega la clase *"active"* al botón de pestaña y a la pestaña correspondiente para mostrar el contenido de la pestaña seleccionada.