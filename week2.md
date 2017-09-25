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
    <footer>
    ```

[semantic-tags]: https://learn.shayhowe.com/html-css/getting-to-know-html/

- Decidir entre <article>, <section>, o <div>:
A veces resulta bastante difícil decidir qué elemento - <artículo>, <sección> o <div> - es el mejor elemento para el trabajo basado en su significado semántico. El truco aquí, como con cada decisión semántica, es mirar el contenido.

Los elementos <article> y <section> contribuyen a la estructura de un documento y ayudan a delinear un documento. Si el contenido se agrupa únicamente con fines de estilo y no proporciona valor al esquema de un documento, utilice el elemento <div>.

Si el contenido se agrega al esquema del documento y puede redistribuirse o sindicarse de forma independiente, utilice el elemento <article>.

Si el contenido se agrega al esquema del documento y representa un grupo temático de contenido, utilice el elemento <section>.

- Syndication: contenido interpretable por un motor de contenido, tipo [hAtom 0.1 Microformat](http://microformats.org/wiki/hatom).


