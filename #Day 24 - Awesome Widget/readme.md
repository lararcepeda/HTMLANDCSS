# Explicando un poco.

Llegando al final del proyecto se me acortaron un poco la información. 
Pero ahora empezaria con la carpeta de JavaScript. Y a medida que tenga más tiempo ire completando los demas readme con más información. 

![imagen](https://i.pinimg.com/564x/a0/4a/6e/a04a6e08a9a76cbaf6e9eee8bda5383c.jpg)

```js
$('.count').each(function(){
			$(this).prop('Counter',0).animate({
				Counter: $(this).text()
			}, {
				duration:4000,
				easing:'swing',
				step: function(now){
					$(this).text(Math.ceil(now));
				}
			});
		});
```

Este código es una función de jQuery que se utiliza para animar el recuento de números en una página web. En particular, esta función se encarga de contar el número de elementos con la clase "count", y luego anima el valor de estos elementos hasta que llegan al número final que se indica en el HTML.

La función "each" itera sobre cada elemento con la clase "count" y utiliza la función "prop" para establecer el valor del contador en 0. Luego, la función "animate" se encarga de incrementar el valor del contador desde 0 hasta el valor final indicado en el HTML, durante un período de tiempo de 4 segundos.

La función "step" se utiliza para actualizar el valor del contador en tiempo real durante la animación, y el método "text" se utiliza para actualizar el texto del HTML con el valor actualizado del contador.

En resumen, este código se utiliza para crear una animación de recuento de números en una página web.