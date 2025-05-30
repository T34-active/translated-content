---
title: Комбинаторы
slug: Learn_web_development/Core/Styling_basics/Combinators
---

{{LearnSidebar}}{{PreviousMenuNext("Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements", "Learn/CSS/Building_blocks/The_box_model", "Learn/CSS/Building_blocks")}}

Наконец мы рассмотрим селекторы, которые называются комбинаторами, поскольку они соединяют другие селекторы, создавая полезную связь селекторов друг с другом и расположением содержимого в документе.

| Необходимые условия: | Базовая компьютерная грамотность, [установленное базовое программное обеспечение](/ru/docs/Learn_web_development/Getting_started/Environment_setup/Installing_software), базовые знания о [работе с файлами](/ru/docs/Learn_web_development/Getting_started/Environment_setup/Dealing_with_files), основы HTML (изучите [Введение в HTML](/ru/docs/Learn/HTML/%D0%92%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5_%D0%B2_HTML)) и понимание работы CSS (изучите [Введение в CSS](/ru/docs/conflicting/Learn_web_development/Core/Styling_basics).) |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Цель:                | Узнать о различных комбинаторных селекторах, которые могут быть использованы в CSS.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

## Комбинатор потомка

**Селектор потомка** — обычно представляется символом пробела (" ") — соединяет два селектора так, что элементы, соответствующие второму селектору, выбираются, если они имеют предка (родителя, родителя родителя, родителя родителя родителя и т.д.), соответствующего первому селектору. Селекторы, которые используют комбинатор потомка, называются _селекторами потомка._

```css
body article p
```

В приведённом ниже примере выбирается только тот элемент \<p>, который находится внутри элемента с классом`.box`.

{{EmbedGHLiveSample("css-examples/learn/selectors/descendant.html", '100%', 500)}}

## Дочерний комбинатор

**Дочерний комбинатор** (`>`) помещается между двумя селекторами CSS. При этом будут выбраны только те элементы, соответствующие второму селектору, которые являются прямыми потомками элементов, соответствующих первому селектору. Все элементы-потомки на более низких уровнях иерархии будут пропущены. Например, чтобы выбрать только те элементы `<p>`, которые являются дочерними элементами `<article>`, селектор пишется так:

```css
article > p
```

Другой пример. Имеется неупорядоченный список, заключающий в себе другой, упорядоченный список. Дочерний комбинатор используется для того, чтобы выбрать только те элементы `<li>`, которые являются прямыми потомками `<ul>`, и присвоить им верхнюю границу красного цвета.

Если вы уберёте символ `>`, указывающий на то, что это селектор с дочерним комбинатором, селектор превратится в селектор всех потомков (комбинатор - пробел) и все элементы `<li>` получат верхнюю границу красного цвета.

{{EmbedGHLiveSample("css-examples/learn/selectors/child.html", '100%', 600)}}

## Соседний родственный комбинатор

Соседний родственный селектор (`+`) используется для выбора элемента, который непосредственно следует за другим элементом и находится на одном с ним уровне иерархии. Например, чтобы выбрать все элементы `<img>` , которые идут сразу после элементов `<p>` :

```css
p + img
```

Распространённый вариант использования — сделать что-то с абзацем, который следует за заголовком, как в примере ниже. Здесь мы ищем абзац, который непосредственно примыкает к `<h1>`, и стилизуем его.

Если вы вставите какой-то другой элемент, например `<h2>` между `<h1>` и `<p>`, вы обнаружите, что абзац больше не соответствует селектору и поэтому не получает цвет фона и переднего плана, применяемый, когда элемент является соседним.

{{EmbedGHLiveSample("css-examples/learn/selectors/adjacent.html", '100%', 800)}}

## Общий родственный комбинатор

Если вы хотите выбрать родственные элементы, даже если они не являются непосредственными соседями, то вы можете использовать общий родственный комбинатор (`~`). Чтобы выбрать все элементы `<img>`, которые находятся в _любом_ месте после элементов `<p>`, надо указать так:

```css
p ~ img
```

В приведённом ниже примере мы выбираем все элементы `<p>`, которые идут после `<h1>`, и хотя в документе есть также `<div>`, тем не менее `<p>`, который идёт после него, будет выбран.

{{EmbedGHLiveSample("css-examples/learn/selectors/general.html", '100%', 600)}}

## Использование комбинаторов

Вы можете соединять с помощью комбинаторов любые селекторы, которые мы изучали в предыдущих уроках, чтобы выбрать часть вашего документа. Например, если мы хотим выбрать пункты списка с классом "a", которые являются прямыми потомками `<ul>`, можно использовать следующую комбинацию:

```css
ul > li[class="a"] {
}
```

Однако будьте осторожны при создании больших списков селекторов, которые выделяют очень конкретные части вашего документа. Будет трудно повторно использовать правила CSS, так как вы сделали селектор очень специфичным для определения местоположения этого элемента в разметке.

Часто бывает лучше создать простой класс и применить его к рассматриваемому элементу. Тем не менее, ваши знания о комбинаторах будут очень полезны, если вам нужно добраться до чего-то в вашем документе и вы не можете получить доступ к HTML, возможно, из-за того, что он генерируется CMS.

## Проверьте ваши навыки!

Мы охватили много тем в этой статье. А вы можете вспомнить наиболее важную информацию? Можете пройти несколько дополнительных тестов для того чтобы убедиться в том, что вы усвоили эту информацию, прежде чем пойдёте дальше — смотрите [Проверьте ваши навыки: Селекторы](/ru/docs/Learn/CSS/Building_blocks/%D0%A1%D0%B5%D0%BB%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D1%8B/%D0%A1%D0%B5%D0%BB%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D1%8B_%D0%97%D0%B0%D0%B4%D0%B0%D1%87%D0%B8).

## Двигаемся дальше

Это последний раздел в наших уроках по селекторам. Далее мы перейдём к другой важной части CSS — [CSS модель коробки](/ru/docs/Learn_web_development/Core/Styling_basics/Box_model).

{{PreviousMenuNext("Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements", "Learn/CSS/Building_blocks/The_box_model", "Learn/CSS/Building_blocks")}}
