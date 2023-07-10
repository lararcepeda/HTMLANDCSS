# Explicando un poquito

![imagen](https://i.pinimg.com/564x/bd/71/a9/bd71a9b95df6de913f3ce43c2ae7a217.jpg)

## Explicando el JavaScript 

```js
const btns = document.querySelectorAll(".btn");

    btns.forEach((btn) => {
      btn.addEventListener("mousemove", function(e){
        const position = btn.getBoundingClientRect();
        const x = e.pageX - position.left - position.width / 2;
        const y = e.pageY - position.top - position.height / 2;

        btn.children[0].style.transform = "translate(" + x * 0.3 + "px, " + y * 0.5 + "px)";
      });
    });

    btns.forEach((btn) => {
      btn.addEventListener("mouseout", function(e){
        btn.children[0].style.transform = "translate(0px, 0px)";
      });
    });
```

Este código es una porción de código JavaScript que se utiliza para crear un efecto de movimiento en los botones de una página web cuando el ratón se mueve sobre ellos.

La porción de código selecciona todos los elementos de la página web con la clase de "btn" y añade dos "EventListeners" a cada uno: uno para detectar cuando el ratón se mueve sobre el botón y otro para detectar cuando el ratón sale del botón.

Cuando el ratón se mueve sobre el botón, la función usa la posición del botón y la posición del ratón para calcular la cantidad de traslación que se debe aplicar al contenido del botón. Esto se logra utilizando las propiedades "pageX" y "pageY" del objeto "event" generado por el evento de movimiento del ratón.

La cantidad de traslación se aplica entonces a la transformación CSS del primer elemento hijo del botón, que suele ser un icono o un texto. La cantidad de traslación se controla mediante un factor de escala de 0.3 para el eje X y 0.5 para el eje Y.

Cuando el ratón sale del botón, la función simplemente restablece la transformación del primer elemento hijo del botón a su posición original.
