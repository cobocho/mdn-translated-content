---
title: ":-moz-focusring"
slug: conflicting/Web/CSS/:focus-visible
tags:
  - Фокус
  - псевдокласс
translation_of: Web/CSS/:-moz-focusring
original_slug: Web/CSS/:-moz-focusring
---

{{Non-standard_header}}{{CSSRef}}

## Описание

Псевдокласс **:-moz-focusring** является расширением браузера Mozilla, которое подобно псевдоклассу {{cssxref (":focus")}}, но взаимодействует только с элементом при наличии у него фокуса. При этом рамка фокуса или другой индикатор располагается вокруг элемента.

Если :-moz-focusring распознается конкретной платформой, то и **:focus** тоже. Однако обратное не всегда верно и зависит от того, активированы ли пользовательские настройки для отрисовки фокуса и как именно действует фокус по отношению к этому элементу. Независимо от того, имеют ли место пользовательские настройки отрисовки фокуса, многое также зависит от настроек операционной системы и других факторов. В связи с этим точное поведение этого псевдокласса может варьироваться от платформы к платформе.

> **Примечание.** Разработчики склонны использовать псевдокласс **:-moz-focusring** для различия между состояниями фокуса, когда пользователь активирует фокусировку с помощью мыши и клавиатуры. Это также потенциально полезно при создании пользовательского элемента с последующим намерением изменить его стиль на основе его поведения.

## Синтаксис

```
:-moz-focusring
```

## Пример

Для определения внешнего вида элемента во время фокусировки на нем можно использовать этот псевдоселектор следующим образом:

```css
mybutton:-moz-focusring {
  outline: 2px dotted;
}
```

## Спецификации

Этот псевдокласс пока ещё не определён ни в одной спецификации, хотя и прошёл этап обсуждения в рабочей группе. По его итогам было решено внести его в группу селекторов 4 или 5.

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- {{bug("418521")}}
