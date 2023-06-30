# Explicando el Codigo.

Hay un gif e imagenes con el mismo nombre en la carpeta para observar el final. 
Pequeño codigo como para practicar y para entender ciertas cositas. 

![imagen](https://64.media.tumblr.com/82ebf85fa130574be12f3c2160c3aef2/86989c81f3fdb3fb-ae/s1280x1920/50f4f04d5336eb3a1aa9d4b53e5a949a5add5a80.jpg)

## HTML y CSS

Al principio tenemos el import donde esta las fuentes. Despues tenemos este pedacito de codigo que dice

```css
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family:'Poppins', sans-serif;
}
```

El pequeño fragmente de css recientemente marcado, selecciona todos los elementos de la pagina y aplica las siguientes reglas. 
- Establece el margen (margin: 0) exterior de todos los elementos en 0. Esto asegura que no haya ningun espacio en blanco adicional alrededor de los elementos. 
- Establece el relleno interno de todos los elementos en 0 (padding: 0). Esto asegura que no haya ningún espacio en blanco adicional dentro de los elementos.
- Cambia el modelo de caja de todos los elementos a border- box, esto significa que el ancho y la altura especificados para un elemento incluiran el relleno y el borde, en lugar de agregarlos al ancho y la altura totales del elemento. Esto facilita el calculo y el control del tamaño real de los elementos. 
- Por ultimo establece la fuente principal para todos los elementos de la pagina. En este caso, se establece la fuente Poppins. 

```css
body{
    min-height: 100vh;
    background: #15151c;
}

.curso{
    z-index: 99999;
    position: fixed;
}

.curso .click-animation{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Al elemento Body se coloca ciertos estilos que establecen:
- Establece la altura minima del cuerpo de la pagina en al menos el 100 de la altura de la ventana (vh significa viesport height o en español, altura de la ventana). Esto asegura que el cuerpo ocupe al menos toda la altura visible de la ventana del navegador, lo que evita que el contenido se recorte o se solape con otros elementos.
- Establece el color del fondo del cuerpo de la pagina en negro (#15151c), lo que significa que el fondo sera de color negro (background).

A la clase Cursor le agregamos estilos que establecen:
- El z-index: 99999: se utiliza para controlar la posicion en el eje Z (profundidad) de un elemento en relación con otros elementos en la pagina. Establecer un valor alto, como el colocado, para el z-index, coloca al elemento por encima de otros elementos con valores más bajos. 
- Y el position marca para controlar el tipo de posicionamiento de un elemento. Al establecer fixed, le estamos diciendo al elemento que se posicione de manera fija en relacion con la ventana del navegador. Esto significa que el elemento permanecera en la misma posicion incluso cuando se desplace la pagina. 

Para la clase click-animation establecen los siguientes estilos: 
- Establece la posicion relativa para las tarjetas. Esto permite controlar la posicion de los elementos secundarios dentro de la tarjeta utilizando propiedades de posicion absoluta o relativa (position: relative).
- Hace que los elementos hijos directos del contenedor sean elementos flexibles (display: flex).
- Centra los elementos flexibles horizontalmente dentro del contenedor (justify-content: center).
- Centra los elementos flexibles verticalmente dentro del contenedor (align-items: center).

```css
.curso .click-animation .shape{
    position: absolute;
    opacity: 0;
}

.curso .click-animation .shape.circule.big{
    width: 40px;
    height: 40px;
    border: 2px solid #4fb4f8;
    border-radius: 50%;
}

.curso .click-animation .shape.circule.small{
    width: 20px;
    height: 20px;
    border: 1px solid #2fb4f8;
    border-radius: 50%;
}
```

Cosas para aclarar de este codigo:
- Position: absolute, se utiliza para controlar el posicionamiento de un elemento en relacion con su elemento primario posicionado (es decir, un elemento primaro que tenga un valor diferente a static en su propiedad position). Cuando colocamos absolute a un elemento se eliminan del flujo normal del documento, lo que significa que no ocuparan espacio en la pagina y no afectaran la posicion de otros elemetos. En su lugar, se posicionan en relacion con su elemento primario posicionado o, si no hay ninguno, en relación con el elemento raíz.
- Opacity: 0, se utiliza para controlar la opacidad de un elemento, es decir, la transparecencia del elemento. Cuando se establece opacity: 0;, el elemento se vuelve completamente transparente, es decir, no es visible en absoluto. Un valor de 0 indica que el elemento es totalmente transparente, mientras que un valor de 1 indica que el elemento es totalmente opaco y completamente visible.
- Width y Height: vendria a ser el alto  el ancho de un elemento. Depende de cuanto espacio va a tomar de la pagina. 
- border: 2px solid #4fb4f8: se utiliza para establecer el estilo de borde de un elemento. Aca se estan estableciendo 2px de ancho del borde, solid especifica el estilo del borde como una linea solida (hay otros bordes para definir que son de borde disponibles, como dotted (punteado), dashed (guión), double (doble línea), entre otros), y el color definde exactamente que color va a hacer el borde. 
- Border-radius: se utiliza para establecer el radio de las esquinas redondeadas de un elemento con bordes. Permite darle al borde del elemento una apariencia suave y redondeada en lugar de tener esquinas afiladas y cuadradas. 

```css
.curso.active .click-animation .shape.circule{
    animation: click-animation-circule 3s ease-out infinite;
}

@keyframes click-animation-circule {
    0%{
        opacity: 0;
    }
    5%{
        opacity: 1;
    }
    30%{
        opacity: 0;
        transform: scale(3);
    }

}

.curso .click-animation .shape.triangle.yellow{
    border-style: solid;
    border-width: 0 5px 10px 5px;
    border-color: transparent transparent #f9de2d transparent;
}

.curso.active .click-animation .shape.triangle.yellow{
    animation: click-animation-triangle-yellow 3s ease-out infinite;
}
```

Aca tenemos muchas cositas nuevas para analizar. Aca tenemos reglas para animaciones. 
- Animation: establece el nombre de la animación que tiene una duración de 3 segundos, una funcion de remporizacion de salida suave (ease-out), y se repite infinitamente (infinite)
- Los keyframes establecen las reglas de esa animacion, define en porcentajes desde el 0 al 30, especifica que en el 0% el elemento sea completamente transparente, despues en el 5% tiene una opacidad completamente opaco. Y el final de la secuencia, nos encontramos con una opacidad en 0, pero la propiedad transform establece que agrande su tamaño tres veces de lo original.
- Despues establecemos estilo a los triangulos amarillos, establece un estilo de borde con diferentes anchos y colores para crear una forma triangular amarilla.
- Y volvemos a la animacion que es lo mismo. 

```css
@keyframes click-animation-triangle-yellow {
    0%{
        opacity: 0;
    }
    5%{
        opacity: 1;
    }
    40%{
        opacity: 0;
        transform: scale(2.5) translate(50px, -50px) rotate(360deg);
    }
}

.curso .click-animation .shape.triangle.green{
    border-style: solid;
    border-width: 0 3.5px 7px 3.5px;
    border-color: transparent transparent #47eda0 transparent;
}

.curso.active .click-animation .shape.triangle.green{
    animation: click-animation-triangle-green 3s ease-out infinite;
}


@keyframes click-animation-triangle-green {
    0%{
        opacity: 0;
    }
    5%{
        opacity: 1;
    }
    40%{
        opacity: 0;
        transform: scale(2.5) translate(20px, 50px) rotate(360deg);
    }
}

.curso .click-animation .shape.disc{
    width: 8.5px;
    height: 8.5px;
    background: #d563f8;
    border-radius: 50%;
}

.curso.active .click-animation .shape.disc{
    animation: click-animation-disc 3s ease-out infinite;
}


@keyframes click-animation-disc {
    0%{
        opacity: 0;
    }
    5%{
        opacity: 1;
    }
    40%{
        opacity: 0;
        transform: scale(2) translate(-70px, -30px);
    }
    
}
```

Aca le vamos a dar estilo a la animacion de los triangulos cuando hacemos click con el mouse, y las demas formas. Y com hacer para repetir. Solo explico lo que no esta repetido. 
- transform: scale(2.5) translate(50px, -50px) rotate(360deg): se utiliza para aplicar transformaciones 2D o 3D a un elemento, se están aplicando varias transformaciones al elemento. 

Veamos qué significan cada una de ellas:
- scale(2.5): Esta transformación escala el elemento en ambos ejes (horizontal y vertical) mediante un factor de escala de 2.5. Esto hace que el elemento se agrande en un 250% de su tamaño original.

- translate(50px, -50px): Esta transformación desplaza el elemento en el plano 2D. El primer valor, 50px, especifica el desplazamiento horizontal hacia la derecha, y el segundo valor, -50px, especifica el desplazamiento vertical hacia arriba. En este caso, el elemento se desplaza 50 píxeles a la derecha y 50 píxeles hacia arriba.

- rotate(360deg): Esta transformación rota el elemento en el plano 2D alrededor de su punto de origen. El valor 360deg indica una rotación completa de 360 grados, lo que significa que el elemento girará en sentido horario hasta volver a su posición original.
Lo demas esta explicado arriba.

```css
section{
    color: #fff;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    flex-direction: column;
    padding: 0 200px;
}

.home h1{
    font-size: 2.5em;
    margin-bottom: 10px;
}

.home p{
    font-size: 1em;
}
```

Aca tenemos los estilos para el texto del medio. Establece en fomra general, el color, la altura minima, el tamaño de la letra tanto como el titulo como para el parrafo. Despues el display flex, emplicado arriba que significa. Justify content tambien. 
- Flex-direction: column,  se utiliza para establecer la dirección principal en la que se colocan los elementos flexibles en un contenedor flex. Cuando se establece flex-direction: column;, los elementos flexibles se colocan en una columna de arriba a abajo. Esto significa que se apilan verticalmente, uno debajo del otro, en el orden en que aparecen en el código HTML.
- El padding es una propiedad CSS que se utiliza para agregar espacio entre el contenido de un elemento y su borde. Permite ajustar el espacio interno dentro del borde de un elemento, creando un espacio de separación entre el contenido y el borde.

## JAVASCRIPT

```JS
const cursoAnimation = document.querySelector(".curso");
    const cursos = document.querySelectorAll(".curso");

    document.addEventListener("mouseover", (e) => {

        let x = e.clientX;
        let y = e.clientY;

        cursoAnimation.style.top = y + "px";
        cursoAnimation.style.left = x + "px";

        cursos.forEach((curso) => {
            curso.classList.add("active");

            function removeCursoActive(){
                curso.classList.remove("active"); 
            }
            
            setTimeout(removeCursoActive, 1000);
        })

        let cursoClone = cursoAnimation.cloneNode(true);
        document.querySelector("body").appendChild(cursoClone);

        setTimeout(() => {
            cursoClone.remove();
        }, 1000);

    });
```

1. Se selecciona el primer elemento con la clase .curso y se asigna a la variable cursoAnimation.
2. Se seleccionan todos los elementos con la clase .curso y se asignan a la variable cursos.
3. Se agrega un evento mouseover al documento que se activa cuando el cursor del mouse se mueve sobre el documento.
4. Dentro del controlador de eventos, se obtienen las coordenadas x e y del cursor del mouse en relación con la ventana del navegador.
5. Se actualizan las propiedades top y left del estilo del elemento cursoAnimation para posicionarlo en las coordenadas x e y.
6. Se itera sobre todos los elementos con la clase .curso y se les agrega la clase active, lo que activa una animación o efecto visual en esos elementos.
7. Se define una función llamada removeCursoActive que se utiliza para eliminar la clase active de un elemento .curso.
8. Se utiliza la función setTimeout para llamar a removeCursoActive después de un segundo (1000 milisegundos) y así eliminar la clase active de los elementos .curso.
9. Se clona el elemento cursoAnimation utilizando el método cloneNode y se asigna a la variable cursoClone.
10. Se agrega el elemento clonado cursoClone al final del elemento body del documento.
11. Se utiliza setTimeout para programar la eliminación del elemento clonado cursoClone después de un segundo (1000 milisegundos).