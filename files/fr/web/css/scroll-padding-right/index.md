---
title: scroll-padding-right
slug: Web/CSS/scroll-padding-right
---

{{CSSRef}}

La propriété **`scroll-padding-right`** est une propriété qui permet de définir le remplissage sur le côté droit entre l'élément et la zone de défilement.

Les propriétés pour le remplissage de la zone de défilement permettent de définir des décalages par rapport à la zone de défilement de l'élément (_scrollport_). On peut ainsi éviter à un élément d'être affiché là où d'autres barres sont présentes ou encore donner plus d'espace entre un élément et les barres de défilement pour y naviguer.

{{InteractiveExample("CSS Demo: scroll-padding-right")}}

```css interactive-example-choice
scroll-padding-right: 0;
```

```css interactive-example-choice
scroll-padding-right: 20px;
```

```css interactive-example-choice
scroll-padding-right: 2em;
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="scroller" id="example-element">
    <div>1</div>
    <div>2</div>
    <div>3</div>
  </div>
  <div class="info">Scroll »</div>
</section>
```

```css interactive-example
.default-example {
  flex-wrap: wrap;
}

.default-example .info {
  width: 100%;
  padding: 0.5em 0;
  font-size: 90%;
}

.scroller {
  text-align: left;
  width: 250px;
  height: 250px;
  overflow-x: scroll;
  display: flex;
  box-sizing: border-box;
  border: 1px solid black;
  scroll-snap-type: x mandatory;
}

.scroller > div {
  flex: 0 0 250px;
  width: 250px;
  background-color: rebeccapurple;
  color: #fff;
  font-size: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  scroll-snap-align: end;
}

.scroller > div:nth-child(even) {
  background-color: #fff;
  color: rebeccapurple;
}
```

## Syntaxe

```css
/* Valeurs avec un mot-clé */
scroll-padding-right: auto;

/* Valeurs de longueur */
/* Type <length> */
scroll-padding-right: 10px;
scroll-padding-right: 1em;
scroll-padding-right: 10%;

/* Valeurs globales */
scroll-padding-right: inherit;
scroll-padding-right: initial;
scroll-padding-right: unset;
```

### Valeurs

- `<length-percentage>`
  - : Un décalage intérieur entre la boîte de défilement et le bord correspondant de l'élément. C'est une longueur ou un pourcentage valide.
- `auto`
  - : Le décalage est déterminé par l'agent utilisateur. Cette valeur correspond généralement à `0px` mais le navigateur peut utiliser une heuristique et déterminer si une valeur non nulle est préférable au regard du contexte dans lequel se trouve l'élément.

## Définition formelle

{{CSSInfo}}

## Syntaxe formelle

{{CSSSyntax}}

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}
