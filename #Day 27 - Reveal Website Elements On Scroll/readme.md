# Explicando un poquito. 

![imagen](https://i.pinimg.com/564x/5e/59/f6/5e59f6c902d53dfca98087733687bd4d.jpg)

## Explicando el JavaScript

```js
</section>

    <script type="text/javascript">
    window.addEventListener('scroll', reveal);

    function reveal(){
      var reveals = document.querySelectorAll('.reveal');

      for(var i = 0; i < reveals.length; i++){

        var windowheight = window.innerHeight;
        var revealtop = reveals[i].getBoundingClientRect().top;
        var revealpoint = 150;

        if(revealtop < windowheight - revealpoint){
          reveals[i].classList.add('active');
        }
        else{
          reveals[i].classList.remove('active');
        }
      }
    }
    </script>
```

Este código es una porción de código HTML y JavaScript que se utiliza para crear un efecto de "revelación" en los elementos de una página web a medida que el usuario se desplaza hacia abajo en la página.

La línea HTML simplemente cierra una sección de la página web.

La porción de código JavaScript comienza con la función reveal(), que se activa cuando el usuario se desplaza por la página. La función selecciona todos los elementos de la página web con la clase "reveal", y luego compara la posición de estos elementos con la posición actual del usuario en la página. Si el elemento está lo suficientemente cerca de la parte superior de la ventana del navegador, se agrega la clase "active" al elemento, lo que activa el efecto de revelación. Si no, se elimina la clase "active".

