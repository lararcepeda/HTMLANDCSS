# Explicando el Codigo. 

No se como hacer para que la fecha me aparezca cada parte en mayusculas en vez de juev 8 de junio del 2023, me gustaria que diga Juev 8 De Junio del 2023. Si alguien sabe como hacer, me lo comenta. 

Codigo para practicar hay un monton, pero este es el que mas he visto en cuestion de practica. Millones de videos, y ayuda hay para hacerlo por tu cuenta. Decidi copiar algunos estilos para aprender tambien a como hacerlo.

![imagen](https://64.media.tumblr.com/10b002227496801554f7ed31540ec883/ed68d3585ff24a51-56/s400x600/aa43658fa0db5cd664ea86173b6070a9cc63633e.jpg)

## HTML y CSS

En el HTML, que en los anteriores archivos no me centre en explicarlo, en este voy a intentar alargar un poco el archivo. 

```html
<body>

    <div class="digital-clock">
        <i class="uil uil-ellipsis-v dot-menu-btn" id="active-menu"></i>
        <ul class="dot-menu" id="active-menu">
            <li class="menu-item" id="active-menu">
                <span class="clock-format-text" id="active-menu">24-hour format</span>
                <div class="format-switch-btn" id="active-menu" data-format="12"></div>
            </li>
        </ul>
        <div class="time">
            <span class="hours">00</span>
            <span class="dots">:</span>
            <span class="minutes">00</span>
            <div class="right-side">
                <span class="period">AM/PM</span>
                <span class="seconds">00</span>
            </div>
        </div>
        <div class="calendar">
            <span class="month-name">Month</span>
            <span class="day-name">Day</span>
            <span class="day-number">00</span>
            <span class="year">0000</span>
        </div>
    </div>
```

Dentro del body, colocamos un div que va a ser el contenedor principal, colocamos el boton que representa un boton de menu, le colocamos la clase y un Id especifico. 
Armamos una lista desordenada que representa el menu. Tenemos nuevamente clase y un Id. Adentro colocamos un elemento de una lista desordenada, el span viene a representar el formato del relog, 24hs o 12hs. Y el div es el swich para que eso pase.
Cerramos nuestra lista desordenada. Abrimos otro div, para colocamos tres span que va a figurar como los numeros del relog. Adentro del div colocamos otro div, que van a figurar lo que vendria a ser que horario es, si a la tarde o al mediodia, despues los segundos. Despues más abajo es lo mismo pero con los dias, que lo dejamos sin especificar a todo, ya que eso va a ser tocado por codigo. 

Comenzamos con CSS. 

```css
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;

}

body{
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #2e2e44;
}

.digital-clock{
    position: relative;
    color: #fff;
    background: #2d2f41;
    width: 425px;
    padding: 20px 45px;
    box-shadow: 0 5px 25px rgba(14, 21, 37, 0.8);
    border-radius: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}
```

Al principio tenemos al import de la fuente de la letra. Despues tenemos el pequño codigo que es general en todos los codigos, es para hacer que el margin y el padding, generalmente, no este presente. Y cambia el modelo de caja de todos los elementos a border-box, esto significa que el ancho y la altura especificados para un elemento incluiran el relleno y el borde, en lugar de agregarlos al ancho y la altura totales del elemento. Esto facilita el calculo y el control del tamaño real de los elementos. Y por ultimo especifica la fuente de la letra para todos. 

El body, tenemos
- Una minima altura en vh que significa significa Viewport Width (ancho del dispositivo). Funciona como las unidades de porcentaje, especificar 10vw es equivalente a ocupar 10% del ancho visible de la pantalla.
- Justifica el contenido como centro. Recordar que solo se puede usar esta especificacion porque anteriormente se menciono que era display flex, Cuando se establece display: flex en un contenedor, se activa el modelo de diseño flexible (flexbox), lo que permite controlar el posicionamiento y alineación de los elementos hijos dentro del contenedor. La propiedad justify-content se utiliza para alinear los elementos a lo largo del eje principal del contenedor flex. Determina cómo se distribuyen y alinean los elementos en el espacio disponible en el eje principal.
- Centra los elementos secundarios verticalmente (align-items: center) dentro del cuerpo de la pagina. Los elementos se alinearan en el centro eje transversal (verticalmente) y se distribuiran de manera uniforme a lo largo del eje princiapal (horizontalmente).
- Por ultimo damos especificaciones al fondo. 

Con la clase tenemos un par de cositas para explicar 
- Establece la posicion relativa para las tarjetas. Esto permite controlar la posicion de los elementos secundarios dentro de la tarjeta utilizando propiedades de posicion absoluta o relativa (position: relative).
- La propiedad color se utiliza para establecer el color del texto dentro de un elemento. Controla el color de la fuente del texto, como el color de las letras en un párrafo o el color del texto en un encabezado y el background se utiliza para establecer el fondo de un elemento. 
- El padding se utiliza para agregar espacio de relleno alrededor del contenido de un elemento. Controla el espacio entre el borde del elemento y su contenido interno, como texto, imágenes o elementos hijos.
- box-shadow: 0 5px 25px rgba(14, 21, 37, 0.8); Agrega una sombra alrededor de las tarjetas (box-shadow). La sombra se compone de una sombra horizontal de desplazamiento de 0px, una sombra vertical de desplazamiento de 5px, un desenfoque de 25px y un color de sombra especificado en rgba (14, 21, 37, 0.8).
- border-radius: 10px; lo que hace que los bordes de las tarjetas sean redondeados.
- flex-direction: column; La direccion en la que estan colocadas los componenetes, en este caso van a estar en columna. 

```css
.digital-clock:before{
    content: "";
    position: absolute;
    background: linear-gradient(45deg, #24ff6d, #2f93f1, #ff5e9a);
    background-size: 200% 200%;
    top: -5px;
    left: -5px;
    bottom: -5px;
    right: -5px;
    z-index: -1;
    filter: blur(40px);
    animation: glowing 10s ease infinite;
}

@keyframes glowing{
    0%{
        background-position: 0 50%;
    }
    50%{
        background-position: 100% 50%;
    }
    100%{
        background-position: 0 50%;
    }
}

.time{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
}

.hours , .dots , .minutes {
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: 600;
    padding: 0 10px;
    line-height: 125px;
}
```

Cuando algun elemento le agregamos un pseudo- elemento (:) se va a mostrar antes o despues de su contenido real. El :before se utiliza para insertar estilo antes del contenido real de un elemento seleccionado, en este caso agregamos.

- El content: "", se utiliza ra especificar el contenido que se debe insertar antes del contenido real del elemento seleccionado. Esta propiedad es obligatoria cuando se utliza :before y :after, incluso si no se especifica ningun valor para content. Se especificada para que no se agrege ningun contenido adicional antes del contenido real del elemento.
- position: absolute se utiliza para controlar la posición de un elemento en relación con su elemento padre posicionado más cercano o con el documento HTML en su conjunto.
- Y el background, lo unico distinto que tiene gradiente, que hay muchas paginados donde colocas el color que queres y te provee el codigo del gradiente. 
- Ya que tiene position absolute, especifica en donde quiere especificamente donde este en el body. 
- El z-index se utiliza para controlar la posicion en el eje Z (profundidad) de un elemento en relación con otros elementos en la pagina. Establecer un valor alto, como el colocado, para el z-index, coloca al elemento por encima de otros elementos con valores más bajos.
- filter: blur() se utiliza para aplicar un efecto de desenfoque a un elemento HTML. Permite ajustar el nivel de desenfoque de un elemento y crear efectos visuales interesantes. El valor de blur() especifica el radio del desenfoque en píxeles. Cuanto mayor sea el valor, mayor será el desenfoque aplicado. Un valor de 0 significa que no hay desenfoque, mientras que valores más altos crean un desenfoque más pronunciado.
- animation se utiliza para aplicar una animación a un elemento HTML. Permite crear efectos de animación personalizados utilizando keyframes y especificar la duración, el ritmo y la repetición de la animación.
- En este caso, se aplicará una animación llamada "glowing" al elemento < div >. La animación durará 10 segundos, se ejecutará con una función de temporización "ease" y se repetirá infinitamente. Los keyframes definidos en @keyframes glowing especifican los cambios en la opacidad y el sombreado del elemento a lo largo de la animación, creando un efecto de destello.

Lo utlimo que me falta por explicar es el line-height, lo demas se explico arriba, se utiliza para establecer la altura de línea de un elemento de texto. Controla el espacio vertical entre líneas de texto y afecta la altura total de una línea.

```css
.hours , .minutes {
    font-size: 5.5em;
    width: 125px;
}

.dots{
    font-size: 5em;
    color: #929292;
}

.hours{
    background: -webkit-linear-gradient(90deg, #634dff, #5fd4ff);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
}

.minutes{
    background: -webkit-linear-gradient(90deg, #ff5e9a, #ffb960);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
}

.right-side{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    margin-left: 10px;
}
```
- -webkit-text-fill-color: transparent: Cuando se aplica -webkit-text-fill-color: transparent, el texto dentro de un elemento se muestra completamente transparente, lo que significa que no tiene color de relleno visible. Esto es útil cuando se combina con -webkit-background-clip: text para crear el efecto de relleno de texto con un fondo visible a través del texto.
- -webkit-background-clip: text: es un prefijo específico del navegador utilizado para aplicar un efecto de recorte de fondo en el texto. Cuando se utiliza webkit-background-clip: text, se permite que el fondo de un elemento se recorte o muestre solo dentro del área ocupada por el texto. Esto crea un efecto en el que el fondo se muestra a través del texto, dándole un aspecto de "relleno de texto".

```css
.period, .seconds {
    font-size: 1.2em;
    font-weight: 500;
}

.period{
    transform: translateY(-20px);
    background: -webkit-linear-gradient(90deg, #f7b63f, #faf8);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
}

.seconds{
    transform: translateY(16px);
    background: -webkit-linear-gradient(90deg, #24ff6d, #2f93f1);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
}

.calendar{
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1.3em;
    font-weight: 500;
    margin-bottom: 5px;
    background: -webkit-linear-gradient(90deg, #ae4af6, #ff98d1);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
}

.day-name, .day-number {
    margin-left: 8px;
}

.year{
    margin-left: 8px;
}

.dot-menu-btn{
    position: absolute;
    top: 0;
    right: 0;
    margin: 10px;
    color: #efefef;
    font-size: 1.5em;
    cursor: pointer;
}
```

Despues sigue bastante parecido, tiene animaciones que en otros informes esta bastante bien explicado. Pasemos directamente al codigo.

## JAVASCRIPT

```js
      const formatSwitchBtn = document.querySelector(".format-switch-btn");

        formatSwitchBtn.addEventListener("click" , () => {
            formatSwitchBtn.classList.toggle("active");

            var formatValue = formatSwitchBtn.getAttribute("data-format");

            if(formatValue === "12"){
                formatSwitchBtn.setAttribute("data-format", "24");
            }
            else{
                formatSwitchBtn.setAttribute("data-format", "12");
            }
        })

        //Get Current time in javascript

        function Clock (){
            var today = new Date ();

            var hours = today.getHours();
            var minutes = today.getMinutes ();
            var seconds = today.getSeconds ();
            let period = "AM";

            //Set the time period (AM/PM)

            if(hours >= 12){
                period = "PM"
            }

            //Set the 12-hour clocl format

            var formatValue = formatSwitchBtn.getAttribute("data-format");

            if(formatValue === "12"){
            hours = hours > 12 ? hours % 12 : hours;
            }
            //Add the 0 for the values Lower than 10

            if(hours < 10) {
                hours = "0" + hours;
            }

            if(minutes < 10){
                minutes = "0" + minutes;
            }

            if(seconds < 10){
                seconds = "0" + seconds;
            }

            document.querySelector(".hours").innerHTML = hours;
            document.querySelector(".minutes").innerHTML = minutes;
            document.querySelector(".seconds").innerHTML = seconds;
            document.querySelector(".period").innerHTML = period;

        }

        var updateClock = setInterval(Clock, 1000);

        //Get the date in JavaScript

        var today = new Date ();
        const dayNumber = today.getDate();
        const year = today.getFullYear();
        const dayName = today.toLocaleDateString("default", {weekday: "long"});
        const monthName = today.toLocaleDateString("default", {month: "short"});

        document.querySelector (".month-name").innerHTML = monthName;
        document.querySelector(".day-name").innerHTML = dayName;
        document.querySelector(".day-number").innerHTML = dayNumber;
        document.querySelector(".year").innerHTML = year;

        //Javascript for dot menu toggle 

        const dotmenuBtn = document.querySelector(".dot-menu-btn");
        const dotMenu = document.querySelector(".dot-menu");

        dotmenuBtn.addEventListener("click", () => {
            dotMenu.classList.toggle("active");
        });

        document.addEventListener("click", (e) => {
            if(e.target.id !== "active-menu"){
                dotMenu.classList.remove("active");
            }
        });
```
1. El evento click en el botón formatSwitchBtn:

Cuando se hace clic en el botón, se agrega o se quita la clase active al botón mediante classList.toggle("active").
Luego, se obtiene el valor actual del atributo data-format del botón.
Si el valor es "12", se cambia a "24" asignando el nuevo valor al atributo data-format del botón.
Si el valor es distinto de "12", se cambia a "12" asignando el nuevo valor al atributo data-format del botón.

2. La función Clock():

Obtiene la hora actual usando new Date().
Obtiene las horas, minutos y segundos actuales.
Determina si el período es "AM" o "PM" según el valor de las horas.
Si el formato del reloj es "12", se ajustan las horas a un formato de 12 horas.
Agrega un cero delante de los valores de horas, minutos y segundos si son menores que 10.
Actualiza los elementos HTML correspondientes con los valores obtenidos.

3. La variable updateClock:

Utiliza setInterval() para llamar a la función Clock() cada segundo y actualizar el reloj digital.

4. Obteniendo la fecha actual:

Se crea un objeto Date para obtener la fecha actual.
Se obtienen el número del día, el año, el nombre del día y el nombre del mes utilizando los métodos y opciones de toLocaleDateString().
Se actualizan los elementos HTML correspondientes con los valores obtenidos.

5. Eventos de menú de puntos:

Cuando se hace clic en el botón dotmenuBtn, se agrega o se quita la clase active al menú de puntos dotMenu mediante classList.toggle("active").
Se agrega un evento click al documento que verifica si se hace clic en algún lugar que no sea el menú de puntos. Si se hace clic fuera del menú, se quita la clase active del menú de puntos.
En resumen, este código implementa la funcionalidad de un reloj digital, incluyendo el cambio de formato de 12 a 24 horas, y un menú de puntos que se muestra y oculta al hacer clic en un botón.

## Cosas que podes hacer con el codigo para seguir aprendiendo. 

- Podes mejorar el JavaScript.
- Podes agrandar el diseño.
- Podes jugar con la paleta de colores. 
- Podes usar distintas partes en otro codigo.
- Podes mejorarlo. 
- Cambiar el diseño. 