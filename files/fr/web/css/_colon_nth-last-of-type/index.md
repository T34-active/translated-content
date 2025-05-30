---
title: :nth-last-of-type
slug: Web/CSS/:nth-last-of-type
l10n:
  sourceCommit: f22e72998f4e8f48b18ef358521bfc9ad1ae9446
---

{{CSSRef}}

La [pseudo-classe](/fr/docs/Web/CSS/Pseudo-classes) [CSS](/fr/docs/Web/CSS) **`:nth-last-of-type`** permet de cibler les éléments selon leur position parmi les voisins qui sont du même type (les mêmes balises) en partant de la fin.

{{InteractiveExample("CSS Demo: :nth-last-of-type", "tabbed-shorter")}}

```css interactive-example
dt {
  font-weight: bold;
}

dd {
  margin: 3px;
}

dd:nth-last-of-type(3n) {
  border: 2px solid orange;
}
```

```html interactive-example
<dl>
  <dt>Vegetables:</dt>
  <dd>1. Tomatoes</dd>
  <dd>2. Cucumbers</dd>
  <dd>3. Mushrooms</dd>
  <dt>Fruits:</dt>
  <dd>4. Apples</dd>
  <dd>5. Mangos</dd>
  <dd>6. Pears</dd>
  <dd>7. Oranges</dd>
</dl>
```

## Syntaxe

La pseudo-classe `nth-last-of-type` prend un seul argument qui représente le motif de répétition des éléments correspondants, comptés à partir de la fin.

Voir [`:nth-last-child`](/fr/docs/Web/CSS/:nth-last-child) pour une explication plus détaillée de sa syntaxe.

```css-nolint
:nth-last-of-type(<an-plus-b> | even | odd) {
  /* ... */
}
```

## Exemples

Ici, on souhaite mettre en avant le deuxième élément [`<span>`](/fr/docs/Web/HTML/Element/span) en partant de la fin&nbsp;:

### HTML

```html
<div>
  <span>Ce span est le premier !</span>
  <span>Ce span ne l'est pas. :(</span>
  <em>Celui-ci est bizarre.</em>
  <span>Celui-ci l'est !</span>
  <strike>C'est un autre type</strike>
  <span>Malheureusement, celui-ci ne l'est pas.</span>
</div>
```

### CSS

```css
span:nth-last-of-type(2) {
  background-color: lime;
}
```

### Résultat

{{EmbedLiveSample('')}}

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}

## Voir aussi

- [`:nth-last-child`](/fr/docs/Web/CSS/:nth-last-child)
- [`:nth-of-type`](/fr/docs/Web/CSS/:nth-of-type)
