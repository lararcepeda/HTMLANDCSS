# Explicando un poco. 

![imagen](https://i.pinimg.com/564x/86/f5/cf/86f5cfe71b3451a0f9a46a7ef00a2ff1.jpg)

```js
window.addEventListener("scroll", () => {
        const indicatorBar = document.querySelector(".scroll-indicator-bar");

        const pageScroll = document.body.scrollTop || document.documentElement.scrollTop;
        const height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
        const scrollValue = (pageScroll / height) * 100;

        indicatorBar.style.width = scrollValue + "%";
    });

    //Responsive navigation menu toggle
    const menuBtn = document.querySelector(".nav-menu-btn");
    const closeBtn = document.querySelector(".nav-close-btn");
    const navigation = document.querySelector(".navigation");

    menuBtn.addEventListener("click", () => {
        navigation.classList.add("active");
    });

    closeBtn.addEventListener("click", () => {
        navigation.classList.remove("active");
    });
```

La primera parte es un evento que se activa cuando el usuario desplaza la página hacia arriba o hacia abajo. Este evento actualiza una barra de indicador de desplazamiento en la página web. La barra de indicador de desplazamiento se actualiza en tiempo real para mostrar el porcentaje de la página que se ha desplazado.

La segunda parte del código es para un menú de navegación en formato responsive. Cuando el usuario hace clic en un botón de menú, aparece una navegación desplegable en la pantalla. Cuando el usuario hace clic en el botón de cierre, la navegación desplegable desaparece. Este menú es útil cuando se visualiza la página en pantallas más pequeñas, como en dispositivos móviles.

