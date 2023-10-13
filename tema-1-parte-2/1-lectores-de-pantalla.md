# 1 Lectores de pantalla (_screen readers_)

## 1.1 Que son?

> _"Os **lectores de pantalla** convirten texto en voz sintetizada. Permiten aos usuarios escoitar contido e navegar co teclado. Esta tecnoloxía axuda ás persoas cegas ou con problemas de visión severa a utilizar as tecnoloxías da información (TIC) co mesmo nivel de independencia e privacidade que calquera outra persoa."_
>
> Citado de [Designing for Screen Reader Compatibility @ WebAIM](https://webaim.org/techniques/screenreader/)

## 1.2 Que teñen en común

1. Le todo o contido.
2. Mostra unha lista de ligazóns (`<a>`s).
3. Mostrar unha lista de títulos (ou `<h1>`s a `<h6>`s).

## 1.3 Gran variedade

Hai unha gran variedade de lectores de pantalla. Algúns dos máis usados móstranse a continuación 👇🏿

![Lista dos lectores de pantalla máis populares](./img/list-of-popular-screen-readers.png)

### 1.3.1 Voiceover para Mac

Aplicación nativa do propio SO:

1. Preferencias do sistema
2. Accesibilidade
3. VoiceOver
4. Activa VoiceOver
5. ⌘ + F5

### 1.3.2 Lector de pantalla para Chrome

Lector de pantalla gratuíto que podes descargar como [extensión](https://chrome.google.com/webstore/detail/screen-reader/kgejglhpjiefppelpmljglcjbhoiplfn?hl=en).

### 1.3.3 NVDA para Windows

Lector de pantalla gratuíto que podes descargar [aquí](https://www.nvaccess.org/download/).

## 1.4 Gotcha! 😱

Os **lectores de pantalla carecen dunha especificación estadarizada**. Cada software interpreta o que considera máis adecuado.

## 1.5 Imaxes

### 1.5.1 Comportamento por defecto

Por defecto, cando un lector de pantalla atopa unha [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) sen un atributo [`alt`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#alt) lerá en voz alta o nome do ficheiro, polo que unha boa práctica consiste en, como mínimo, nomear as imaxes de xeito descriptivo e consistente.

Un problema habitual son as **imaxes subidas por usuarios** (en paltaformas que así o permiten) xa que a miúdo reciben nomes de ficheiros que inclúen un hash.

### 1.5.2 Comportamento desexable

É moito mellor engadir o atributo `alt` ás `<img>` xa que, nese caso, os lectores de pantalla lerán o texto alternativo en lugar do nome do ficheiro.

```html
<img
    src="https://example.com/a-miña-imaxe.png
    alt="o meu gato sendo adorable"
/>
```

### 1.5.3 Imaxes non relevantes

Cando nos atopemos ante imaxes non relevantes para o usuario (imaxes decorativas ou fondos, por exemplo) considérase unha boa práctica incluir un **atributo `alt` cunha cadea baleira**, xa que o lector de pantalla **vaise saltar** esa imaxe.

```html
<img
    src="https://example.com/fondo1.png
    alt=""
/>
```

### 1.5.4 Imaxes, SEO e `a11y`

Un apartado no que o SEO e `a11y` difiren e no uso do atributo `alt` das `<img>`s. Unha **práctica SEO** habitual é **encher o `alt` con palabras clave** xa que os buscadores len ese atributo. Esta práctica é **moi nociva** dende o punto de vista da **accesibilidade** e **debe ser evitada**.

### 1.5.5 Guideline 1.1 de WebAIM

Consulta a lista de [WebAIM (ver Guideline 1.1)](https://webaim.org/standards/wcag/checklist).

## 1.6 Audio

### 1.6.1 Recomendacións básicas

Recordemos algunhas das recomendacións da lista de WebAIM para audio.

| Nivel A | Nivel AA | Nivel AAA |
|---------|----------|-----------|
| Proporciona unha transcripción do audio | Proporciona subtítulos sincronizados | Proporciona vídeo con linguaxe de signos sincronizado |

### 1.6.2 Guideline 1.2 de WebAIM

Na `versión 2.0` da lista hai **9 recomendacións**:

- 3 para Nivel A.
- 2 para Nivel AA.
- 4 para Nivel AAA.

Consulta a lista de [WebAIM (ver Guideline 1.2)](https://webaim.org/standards/wcag/checklist)
