## Full Stack Web Development Bootcamp @Otoño2017

## ~ 20170925

### HTML
- Block-level vs. inline elements: [[enlace]][block-vs-inline]
    + Un elemento de tipo **block-level** siempre empieza en una nueva linea y toma todo el ancho disponible (se agranda hasta la izquierda y derecha tanto como puede). P.e.:
    ```html
    <div>
    <h1>
    <p>
    <ul>
    <ol>
    <li>
    ...
    ```
    + Un elemento **inline** no empieza en una linea nueva y sólo toma el ancho que necesita. P.e:
    ```html
    <span>
    <a>
    <em>
    <strong>
    <small>
    <img>
    <input>
    ...
    ```

[block-vs-inline]: http://www.html5-tutorials.org/html-basics/block-inline-elements/

- Semantic tags: [[enlace]][semantic-tags]
    ```html
    <header>
    <nav>
    <section>
    <article>
    <aside>
    <hgroup>
    <footer>
    <address>
    ```

[semantic-tags]: https://learn.shayhowe.com/html-css/getting-to-know-html/

- Decidir entre <code>article</code>, <code>section</code>, o <code>div</code>:

A veces resulta bastante difícil decidir qué elemento - <code>artículo</code>, <code>sección</code> o <code>div</code> - es el mejor elemento para el trabajo basado en su significado semántico. El truco aquí, como con cada decisión semántica, es mirar el contenido.

Los elementos <code>article</code> y <code>section</code> contribuyen a la estructura de un documento y ayudan a delinear un documento. Si el contenido se agrupa únicamente con fines de estilo y no proporciona valor al esquema de un documento, utilice el elemento <code>div</code>.

Si el contenido se agrega al esquema del documento y puede redistribuirse o sindicarse de forma independiente, utilice el elemento article>.

Si el contenido se agrega al esquema del documento y representa un grupo temático de contenido, utilice el elemento <code>section</code>.

- **Aside**:

El elemento <code>aside</code> contiene contenido, como barras laterales, inserciones o breves explicaciones, que está tangencialmente relacionado con el contenido que lo rodea. Cuando se utiliza dentro de un elemento <code>article</code>, por ejemplo, el elemento <code>aside</code> puede identificar el contenido relacionado con el autor del artículo.

Podemos instintivamente pensar en un elemento <code>aside</code> como un elemento que aparece a la izquierda o a la derecha de una página. No obstante, debemos recordar que todos los elementos estructurales, incluido el elemento <code>aside</code>, son elementos a nivel de bloque y, como tales, aparecerán en una nueva línea, ocupando el ancho total disponible de la página o del elemento que son anidados dentro, también conocido como su elemento padre.

- Syndication: contenido interpretable por un motor de contenido, tipo [hAtom 0.1 Microformat](http://microformats.org/wiki/hatom).

## ~ 20170926

### CSS

- Specifity ~ prioridad en la selección: inline styles, selector por id, selector por clase, selector por atributo, por pseudo-clase, por elemento y pseudo-elemento. [enlace](https://specificity.keegan.st/)
    + Selector por id > selector por clase > selector por atributo.
    + Para la misma prioridad, el último tiene mayor prioridad. En este caso será rojo:
        ```css
        .class1 { color: black; }
        .class2 { color: red; }
        ```
    + Para tener prioridad sobre todo, usar <code>!important</code>.

- Type selectors: <code>div</code>, class selectors: <code>.awesome</code>, id selectors: <code>#shayhowe</code>.

- Selectors:
    + [w3.org](https://www.w3.org/TR/css3-selectors/#selectors).
    + [w3schools](https://www.w3schools.com/CSS/css_pseudo_elements.asp).

- Shorthand properties: [enlace](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties).

- Units: [enlace](https://www.w3schools.com/CSSref/css_units.asp).
    + Relativos: em, ex, ch, rem, vw, vh, vmin, vmax, %.
    + Absolutos: cm, mm, in, px, pt, pc.

- Box model:
    + width, height, padding, margin, border.
    + box-sizing: content-box | **border-box** | initial | inherit;
    <br>La propiedad de <code>box-sizing</code> se utiliza para alterar el modelo de caja CSS predeterminado utilizado para calcular el ancho y la altura de los elementos.

- Position: [enlace](http://www.barelyfitz.com/screencast/html-training/css/positioning/), [gráfico](images/positioning_elements.png)
    + position: static    ~ por defecto todos...
    + position: relative  ~ respecto su posición natural.
    + position: fixed     ~ relativo al viewport.
    + position: absolute  ~ relativo al elemento posicionado padre (cuyo position != static).
    + position: sticky    ~ relativo a la posición del scroll.
    + float: right | left; [enlace](https://www.w3schools.com/Css/css_float.asp)
    <br>Elementos después de un elemento <code>float</code> flotarán alrededor de él. Para evitar esto, utilizar la propiedad <code>clear</code>.

- Tricks:
  + [centrado de elementos.](https://css-tricks.com/centering-css-complete-guide/)
  + [más de centrado de elementos.](https://devcode.la/tutoriales/como-centrar-un-div-con-css/)

- Media querys:
  ```css
  /* default styles here for older browsers.
     I tend to go for a 600px - 960px width max but using percentages
  */
  @media only screen and (min-width:960px){
    /* styles for browsers larger than 960px; */
  }
  @media only screen and (min-width:1440px){
    /* styles for browsers larger than 1440px; */
  }
  @media only screen and (min-width:2000px){
    /* for sumo sized (mac) screens */
  }
  @media only screen and (max-device-width:480px){
    /* styles for mobile browsers smaller than 480px; (iPhone) */
  }
  @media only screen and (device-width:768px){
    /* default iPad screens */
  }
  /* different techniques for iPad screening */
  @media only screen and (min-device-width: 481px) and (max-device-width: 1024px) and (orientation:portrait) {
    /* For portrait layouts only */
  }
  @media only screen and (min-device-width: 481px) and (max-device-width: 1024px) and (orientation:landscape) {
    /* For landscape layouts only */
  }
  ```

- CSS reset: cross-browser compatibility.
    + [Eric Meyer’s reset](http://meyerweb.com/eric/tools/css/reset/).
    + [Normalize.css](http://necolas.github.io/normalize.css/).

## ~ 20170927

- Flexbox: La idea principal detrás de <code>flex layout</code> es dar al contenedor la capacidad de alterar sus artículos (anchura, altura y orden) para llenar mejor el espacio disponible.
Un contenedor <code>flex</code> expande los elementos para llenar el espacio libre disponible o los encoge para evitar el desbordamiento.
[enlace](https://scotch.io/tutorials/a-visual-guide-to-css3-flexbox-properties)
[cheatsheet](http://apps.workflower.fi/css-cheats/?name=flexbox)

## ~20170928

### SASS

- extend (placeholders)
- include (mixins)
