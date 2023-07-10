# Explicando un poquito 

![imagen](https://i.pinimg.com/564x/af/f5/e0/aff5e019cd2897db29648808d2ed556e.jpg)

## Explicando el JavaScript

```js
const display = document.querySelector(".display");
const buttons = document.querySelectorAll("button");
const specialChars = ["%","*","/","-","+","="];
let output = "";

const calculate = (btnValue) => {
    if(btnValue === "=" && btnValue !== ""){
        output = eval(output.replace("%", "/100"));
    }
    else if(btnValue === "AC"){
        output = "";
    }
    else if(btnValue === "DEL"){
        output = output.toString().slice(0,-1);
    }
    else{
        if(output === "" && specialChars.includes(btnValue)) return;
        output += btnValue;
    }

    display.value = output;
};

document.addEventListener("keydown", (e) => {
    const keyValue = e.key;
    const button = document.querySelector(`button[data-value="${keyValue}"]`);
    if (button) {
        calculate(button.dataset.value);
    }
});

buttons.forEach((button) => {
    button.addEventListener("click", (e) => calculate(e.target.dataset.value));
});
```

Este código es una porción de código JavaScript que se utiliza para crear una calculadora funcional en una página web.

La porción de código selecciona el elemento HTML con la clase de "display", así como todos los botones de la página web. También define una matriz de caracteres especiales para su uso en la lógica de la calculadora.

La función principal es calculate(), que se llama cuando se hace clic en un botón o se presiona una tecla en el teclado. La función toma el valor del botón o la tecla presionada como entrada, y luego realiza una serie de operaciones para calcular el resultado de la operación.

Si el valor del botón o la tecla presionada es "=", la función evalúa la expresión matemática almacenada en la variable "output", reemplazando cualquier carácter "%" con "/100" antes de realizar el cálculo.

Si el valor es "AC", la función restablece la variable "output" a una cadena vacía.

Si el valor es "DEL", la función elimina el último carácter de la cadena "output".

Si el valor es cualquier otro carácter, la función agrega el carácter a la cadena "output", a menos que la cadena esté vacía y el carácter sea un carácter especial.

La función luego actualiza el valor del elemento "display" con el contenido actualizado de la variable "output".

El código también define dos EventListeners: uno para detectar cuándo se presiona una tecla en el teclado, y otro para detectar cuándo se hace clic en un botón. Ambos llaman a la función "calculate()" con el valor correspondiente del botón o la tecla presionada.