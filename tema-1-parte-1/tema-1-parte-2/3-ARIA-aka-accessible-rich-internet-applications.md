# 3 ARIA (Accessible Rich Internet Applications)

## 3.1 Documentación oficial e cometido

- [Documentación oficial de ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA).
- [Especificacións oficiais de ARIA](https://www.w3.org/TR/html-aria/#aria-table).

> _"Accessible Rich Internet Applications (ARIA) é unha colección de atributos que definen como producir contido e aplicacións web (especialmente as desenvolvidas con JS) máis accesibles para as persoas con discapacidade."_
>
> Citado da [Documentación oficial de ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)

## 3.2 Etiquetas

### 3.2.1 Que ofrece ARIA

ARIA ofrécenos excelentes ferramentas para etiquetar e describir calquera elemento que queiramos mediante:

- [`aria-label`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)
- [`aria-labeledby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby)
- [`aria-describedby`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-describedby)

### 3.2.2 Exemplo de `aria-labeledby`

```html
<ol>
    <li>
        Clonade o código
        <div class="visuallyhidden" id="ligazonGithub">
            Páxina Github dos apuntamentos de DIW
        </div>
        <a
            aria-labelledby="ligazonGithub"
            href="https://github.com/davidgchaves/apuntamentos-complementarios-diw-distancia-ies-san-clemente"
        >
            deste repo
        </a>
    </li>
</ol>
```

### 3.2.3 `labelledby` vs `describedby`?

Unha etiqueta (`labelledby`) proporciona información esencial sobre un obxecto, mentres que unha descrición (`describedby`) proporciona información extra que a usuaria podería precisar.

Por exemplo:

> _Supoñamos que temos un `<button>` que envía un `<form>`ulario, pero tras o envío, redirecciona á paxina principal._

Poderiamos facer 2 cousas simultáneamente:

1. Etiquetar (`labelledby`) o `<button>` como _"envía o formulario"_.
2. Describir (`describedby`) que _"tras o envío do formulario serás redirixido á paxina principal"_.

## 3.3 Roles, estados e propiedades

ARIA proporciona roles para ser aplicados a calquera elemento. Entre [todos roles proporcionados por ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles) podemos destacar:

- [`banner`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/banner_role)
- [`button`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role)
- [`checkbox`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/checkbox_role)
- [`tree`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/tree_role)

Tamén proporciona [estados e propiedades](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes) coma:

- [`aria-autocomplete`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-autocomplete)
- [`aria-expanded`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-expanded)
- [`aria-haspopup`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-haspopup)
- [`aria-modal`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-modal)

Todas estes _roles, estados e propiedades_ de ARIA axudan moito aos lectores de pantalla.

Ademais, ao ser atributos, poden ser usados con **selectores CSS**

```css
.dropdown[aria-expanded="false"] .icon::after {
    content: '▶';
}
.dropdown[aria-expanded="true"]  .icon::after {
    content: '▼';
}
```

## 3.4 ARIA e dinamismo: `area-live`

### 3.4.1 Contexto

A día de hoxe as aplicacións tenden a ser moi dinámicas. Para os casos nos que se poida **recibir información importante en calquera momento** ARIA ofrece a posibilidade de **marcar un elemento** como que contén datos en directo ([`aria-live`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Live_Regions)) para que os lectores de pantalla poidan ler as actualizacións a medida que chegan.

### 3.4.2 Exemplo de uso

Pensade, por exemplo, nunha aplicación para todas aquelas que teñan bitcoins e queiran coñecer o seu valor actual, mentres o resto da xente esperamos a que lles actualice a 👇🏿👇🏿👇🏿

```html
<div aria-live="assertive">
    O valor dos teus ₿ caeu a 0€. Deixa de malgastar a enerxía de todas 😎
</div>
```

Cando o contido do `<div>` se actualice, calquera tecnoloxía de asistencia avisará á usuaria (por exemplo, un lector de pantalla lerá o estado actualizado).

### 3.4.3 Valores de `aria-live`

`aria-live` pode tomar [3 valores](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-live#values) coñecidos como **_configuración da cortesía_** 😂😂😂:

- [`aria-live="assertive"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-live#assertive): interromperá o que estea facendo para anunciar.
- [`aria-live="polite"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-live#polite): anunciará a actualización da rexión en directo cando estea inactivo.
- [`aria-live="off"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-live#off): non lerá a actualización (equivalente a non usar `aria-live`).
