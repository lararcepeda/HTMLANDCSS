# Explicando un poquito. 

Seguimos explicando lo que vendria a ser el HTML. 

![imagen](https://i.pinimg.com/564x/bc/dd/51/bcdd51d76e3f686d5ab659a09b443798.jpg)

## Listas

Se dividen en listas **ordenadas** y **no ordenadas**. Las listas no ordenadas se usan para marcar listas de artículos cuyo orden no es importante. Cada lista desordenada comienza con un elemento < ul > («unordered list») que delimita todos los elementos de la lista. El siguiente paso es delimitar cada artículo de la lista con un elemento <li> («list item»).

```html
<ul>
  <li>leche</li>
  <li>huevos</li>
  <li>pan</li>
  <li>hummus</li>
</ul>
```

Las listas ordenadas son aquellas en las que el orden de los elementos si importa. La estructura de marcado es la misma que para las listas no ordenadas, excepto que debes delimitar los elementos de la lista con una etiqueta < ol > («ordered list»), en lugar de < ul >

```html
<ol>
  <li>Conduce hasta el final de la calle</li>
  <li>Gira a la derecha</li>
  <li>Sigue derecho por las dos primeras glorietas</li>
  <li>Gira a la izquierda en la tercer glorieta</li>
  <li>El colegio está a tu derecha, 300 metros más adelante</li>
</ol>
```

Las lists anidadas:

```html
<ol>
  <li>Pela el ajo y picarlo en trozos gruesos.</li>
  <li>
    Retira las semillas y el tallo del pimiento, y cortarlo en trozos gruesos.
  </li>
  <li>Mete todos los alimentos en un procesador de alimentos.</li>
  <li>Pica todos los ingredientes hasta conseguir una pasta.</li>
  <li>Si deseas un hummus "grueso", procésalo corto tiempo.</li>
  <li>Pica durante más tiempo si se desea obtener un hummus "suave".</li>
</ol>
```

Puede tener sentido anidarlos dentro de su propia lista no ordenada e introducir esa lista.

Justo en este codigo no hay listas, pero en otros si. 