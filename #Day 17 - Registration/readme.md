# Explicando un poquito.

Seguimos con el HTML.

![imagen](https://i.pinimg.com/564x/22/f5/f0/22f5f08623a6bb6b69ec08be374d969e.jpg)

## Formateo de texto avanzado

Listas de descripción. El propósito de estas listas es marcar un conjunto de elementos y sus descripciones asociadas, como términos y definiciones, o preguntas y respuestas.

Las listas de descripción utilizan un contenedor diferente al de los otros tipos de listas — < dl > («description list» o lista de descripciones); además, cada término está envuelto en un elemento < dt > («description term» o término a describir), y cada descripción está envuelta en un elemento < dd > («description definition» o definición de descripción). Para redondear esta información veamos un ejemplo:

```html
<dl>
  <dt>soliloquio</dt>
  <dd>
    En las obras dramáticas, corresponde a cuando un personaje se habla a sí
    mismo para representar sus pensamientos o sentimientos internos y, en el
    proceso, transmitirlos a la audiencia (pero no a otros personajes).
  </dd>
  <dt>monólogo</dt>
  <dd>
    En las obras dramáticas, corresponde a cuando un personaje habla de sus
    pensamientos en voz alta para compartirlos con el público y cualquier otro
    personaje presente.
  </dd>
  <dt>aparte</dt>
  <dd>
    En las obras dramáticas, corresponde a cuando un personaje comparte un
    comentario solo con la audiencia para dar efecto cómico o dramático. Suele
    ser un sentimiento, un pensamiento o información adicional.
  </dd>
</dl>
```

### Citas

HTML también dispone de elementos para el marcado de citas; cual elemento utilices depende de si estás marcando la cita como un bloque o como un elemento en línea.

#### Cita en bloque independiente (blockquote)

Si una sección de contenido a nivel de bloque (ya sea un párrafo, varios párrafos, una lista, etc.) se cita en otro lugar, debes envolverla dentro de un elemento < blockquote > para indicarlo, e incluye una URL que apunte a la fuente de la cita dentro de un atributo cite. 

```html
<p>
  El <strong>elemento HTML <code>&lt;blockquote&gt;</code></strong> (o
  <em>elemento HTML de cita en bloque independiente</em>) indica que el texto al
  que delimita es una cita ampliada.
</p>
```

#### Citas en línea

Las citas en línea funcionan exactamente de la misma manera, excepto que usan el elemento < q >. 

```html
<p>
  El elemento de cita — <code>&lt;q&gt;</code> — se
  <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q"
    >utiliza en para citas breves que no requieren saltos de párrafo.</q
  >
</p>
```

### Citas

El contenido del atributo cite suena útil, pero desafortunadamente los navegadores, lectores de pantalla, etc. No hacen mucho con él. No hay forma de hacer que el navegador muestre el contenido de cite sin escribir tu propia solución usando JavaScript o CSS. Si deseas que la fuente de la cita esté disponible en la página, lo debes hacer en el texto a través de un enlace o de alguna otra forma apropiada.

Hay un elemento < cite >, pero está destinado a contener el título del recurso que se cita, p. ej. el nombre del libro. Sin embargo, no hay razón por la que no puedas vincular el texto dentro de < cite > a la fuente de la cita de alguna manera:

```html
<p>
  De acuerdo con
  <a href="https://developer.mozilla.org/es/docs/Web/HTML/Element/blockquote">
    <cite>página de citas en bloque independiente de MDN</cite></a
  >:
</p>

<blockquote
  cite="https://developer.mozilla.org/es/docs/Web/HTML/Element/blockquote"
>
  <p>
    El <strong>elemento HTML <code>&lt;blockquote&gt;</code></strong> (o
    <em>elemento HTML de cita en bloque independiente</em>) indica que el texto
    al que delimita es una cita ampliada.
  </p>
</blockquote>

<p>
  El elemento de cita — <code>&lt;q&gt;</code> — se
  <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q"
    >utiliza en citas breves que no requieren saltos de párrafo.</q
  >
  --
  <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q">
    <cite>página q de MDN</cite></a
  >.
</p>
```

Las citas se escriben en cursiva de forma predeterminada.

### Abreviaturas

Otro elemento bastante común que encontrarás cuando busques en la Web es < abbr > — se usa para envolver una abreviatura o acrónimo, y proporcionar una expansión completa del término incluida dentro de un atributo title. 

```html
<p>
  Usamos <abbr title="Lenguaje de marcado de hipertexto">HTML</abbr> para
  estructurar nuestros documentos web.
</p>

<p>
  Creo que el <abbr title="Reverendo">Rev.</abbr> Green lo hizo en la cocina con
  la motosierra.
</p>
```

Estos saldrán con un aspecto similar a este (la expansión aparecerá en una descripción emergente cuando se coloque el cursor sobre el término):

### Marcar la información de contacto

HTML tiene un elemento para marcar la información de contacto — < address >. Este simplemente envuelve tus datos de contacto.

```html
<address>
  <p>Chris Mills, Manchester, The Grim North, Reino Unido</p>
</address>
```

También

```html
<address>
  <p>
    Chris Mills<br />
    Manchester<br />
    The Grim North<br />
    Reino Unido
  </p>

  <ul>
    <li>Tel: 01234 567 890</li>
    <li>Email: me@grim-north.co.uk</li>
  </ul>
</address>
```
Ten en cuenta que algo como esto también estaría bien, si la página vinculada contuviera la información de contacto:

```html
<address>
  <p>Página escrita por <a href="../authors/chris-mills/">Chris Mills</a>.</p>
</address>
```

### Superíndice y subíndice

En ocasiones, necesitarás utilizar superíndice y subíndice al marcar elementos como fechas, fórmulas químicas y ecuaciones matemáticas para que tengan el significado correcto. Los elementos < sup > y < sub > se ocupan de ello. Por ejemplo

```html
<p>Nací el 25<sup>th</sup> de mayo de 2001.</p>
<p>
  La fórmula química de la cafeína es
  C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>.
</p>
<p>If x<sup>2</sup> es 9, x debe ser igual 3 o -3.</p>
```

### Representación del código informático

Hay una serie de elementos disponibles para marcar código informático usando HTML:

- < code >: Para marcar fragmentos genéricos de código informático.
- < pre >: Para respetar los espacios en blanco (en general, en los bloques de código) — si utilizas la sangría o diversos espacios en blanco consecutivos dentro de un texto, los navegadores los ignorarán y no se mostrarán en la página. Sin embargo, si delimitas el texto con las etiquetas <pre></pre>, los espacios en blanco se representarán de forma idéntica a como se ven en tu editor de texto.
- < var >: Para marcar específicamente nombres de variables.
- < kbd >: Para marcar entradas de teclado (y de otro tipo) en el ordenador.
- < samp >: Para marcar la salida de un programa de ordenador.

```html
<pre><code>var para = document.querySelector('p');

para.onclick = function() {
  alert('¡Guau!, ¡deja de apretar!');
}</code></pre>

<p>
  No debes utilizar elementos de presentación como <code>&lt;font&gt;</code> y
  <code>&lt;center&gt;</code>.
</p>

<p>
  En el ejemplo de JavaScript anterior, <var>para</var> representa un elemento
  de párrafo.
</p>

<p>
  Selecciona todo el texto con <kbd>Ctrl</kbd>/<kbd>Cmd</kbd> + <kbd>A</kbd>.
</p>

<pre>$ <kbd>ping mozilla.org</kbd>
<samp>PING mozilla.org (63.245.215.20): 56 bytes de datos
64 bytes de 63.245.215.20: icmp_seq=0 ttl=40 time=158.233 ms</samp></pre>
```

### Marcar horas y fechas

HTML también proporciona el elemento < time > para marcar horas y fechas en un formato legible por la máquina. Por ejemplo:

```html
<time datetime="2016-01-20">20 Enero 2016</time>
```

¿Por qué es útil esto? Bueno, hay muchas formas diferentes en que los humanos escriben las fechas. La fecha anterior se podría escribir como:

20 Enero 2016
20th January 2016
Ene 20 2016
20/01/16
01/20/16
El 20 del mes que viene
20e Janvier 2016
2016 年 1 月 20 日
... y así sucesivamente ...
Pero estas diferentes formas no las pueden reconocer fácilmente las computadoras — ¿qué pasaría si quisieras tomar automáticamente las fechas de todos los eventos en una página e insertarlas en un calendario? El elemento < time > te permite adjuntar una fecha/hora inequívoca y legible por la máquina para este propósito.

```html
<!-- Fecha simple estándar -->
<time datetime="2016-01-20">20 Enero 2016</time>
<!-- Solo año y mes -->
<time datetime="2016-01">Enero 2016</time>
<!-- Solo mes y día -->
<time datetime="01-20">20 Enero 2016</time>
<!-- Solo tiempo, horas y minutos -->
<time datetime="19:30">19:30</time>
<!-- ¡También puedes hacer segundos y milisegundos! -->
<time datetime="19:30:01.856">19:30:01.856</time>
<!-- Fecha y hora -->
<time datetime="2016-01-20T19:30">7.30pm, 20 Enero 2016</time>
<!-- Fecha y hora con desplazamiento de zona horaria -->
<time datetime="2016-01-20T19:30+01:00"
  >7.30pm, 20 Enero 2016 es 8.30pm en Francia</time
>
<!-- Llamar a un número de semana específico -->
<time datetime="2016-W04">La cuarta semana de 2016</time>
```

## Cosas que podes mejorar de este proyecto. 

- Agregarle JavaScript.
- Agrandar el diseño.
- Cambiar la paleta de colores.
- Mejorar la composicion del codigo. 