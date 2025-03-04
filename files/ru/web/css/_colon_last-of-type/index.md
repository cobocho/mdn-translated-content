---
title: ":last-of-type"
slug: Web/CSS/:last-of-type
---
{{CSSRef}}

[CSS](/ru/docs/CSS) [псевдокласс](/ru/docs/Web/CSS/Псевдо-классы) **`:last-of-type`** находит последнего потомка с заданным тегом в списке детей родительского элемента.

```css
/* Выбирает <p>, являющийся последним элементом
   среди элементов своего типа среди своих соседей */
p:last-of-type {
  color: lime;
}
```

> **Примечание:** В первоначальном определении выбранный элемент должен иметь родителя. Начиная с Selectors Level 4, это не является обязательным.

## Синтаксис

{{csssyntax}}

## Пример

### Стилизация последнего параграфа

#### HTML

```html
<h2>Заголовок</h2>
<p>Параграф 1</p>
<p>Параграф 2</p>
```

#### CSS

```css
p:last-of-type {
  color: red;
  font-style: italic;
}
```

#### Результат

{{EmbedLiveSample('Стилизация_последнего_параграфа')}}

### Вложенные элементы

Этот пример показывает как можно обратиться к вложенным элементам. Заметим, что в случаях когда не указано ни одного простого селектора, подразумевается [универсальный селектор](/ru/docs/Web/CSS/Universal_selectors) (`*`).

#### HTML

```html
<article>
  <div>Этот `div` первый.</div>
  <div>Этот <span>вложенный `span` является последним</span>!</div>
  <div>Этот <em>вложенный `em` первый</em>, а этот <em>вложенный `em` последний</em>!</div>
  <b>Этот `b` будет выбран!</b>
  <div>Это последний `div`!</div>
</article>
```

#### CSS

```css
article :last-of-type {
  background-color: pink;
}
```

#### Результат

{{EmbedLiveSample('Вложенные_элементы', 500)}}

## Спецификации

{{Specifications}}

## Поддержка браузерами

{{Compat}}

## Смотрите также

- {{cssxref(":last-child")}}, {{Cssxref(":nth-last-of-type")}}
