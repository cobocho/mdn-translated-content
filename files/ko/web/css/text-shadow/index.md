---
title: text-shadow
slug: Web/CSS/text-shadow
---

{{CSSRef}}

**`text-shadow`** [CSS](/ko/docs/Web/CSS) 속성은 텍스트에 그림자(shadow)를 추가합니다. 텍스트와 그 장식에 적용 할 쉼표로 구분 된 그림자 목록을 허용합니다. 각 그림자는 요소, 흐림 반경 및 색상의 X 및 Y 오프셋 조합으로 설명됩니다.

{{EmbedInteractiveExample("pages/css/text-shadow.html")}}

## 구문

```css
/* offset-x | offset-y | blur-radius | color */
text-shadow: 1px 1px 2px black;

/* color | offset-x | offset-y | blur-radius */
text-shadow: #fc0 1px 0 10px;

/* offset-x | offset-y | color */
text-shadow: 5px 5px #558abb;

/* color | offset-x | offset-y */
text-shadow: white 2px 5px;

/* offset-x | offset-y
/* Use defaults for color and blur-radius */
text-shadow: 5px 10px;

/* Global values */
text-shadow: inherit;
text-shadow: initial;
text-shadow: revert;
text-shadow: revert-layer;
text-shadow: unset;
```

This property is specified as a comma-separated list of shadows.

Each shadow is specified as two or three `<length>` values, followed optionally by a `<color>` value. The first two `<length>` values are the `<offset-x>` and `<offset-y>` values. The third, optional, `<length>` value is the `<blur-radius>`. The`<color>` value is the shadow's color.

When more than one shadow is given, shadows are applied front-to-back, with the first-specified shadow on top.

This property applies to both {{cssxref("::first-line")}} and {{cssxref("::first-letter")}} [pseudo-elements](/ko/docs/Web/CSS/Pseudo-elements).

### Values

- {{cssxref("&lt;color&gt;")}}
  - : Optional. The color of the shadow. It can be specified either before or after the offset values. If unspecified, the color's value is left up to the user agent, so when consistency across browsers is desired you should define it explicitly.
- `<offset-x> <offset-y>`
  - : Required. These {{cssxref("&lt;length&gt;")}} values specify the shadow's distance from the text. `<offset-x>` specifies the horizontal distance; a negative value places the shadow to the left of the text. `<offset-y>` specifies the vertical distance; a negative value places the shadow above the text. If both values are `0`, the shadow is placed directly behind the text, although it may be partly visible due to the effect of `<blur-radius>`.
- `<blur-radius>`
  - : Optional. This is a {{cssxref("&lt;length&gt;")}} value. The higher the value, the bigger the blur; the shadow becomes wider and lighter. If not specified, it defaults to `0`.

## Formal definition

{{CSSInfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Simple shadow

```css
.red-text-shadow {
  text-shadow: red 0 -2px;
}
```

```html
<p class="red-text-shadow">Sed ut perspiciatis unde omnis iste
    natus error sit voluptatem accusantium doloremque laudantium,
    totam rem aperiam, eaque ipsa quae ab illo inventore.</p>
```

{{EmbedLiveSample('Simple_shadow', '660px', '90px')}}

### Multiple shadows

```css
.white-text-with-blue-shadow {
  text-shadow: 1px 1px 2px black, 0 0 1em blue, 0 0 0.2em blue;
  color: white;
  font: 1.5em Georgia, serif;
}
```

```html
<p class="white-text-with-blue-shadow">Sed ut perspiciatis unde omnis iste
    natus error sit voluptatem accusantium doloremque laudantium,
    totam rem aperiam, eaque ipsa quae ab illo inventore.</p>
```

{{EmbedLiveSample('Multiple_shadows', '660px', '170px')}}

## 명세서

{{Specifications}}

## 브라우저 호환성

{{Compat}}

## See also

- {{cssxref("box-shadow")}}
- The {{cssxref("&lt;color&gt;")}} data type (for specifying the shadow color)
- [Applying color to HTML elements using CSS](/ko/docs/Web/CSS/CSS_Colors/Applying_color)
