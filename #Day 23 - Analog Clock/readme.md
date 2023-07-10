# Explicando un poco. 

Volvamos a los codigos un ratito. 

![imagen](https://i.pinimg.com/564x/3c/98/8e/3c988e1f5de55be97166a4c6513c25b2.jpg)

```js
function setClock(){
            let now = new Date();
            let hours = now.getHours();
            let minutes = now.getMinutes();
            let seconds = now.getSeconds();

            hrValue = (hours * 30) + (minutes * 6) / 12;
            minValue = minutes * 6;
            secValue = seconds * 6;

            document.querySelector(".hr-hand").style.transform = 
            "rotate(" + hrValue + "deg)";
            document.querySelector(".min-hand").style.transform =
            "rotate(" + minValue + "deg)";
            document.querySelector(".sec-hand").style.transform =
            "rotate(" + secValue + "deg)";
        }

        setInterval(setClock, 1000);
```

La función setClock() obtiene la hora actual utilizando el objeto Date() y calcula el valor de rotación para cada una de las manecillas del reloj. El valor de rotación se basa en la hora actual y se aplica a las manecillas del reloj utilizando la propiedad transform del objeto CSS style.

Luego se llama la función setInterval(), que llama repetidamente la función setClock() cada segundo, haciendo que las manecillas del reloj se actualicen en tiempo real.