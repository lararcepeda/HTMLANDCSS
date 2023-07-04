# EXPLICANDO EL CODGIO 

En el HTML tenemos dos partes de codigo, tenes la parte en donde va a estar todas las estrellas y como van a ser. 
En el otro espacio, vamos a colocar lo que vendria a ser el texto, esta separado en distintos compartenimientos ya que vendria a entender el tema de la animación, para que tenga su tiempo de espacio de uno al otro. 

![imagen](https://64.media.tumblr.com/1934a4d14a4dc01f6d9a0dc57b63a918/e5fe81c4d7142fc0-d2/s400x600/b69ee229b2db62d097d23a6f2d96aef6b8909736.pnj)

## CSS

```CSS
.text{
  z-index: 1;
  color: #fff;
  font-family: "roboto mono", monospace;
  font-size: 100px;
  font-weight: 200;
  display: flex;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  letter-spacing: 5px;
  -webkit-box-reflect: below 1px linear-gradient(transparent, rgba(225, 225, 225, 0.2));
}

.text span:nth-child(1){
  color: #4285f4;
  animation: animText 1s ease-in-out infinite;
}

.text span:nth-child(2){
  color: #ea4335;
  animation: animText 1s ease-in-out infinite;
  animation-delay: 0.8s;
}

.text span:nth-child(3){
  color: #fbbc05;
  animation: animText 1s ease-in-out infinite;
  animation-delay: 1.2s;
}

.text span:nth-child(4){
  color: #34a853;
  animation: animText 1s ease-in-out infinite;
  animation-delay: 1.6s;
}
```

A la clase Text, encontramos los siguientes estilos.
- El z-index: 1: se utiliza para controlar la posicion en el eje Z (profundidad) de un elemento en relación con otros elementos en la pagina. Establecer un valor alto, como el colocado, para el z-index, coloca al elemento por encima de otros elementos con valores más bajos.
- El color viene a ser la letra de fondo, el tipo de letra utilizado, el tamaño de la letra, el peso de la letra.
- Hace que los elementos hijos directos del contenedor sean elementos flexibles (display: flex).
- Position: absolute, se utiliza para controlar el posicionamiento de un elemento en relacion con su elemento primario posicionado (es decir, un elemento primaro que tenga un valor diferente a static en su propiedad position). Cuando colocamos absolute a un elemento se eliminan del flujo normal del documento, lo que significa que no ocuparan espacio en la pagina y no afectaran la posicion de otros elemetos. En su lugar, se posicionan en relacion con su elemento primario posicionado o, si no hay ninguno, en relación con el elemento raíz.
- Coloca un porcentaje entre donde quiere que este, desde arriba y abajo. 
- El transform se utiliza para aplicar transformaciones 2D o 3D a un elemento, se están aplicando varias transformaciones al elemento.
- El espacio de la letra en el medio. 
- -webkit-box-reflect: below 1px linear-gradient(transparent, rgba(225, 225, 225, 0.2)); 
- La propiedad -webkit-box-reflect es una propiedad específica de WebKit (motor de renderizado utilizado en navegadores como Safari y antiguas versiones de Chrome) que permite crear un efecto de reflexión en un elemento.En el caso de -webkit-box-reflect: below 1px linear-gradient(transparent, rgba(225, 225, 225, 0.2)), se está aplicando un efecto de reflexión debajo del elemento. Veamos los detalles de los valores utilizados: below: Indica que la reflexión se coloca debajo del elemento. 1px: Especifica la altura de la reflexión, en este caso, se establece en 1 píxel. linear-gradient(transparent, rgba(225, 225, 225, 0.2)): Define un gradiente lineal que se utiliza como la reflexión. Comienza con un color transparente en el extremo inferior y se desvanece gradualmente en un color semi-transparente (rgba(225, 225, 225, 0.2)).

Los siguientes estilos son todos parecidos, asi que solo explico uno de los que hay, viene a ser las estrellitas. 

- El selector text span:nth-child(1) se utiliza para seleccionar el primer hijo span dentro de un elemento con la clase .text. color: #4285f4;: Establece el color del texto en azul (#4285f4). animation: animText 1s ease-in-out infinite;: Aplica una animación llamada animText al texto. La animación tiene una duración de 1 segundo (1s), se ejecuta con una aceleración y desaceleración suave (ease-in-out) y se repite infinitamente (infinite).

Despues el codigo especifica cuando comienza y termina con los keyfremes. 

```css
.stars-01{
  content: "";
  position: absolute;
  width: 8px;
  height: 8px;
  box-shadow: 100px 200px #FFEB3B, 200px 250px #FF9800, 200px 500px #00BCD4, 300px 300px #009688,
              550px 150px #00BCD4, 550px 300px #2196F3, 350px 500px #FFF, 1750px 150px #00BCD4,
              1000px 400px #673AB7, 650px 450px #03A9F4, 1200px 50px #FF5722, 1100px 450px #673AB7,
              950px 50px #00BCD4, 1100px 500px #03A9F4, 850px 400px #FF9800, 850px 300px #F44336,
              1200px 100px #FF9800, 900px 300px #CDDC39, 1150px 400px #F44336, 1650px 900px #00BCD4,
              650px 600px #FF5722, 350px 600px #009688, 600px 650px #E91E63, 150px 750px #00BCD4,
              1750px 450px #FF5722, 250px 800px #00BCD4, 1800px 1150px #FF9800, 450px 1450px #FF5722,
              1150px 800px #00BCD4, 100px 700px #3F51B5, 350px 650px #FFEB3B, 250px 600px #FF5722,
              1850px 700px #CDDC39, 1650px 600px #FFEB3B, 450px 1050px #673AB7, 1550px 500px #F44336,
              150px 1400px #8BC34A, 800px 800px #9C27B0, 1250px 1950px #9C27B0, 100px 1700px #8BC34A,
              1150px 1350px #E91E63, 1700px 50px #FFF, 1750px 500px #F44336, 300px 1100px #CDDC39,
              350px 1650px #009688, 1700px 1200px #F44336, 450px 800px #FF5722, 2000px 500px #8BC34A,
              350px 1600px #F44336, 1350px 1350px #673AB7, 1100px 1750px #3F51B5, 150px 950px #FFEB3B,
              1600px 1700px #2196F3, 400px 1000px #FF9800, 650px 1050px #4CAF50, 2000px 1650px #00BCD4,
              1100px 700px #9C27B0, 1350px 600px #F44336, 600px 1900px #CDDC39, 1500px 600px #9E9E9E,
              20px 1350px #8BC34A, 850px 1800px #E91E63, 450px 1150px #2196F3, 50px 700px #FF5722,
              100px 1400px #F44336, 1000px 1700px #9C27B0, 250px 600px #FF5722, 1200px 850px #CDDC39,
              1750px 20px #673AB7, 100px 1550px #FFEB3B, 1200px 1650px #3F51B5, 1500px 700px #2196F3,
              1800px 600px #03A9F4, 650px 800px #00BCD4, 700px 600px #00BCD4, 1100px 1350px #F44336,
              900px 550px #FF5722, 1600px 800px #2196F3, 1000px 1100px #F44336, 1650px 1350px #FF5722,
              750px 1050px #FFC107, 1750px 800px #CDDC39, 600px 1650px #F44336, 150px 1550px #673AB7,
              250px 1800px #FFF, 1100px 1700px #FFC107, 800px 1500px #3F51B5, 1100px 1200px #FF5722,
              1450px 1600px #CDDC39, 150px 1400px #FFF, 1200px 1450px #03A9F4, 1800px 1050px #FFF,
              1250px 1300px #CDDC39, 1000px 1000px #4CAF50, 300px 700px #4CAF50, 100px 1250px #9C27B0,
              700px 1750px #00BCD4, 1950px 250px #FFF, 1550px 700px #F44336;
  animation: starsUp 10s linear infinite;
}
```

Estos pequeños estilos se repiten para cada div chico que tenemos, que viene a ser las estrellas. 
Lo primero que hacemos es darle el estilo de content para que nos deje utilizar las animaciones. 
- El content: "", se utiliza ra especificar el contenido que se debe insertar antes del contenido real del elemento seleccionado. Esta propiedad es obligatoria cuando se utliza :before y :after, incluso si no se especifica ningun valor para content. Se especificada para que no se agrege ningun contenido adicional antes del contenido real del elemento.
- Le especificamos el ancho y el largo de nuestras estrellitas. 
- Y el bloque grande viene a especificar varias cosas, El código que has proporcionado define múltiples sombras usando la propiedad box-shadow en CSS. Cada sombra se separa por comas. Define la distancia horizonal desde el elemento al origen de la sombra. Un valor positivo desplaza la sombra hacia la derecha y un valor negativo hacia la izquierda. Define la distancia vertical desde el elemento al origen de la sombra. Un valor positivo desplaza la sombra hacia abajo y un valor negativo hacia arriba. Define el radio de desenfoque de la sombra. Un valor más alto crea una sombra más difusa, mientras que un valor de 0 crea una sombra nítida. Y por urltimo Define el color de la sombra.

```css
offset-x offset-y blur-radius color

```
Y despues los keyframes que abarcan el tiempo que tardan en pasar y cuando. 

## Cosas que podes hacer con el codigo para seguir aprendiendo. 

- Podes agregar el JavaScript.
- Podes agrandar el diseño.
- Podes jugar con la paleta de colores. 
- Podes usar distintas partes en otro codigo.
- Podes mejorarlo. 
- Cambiar el diseño. 
