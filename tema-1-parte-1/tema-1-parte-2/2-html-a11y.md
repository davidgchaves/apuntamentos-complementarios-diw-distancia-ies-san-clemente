# 2 HTML `a11y`

Simplememte usando xuizosamente o **HTML**, xa estamos axudando coa accesibilidade.

## 2.1 Tags semánticos sen funcionalidade integrada

Algúns dos **tags semánticos** teñen significado (dende un punto de vista semántico) pero non aportan ningunha funcionalidade especial, como por exemplo:

- [`<aside>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside)
- [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)
- [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header)
- [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)
- [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)

En realidade, moitos deles poden ser considerados [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)s semánticos.

## 2.2 Tags semánticos con funcionalidade integrada

Outros tags **si que proporcionan funcións integradas**, como no caso de:

- [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
- [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
- [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
- [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)

## 2.3 Pro-tip: evitemos a sopa de `<div>`s

Xa que temos unha chea de tags semánticos (ver sección 2.1) e tags con funcionalidade integrada (ver sección 2.2), deberiamos **utilizar os `<div>`s como último recurso**, evitando a coñecida _sopa de `<div>`s_ (`<div>` soup) tan habitual en **html** previo á versión 5.

⚠️👀⚠️ Contrario á opinión xeralizada, **os tags semánticos do apartado 2.1 non aportan nada aos lectores de pantalla** ⚠️👀⚠️.

## 2.4 Conformidade WebAIM

### 2.4.1 Guideline 1.3 de WebAIM

Consulta a lista de [WebAIM (ver Guideline 1.3 - Contido que pode ser presentado de varios xeitos sen perder información ou estrutura)](https://webaim.org/standards/wcag/checklist).

### 2.4.2 Exemplo de boa práctica

Como exemplo de boa práctica podemos citar a **importancia de estruturar os `<h1>` a `<h6>` correctamente** para poder navegar coas frechas entre eles usando un lector de pantalla.

| Mala práctica `a11y`          | Boa práctica `a11y` |
|-------------------------------|---------------------|
| Usar `<div>`s con clases CSS `.h1` a `.h6` | Usar `<h1>` a `<h6>` xuizosamente |

⚠️👀⚠️ Calquera cousa que mudemos mediante CSS non vai afectar aos lectores de pantalla ⚠️👀⚠️

## 2.5 Etiquetado nos `<form>`s

### 2.5.1 O problema do etiquetado e a `a11y`

Os campos que conforman un [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) poden ser confusos para os usuarios de lectores de pantalla. Hai moitos xeitos de etiquetar os campos dun formulario para que a etiqueta sexa lida en alto sempre que o campo teña o foco.

O grao máximo deste problema é directamente non etiquetar en absoluto. Pero etiquetar de xeito erróneo como veremos a continuación, tampouco axuda coa `a11y`.

### 2.5.2 O problema: etiquetas visuais mediante `<div>`s ou `<p>`s

Un patrón común é usar etiquetas `<div>`s ou `<p>`s para etiquetar campos dun `<form>`. Non é a mellor das solucións. **Visualmente funciona, pero no aportan nada dende unha óptica `a11y`**.

```html
<form>
    <p>Nome</p>
    <input type="text" />
    <p>Apelidos</p>
    <input type="text" />
    <div>Contrasinal</div>
    <input type="password" />
    <input type="submit" value="Submit" />
</form>
```

### 2.5.3 Etiquetado explícito: `<label>`s e `for`

O uso do tag HTML [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) en conxunción co atributo [`for`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label#for) é unha solución moito mellor dende unha perspectiva `a11y`.

```html
<form>
    <label for="nome">Nome</label>
    <input id="nome" type="text" />

    <label for="apelidos">Apelidos</label>
    <input id="apelidos" type="text" />

    <label for="contrasinal">Contrasinal</label>
    <input id="contrasinal" type="password" />

    <input type="submit" value="Submit" />
</form>
```

### 2.5.4 Etiquetado implícito: `<label>`s

Podemos usar o tag `<label>` para etiquetar implícitamente os campos do `<form>`. Os lectores de pantalla farán o mesmo que no caso anterior de etiquetado explícito. Polo tanto, **dende unha perspectiva `a11y` a opción anterior e esta son simplemente unha cuestión de estilo persoal**.

```html
<form>
    <label>
        Nome
        <input id="nome" type="text" />
    </label>
    <label>
        Apelidos
        <input id="apelidos" type="text" />
    </label>
    <label>
        Contrasinal
        <input id="contrasinal" type="password" />
    </label>

    <input type="submit" value="Submit" />
</form>
```

### 2.5.5 Tags _`<label>`eables_

Só podemos utilizar o tag `<label>` cos elementos que o admiten, entre os que atopamos:

- [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
- [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
- [`<meter>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meter)
- [`<output>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output)
- [`<progress>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress)
- [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)
- [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)

### 2.5.6 Tags non _`<label>`eables_: `aria-label`

Cando teñamos un elemento que non admita o uso `<label>`, deberemos utilizar o atributo [`aria-label`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label) xa que o lector de pantalla lerá o contido deste atributo como se fose un `<label>`.

```html
<div aria-label="Etiqueta para o div">Ola 🖖🖖🖖</div>
```

## 2.6 Comunicación directa co lector de pantalla mediante CSS

Se precisamos comunicación directa co lector de pantalla (por exemplo para _anunciarlles ás usuarias de lectores de pantalla que o noso sitio web ofrece funcións de accesibilidade_), podemos utilizar **unha clase CSS** (por exemplo, nomeada `.visuallyhidden`) que **oculte, visualmente, o contido**.

```css
.visuallyhidden {
    position: absolute;
    left: 0;
    top: -500px;
    width: 1px;
    height: 1px;
    overflow: hidden;
}
```

```html
<div>
    <p class="visuallyhidden">
        Aviso para persoas con dificultades de visión:
        temos unha chea de melloras no noso sitio
        orientadas a que vos sintades na vosa casa
    </p>
<div>
```

O único que fai `.visuallyhidden` é:

- Posicionar de xeito absoluto (`position: absolute`).
- Enviar cara arriba fora da pantalla (`top: -500px`).

## 2.7 `<button>`s

### 2.7.1 Un `<button>` facendo de `<button>`

```html
<button onclick="alert('Ola 🖖🖖🖖')">
    Dalle ao click!
</button>
```

A continuación imos ver **canta funcionalidade** hai detrás do código anterior, tentando chegar a algo semellante partindo dun `<div>`. Deste xeito faremos fincapé na importancia e a funcionalidade por defecto que proporcionan os tags semánticos como `<buttton>`.

### 2.7.2 Simulando un`<button>` cun `<div>`

#### 2.7.2.1 Un `<div>` _clickable_

```html
<div onclick="alert('Ola 🖖🖖🖖')">
    Dalle ao click!
</button>
```

Este escenario é **completamente desconcertante para un lector de pantalla**. Non ten nin idea do _propósito_ do `<div>` nin da súa _natureza_ como botón.

#### 2.7.2.2 Un `<div>` facendo de `<button>` v2

Podemos usar o atributo `role` (forma parte de ARIA).

```html
<div role="button" onclick="alert('Ola 🖖🖖🖖')">
    Dalle ao click!
</button>
```

Grazas ao atributo `role`, agora o lector de pantalla interpretará o `<div>` como un `<button>`... pero non podermos chegar a el sen rato (mediante `TAB`). **Técnicamente**: este `<div>` non é enfocable (_focus_) mediante teclado.

#### 2.7.2.3 Un `<div>` facendo de `<button>` v3

Co atributo global [`tabindex`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex) podemos solucionar a enfocabilidade.

```html
<div tabindex="0"
     role="button"
     onclick="alert('Ola 🖖🖖🖖')">
    Dalle ao click!
</button>
```

...pero todavía queda outro problema. O `<div>` agora é enfocable por teclado, pero **non é clickable** por teclado. É dicir, presionando `ENTER` ou a `barra espaciadora` no teclado, o `<div>` non fai nada.

#### 2.7.2.4 Un `<div>` facendo de `<button>` v4

Co evento [`keyup`](https://developer.mozilla.org/en-US/docs/Web/API/Element/keyup_event) podemos solucionar a _clickabilidade_ mediante teclado.

```html
<div tabindex="0"
     role="button"
     onclick="alert('Ola 🖖🖖🖖')"
     onkeyup="alert('Ola 🖖🖖🖖')">
    Dalle ao click!
</button>
```

Se nos poñemos exquisitas deberiamos detectar mediante JS que as teclas presionadas son `ENTER` ou a `barra espaciadora`.

#### 2.7.2.5 Un `<div>` facendo de `<button>` v5

Dende o punto de vista dunha usuaria dun lector de pantalla

> _por que debería "clickar" no botón?_

Fai falla unha aclaración, e para iso podemos utilizar un atributo ARIA que vimos anteriormente, o `aria-label`.

```html
<div aria-label="Alerta ao mundo cun saúdo spockiano"
     tabindex="0"
     role="button"
     onclick="alert('Ola 🖖🖖🖖')"
     onkeyup="alert('Ola 🖖🖖🖖')">
    Dalle ao click!
</button>
```

Agora ós lectores de pantalla lerán

> _`Alerta ao mundo cun saúdo spockiano`_

É dicir, porqué deberías pulsar o botón.

Deste xeito aproximámonos á funcionalidade por defecto dun `<button>`, cunha 🎠 cabriola 🎠 extra de ARIA.
