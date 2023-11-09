# 2 Elementos semánticos

## 2.1 Algúns elementos para clasificar os contidos

- [`<address>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address): información de contacto do sitio web (cando se atopa dentro dun `<footer>`) ou información de contacto da autora (cando se atopa dentro dun `<article>`); pode incluir redes sociais, email, dirección postal, móbil...
- [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article): ver 2.3.
- [`<aside>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside): contido indirectamente relacionado co contido principal.
- [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer):  o máis usado é coma pé de paxina do sitio web, pero pode ser usado tamén coma pé de páxina dun `<article>`.
- [`<h1>` a `<h6>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements): é de bo gusto usar só 1 `<h1>` por páxina (os responsables de SEO vancho confirmar 😂). Nunca utilizedes os encabezados para darlle tamaño aos títulos (iso é responsabilidade do CSS).
- [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header): o máis usado é coma cabeceira do sitio web, pero pode ser usado tamén coma cabeceira dun `<article>`.
- [`<main>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main): só pode haber **1 por páxina**. Marca aquela área que amplía o tema principal dun documento ou contén a funcionalidade principal dunha aplicación.
- [`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav): o sistema de navegación principal do sitio.
- [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section): ver 2.3.

A lista completa pode ser consultada [aquí](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#content_sectioning)

## 2.2 Algunhas verdade incomodas sobre os `<div>`s (e os `<span>`s)

Un [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div):

- Non significa nada. Non comunica nada como elemento dunha páxina web.
- Non é unha división. Non é unha sección. Non é un elemento que xenere seccións.
- Contén clases e ides CSS e agrupa outros elementos HTML.
- Son útiles para facilitar a aplicación de estilos CSS e para ser usados dende JS.
- [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) é o seu equivalente [_inline_](https://developer.mozilla.org/en-US/docs/Glossary/Inline-level_content) (`<div>` é un elemento [_block_](https://developer.mozilla.org/en-US/docs/Glossary/Block-level_content)).

> **Corolario**: _usade `<div>` como **último recurso**, cando non haxa ningunha outra opción._

## 2.3 `<article>` vs `<section>` vs `<div>`

| `<article>`        | `<section>`          | `<div>`        |
|--------------------|----------------------|----------------|
| Contido sindicado  |  Contido relacionado | Último recurso |
| O contido pode manterse por si mesmo sen ter que relacionarse con nada da páxina, é dicir, conta unha historia por si mesmo | Pode non manterse por si mesmo pero a información está relacionada | Non hai historia e nada está relacionado |
| Pode conter `<header>`, `<footer>`, `<section>` e `<h1>` a `<h6>` | Pode estar contido nun `<article>`.  | Caixa de sastre que agrupa elementos para aplicar CSS ou JS |

> _Cando pensamos nun `<div>` e non atopamos ningún outro elemento mellor, probablemente sexa unha `<section>`._

## 2.4 Máis sobre `<main>`

- O contido de `<main>` debería ser único dentro do documento.
- É unha etiqueta informativa moi útil para os **lectores de pantalla**.
- É un punto de referencia. Favorecer o uso de `<main>` fronte a [ARIA `role="main"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/main_role).
- Cun atributo `id` pode ser o obxectivo do [patrón _"Skip Navigation" ou "Skip to Main Content"_](https://css-tricks.com/how-to-create-a-skip-to-content-link/) que vimos no tema de accesibilidade (`a11y`).
- Os navegadores coma Firefox buscan `<main>` para poder refinar o [Modo Vista de Lectura](https://support.mozilla.org/en-US/kb/firefox-reader-view-clutter-free-web-pages).

## 2.5 `<br>`, 🦆 o parruliño feo 🦆

Cando o **formato do contido é crítico** (por exemplo unha **dirección postal**, un **poema**, ...) pódese utilizar [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br).
