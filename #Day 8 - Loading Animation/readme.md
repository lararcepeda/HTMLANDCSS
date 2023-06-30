# Explicando el Codigo.

Vamos directamente al CSS, lo voy a explicar medio rapido ya que en otras entradas tenes más especificado las cosas, y me quiero centrar en el javascript. 

![imagen](https://64.media.tumblr.com/d6c855ae924bcb04d5c0c95979fd5d20/222255b60af912f4-f3/s400x600/471f181e5149600d90dd5115ba9a3d1a56e3cff6.jpg)

## Explicando el CSS

```css
body {
  height: 100vh;
  background-color: #131221;
}
body,
.container,
.overlay {
  display: flex;
  align-items: center;
  justify-content: center;
}
.container {
  position: relative;
  height: 450px;
  width: 350px;
  border-radius: 16px;
  background-color: #fff;
  overflow: hidden;
}
.container.active {
  background-color: #000;
}
.container::before {
  content: "";
  position: absolute;
  height: 650px;
  width: 650px;
  background-image: conic-gradient(transparent, transparent, transparent, #fff);
}
.container.active:before {
  animation: rotate 4s linear infinite;
}
@keyframes rotate {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
.container .overlay {
  position: absolute;
  height: 440px;
  width: 340px;
  font-size: 40px;
  font-weight: 500;
  color: #fff;
  border-radius: 12px;
  background-color: #131221;
}
```

Vamos a dar un pantallaso general.
- Colocamos de manera general el fondo de la pagina y la altura. 
- Los estilos estan puestos para que este todo en el centro. 
- Las lineas que van a representar el fecto de carga estan en escondido para que no se note cuando comienza, y con javascript le colocamos más movimiento, y con el css le agregamos la animación. 

Y lo demas se fue explicando en los otros mds. Vamos al Javascript. 

## JavaScript.

```js
const container = document.querySelector(".container"),
        percent = document.querySelector("#percent");

      let perVal = 0;

      let increament = setInterval(() => {
        perVal++;
        percent.textContent = `${perVal}%`;

        if (perVal == 100) {
          clearInterval(increament);
          container.classList.remove("active");
        }
      }, 100);
```

Primero, se utiliza la función *querySelector()* para seleccionar dos elementos en el documento HTML: uno que tiene la clase *"container"* y otro con el ID *"percent"*. Estos elementos se almacenan en las variables container y percent, respectivamente.

Luego, se definen dos variables más: *perVal* que se inicializa en 0 y increament que contiene un intervalo. El intervalo se ejecutará cada 100 milisegundos y aumentará el valor de perVal en 1 y actualizará el contenido del elemento percent con el nuevo valor de perVal seguido del carácter *'%'*.

El intervalo se ejecutará hasta que perVal llegue a 100. En ese momento, se detiene el intervalo con clearInterval() y se elimina la clase *"active"* del elemento container.

En resumen, este código muestra una animación de carga que aumenta el porcentaje de completado en el elemento percent hasta llegar al 100%, momento en que se detiene la animación y se elimina la clase *"active"* del elemento container.