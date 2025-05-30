---
title: box-sizing
slug: Web/CSS/box-sizing
---

{{CSSRef}}

[CSS](/ru/docs/Web/CSS) свойство **`box-sizing`** определяет как вычисляется общая ширина и высота элемента.

{{InteractiveExample("CSS Demo: box-sizing")}}

```css interactive-example-choice
box-sizing: content-box;
width: 100%;
```

```css interactive-example-choice
box-sizing: content-box;
width: 100%;
border: solid #5b6dcd 10px;
padding: 5px;
```

```css interactive-example-choice
box-sizing: border-box;
width: 100%;
border: solid #5b6dcd 10px;
padding: 5px;
```

```html interactive-example
<section id="default-example">
  <div id="example-element-parent">
    <p>Parent container</p>
    <div class="transition-all" id="example-element">
      <p>Child container</p>
    </div>
  </div>
</section>
```

```css interactive-example
#example-element-parent {
  width: 220px;
  height: 200px;
  border: solid 10px #ffc129;
  margin: 0.8em;
}

#example-element {
  height: 60px;
  margin: 2em auto;
  background-color: rgba(81, 81, 81, 0.6);
}

#example-element > p {
  margin: 0;
}
```

По умолчанию в [блоковой модели CSS](/ru/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model) ширина и высота, которую вы задаёте элементу применяется только для контента элемента. Если у элемента есть граница или внутренний отступ, то они добавляются к ширине и высоте, чтобы получить отображаемый на экране размер. Это значит, что когда вы выставляете ширину и высоту, вам придётся изменять значение, при добавлении границ и отступов. Например, если у вас есть четыре блока с `width: 25%;` , и у какого-нибудь из них есть граница или внутренний отступ слева или справа, то по умолчанию они не поместятся на одной строке.

Свойство `box-sizing` может изменять это поведение:

- `content-box` даёт стандартное поведение свойства box-sizing. Если вы выставите элементу ширину 100 пикселей, то ширина его контента будет 100 пикселей, а ширина границ и внутренних отступов при рендере будет добавлена к финальной ширине, делая элемент шире ста пикселей.
- `border-box` говорит браузеру учитывать любые границы и внутренние отступы в значениях, которые вы указываете в ширине и высоте элемента. Если вы выставите элементу ширину 100 пикселей, то эти 100 пикселей будут включать в себя границы и внутренние отступы, а контент сожмётся, чтобы выделить для них место. Обычно это упрощает работу с размерами элементов.

> **Примечание:**Часто выставление `box-sizing: border-box` полезно для размещения элементов. Оно сильно упрощает работу с размерами элементов, и как правило устраняет ряд подводных камней, на которые вы можете наткнуться, размещая контент. С другой стороны, используя `position: relative` или `position: absolute`, `box-sizing: content-box` позволяет позиционным значениям быть зависимыми только от контента, а не от границ и отступов, что иногда желательно.

## Синтаксис

Для свойства `box-sizing` устанавливается единственное ключевое слово из списка значений ниже.

### Значения

- `content-box`
  - : Это значение по умолчанию, определённое в CSS стандарте. Свойства [width](/ru/docs/Web/CSS/width) и [height](/ru/docs/Web/CSS/height) включают исключительно контент, и не включают [padding](/ru/docs/Web/CSS/padding) и [border](/ru/docs/Web/CSS/border). Например `.box {width: 350px; border: 10px solid black;}` будет иметь ширину 370 пикселей.Размеры элемента рассчитываются следующим образом: _width = ширина контента_, и _height = высота контента_. (Границы и внутренние отступы не включаются в вычисление.)
- `border-box`
  - : Свойства [width](/ru/docs/Web/CSS/width) и [height](/ru/docs/Web/CSS/height) включают контент, внутренний отступ и границы, но не включают внешний отступ. Заметьте, что внутренний отступ и граница будут внутри блока. Например, `.box {width: 350px; border: 10px solid black;}` будет иметь общую ширину 350 пикселей, а ширина контента составит 330 пикселей. Размер контента не может быть отрицательным, минимальное значение - 0, поэтому `border-box` невозможно использовать для скрытия элемента.Размеры элемента рассчитываются следующим образом: _width = граница + внутренний отступ + ширина контента_, и _height = граница + внутренний отступ + высота контента_.

### Формальный синтаксис

{{csssyntax}}

> [!NOTE]
> Значение `padding-box` устарело

## Пример

Этот пример показывает как разные значения `box-sizing` изменяют видимый размер двух идентичных элементов.

### HTML

```html
<div class="content-box">Content box</div>
<br />
<div class="border-box">Border box</div>
```

### CSS

```css
div {
  width: 160px;
  height: 80px;
  padding: 20px;
  border: 8px solid red;
  background: yellow;
}

.content-box {
  box-sizing: content-box;
  /* Total width: 160px + (2 * 20px) + (2 * 8px) = 216px
     Total height: 80px + (2 * 20px) + (2 * 8px) = 136px
     Content box width: 160px
     Content box height: 80px */
}

.border-box {
  box-sizing: border-box;
  /* Total width: 160px
     Total height: 80px
     Content box width: 160px - (2 * 20px) - (2 * 8px) = 104px
     Content box height: 80px - (2 * 20px) - (2 * 8px) = 24px */
}
```

### Результат

{{EmbedLiveSample('Пример', 'auto', 300)}}

## Спецификации

{{Specifications}}

{{cssinfo}}

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- [Блоковая модель CSS](/ru/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model)
