# 1 Notas básicas sobre HTML

## 1.1 O proceso de deseño

1. **UX**: identificación de problemas e búsqueda (investigación) de solucións.
2. **UI + accesibilidade (`a11y`)**: crea unha interface accesible que resolva os problemas tomando como punto de partida a **UX**. Comproba canto antes e con frecuencia que vas polo bo camiño.
3. **Contido**: conta unha historia sobre o problema e a súa solución tomando como punto de partida a **UX**.
4. **HTML**: identifica a estrutura e compoñentes do **contido** (listas, ligazóns, encabezados, ...). **Non te preocupes pola apariencia do producto**.
5. **CSS**: fai que o **contido** en **HTML** _"quede bonito"_. Podes engadir novo **HTML** xuizosamente, só para facilitar a tarefa ás clases CSS e para agrupar elementos para aplicarlles estilos.

## 1.2 Vocabulario HTML

### 1.2.1 Que é o HTML

O HTML:

- Identifica os **elementos** dunha páxina web.
- **Non** é responsábel da apariencia da páxina.
- Inclúe varios *tesouros ocultos* para a `a11y`, SEO e incluso Intelixencia Artificial (AI).
- É o que nos permite pasar de **contido** a **código**.

### 1.2.2 😈 vs 👼

O [😈😈😈 do HTML](https://www.htmhell.dev/) fronte ao [👼👼👼 do HTML](https://www.htmhell.dev/tips/) (⚠️ é discutíbel ⚠️)

### 1.2.3 Exemplo HTML + JS (React)

☢️ O código é equivalente ☢️

**Inferno** 😈😈😈

```html
<div role="list">
  <div class="row">
    <span class="dot"></span>
    <div class="li" role="listitem">
       {this.props.descOne}
    </div>
  </div>
  <div class="row">
    <span class="dot"></span>
    <div class="li" role="listitem">
           {this.props.descTwo}
    </div>
  </div>
  <div class="row">
    <span class="dot"></span>
    <div class="li" role="listitem">
          {this.props.descThree}
     </div>
  </div>
</div>
```

**Ceo** 👼👼👼

```html
<ol class="list">
  <li>{this.props.descOne}</li>
  <li>{this.props.descTwo}</li>
  <li>{this.props.descThree}</li>
</ol>
```

> - _Fonte: [Cleaner More Accessible Code With HTML by Mark Steadman](https://dev.to/steady5063/cleaner-more-accessible-code-with-html-1ghd)_

### 1.2.4 Documentación de referencia para os elementos

Lista con todos os _tags_ ou _etiquetas_ HTML (incluidos os obsoletos e _deprecated_):

- [MDN: elementos HTML](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

### 1.2.5 Máis `<meta>`data da que quixeras saber

⚠️ É unha curiosidade ⚠️

- [The Open Graph protocol @ Facebook](https://ogp.me/)

## 1.3 Temos que falar das listas

### 1.3.1 Tipos de listas

Dende o **punto de vista do contido** podemos considerar **4 tipos de listas** en HTML.

#### 1.3.1.1 `<ul>`

As [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) son listas non ordenadas para simplemente... listar cousas.

Cada item da lista é un [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li).

#### 1.3.1.2 `<ol>`

As [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) son listas ordenadas ou numeradas para dar indicacións pautadas, _os 20 filmes do 2023_, etc.

Como nas `<ul>`s, cada item da lista é un `<li>`.

#### 1.3.1.3 `<dl>`

As [`<dl>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl) son _listas de descrición_ (antes coñecidas coma _lista de definición_) para emparellar conceptos (_key-value pairs_) coma termo ➡ definición, categoría ➡ descrición, etc.

- O **termo da descrición** vai nun [`<dt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dt) (sería a parte da _key_).
- Os **detalles da descrición** van nun [`<dd>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dd) (sería a parte do _value_).

Un **exemplo** de lista de descrición 🤓

```html
<p>Exemplo lista de descrición "key-value"</p>
<dl>
  <dt><code>reversed</code></dt>
  <dd>Reverse numbering. No value required.</dd>

  <dt><code>start="x"</code></dt>
  <dd>x is an Arabic numeral indicating where to start the numbering if it's not 1.</dd>
</dl>
```

#### 1.3.1.4 `<menu>`

Un [`<menu>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menu) é unha lista interactiva para grupos de [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) ou lig[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)zóns, por exemplo. Soen levar **asociados eventos JS** para proporcionar esa interactividade.

Coma nas `<ul>`s, cada item da lista é un `<li>` que debería conter elementos interactivos como os antes mencionados.

> _O elemento HTML `<menu>` descríbese na especificación HTML coma unha **alternativa semántica** a `<ul>`, pero os navegadores trátano (e expóñeno a través da árbore de accesibilidade) do mesmo xeito que `<ul>`. Representa unha lista desordenada de elementos (que están representados por elementos `<li>`)._

> - _Fonte: [`<menu>`: The Menu element @ MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menu)_

Polo tanto, un bo exemplo de `<menu>`

```html
<div class="news">
  <a href="#">NASA’s Webb Delivers Deepest Infrared Image of Universe Yet</a>
  <menu>
    <li><button id="save">Save for later</button></li>
    <li><button id="share">Share this news</button></li>
  </menu>
</div>
```

### 1.3.2 ⚠️ `<ul>` vs `<menu>` ⚠️

> 👀 _`<ul>` é para **mostrar**, `<menu>` é para interactuar_ 👀

### 1.3.3 Listas anidadas

✅ **Correcto** ✅

```html
<ul class="nested">
  <li>List item con cousas anidadas
    <ol>
      <li>Mais outra cousa, desta volta anidada</li>
    </ol>
  </li>
</ul>
```

❌ **Incorrecto** ❌

```html
<ul class="nested">
  <li>List item con cousas anidadas (non é certo)</li>
    <ol>
      <li>Mais outra cousa, desta volta anidada (meh!)</li>
    </ol>
</ul>
```

### 1.3.4 Máis tipos de listas

En [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)ularios tamen poderiamos considerar:

- [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select).
- [`<datalist>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist).

### 1.3.5 Investiga 🕵️‍♀️🕵️‍♀️🕵️‍♀️

1. Como podemos ordenar unha `<ol>` de maior a menor? 👀 se facemos isto é porque hai un significado na inversión dos números, non pode ser _porque mola_.
2. Como podemos comezar a `<ol>` no número 9?
3. Como podemos ordenar unha `<ol>` de maior a menor comezando no 9 e con so 4 elementos (do 9 ao 6)?
4. Como podemos usar letras e números romanos en vez de números nas `<ol>`?
