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


