---
title: Affectation après reste (%=)
slug: Web/JavaScript/Reference/Operators/Remainder_assignment
---

{{jsSidebar("Operators")}}

L'opérateur de reste et d'affectation (`%=`) calcule le reste de la division de l'opérande gauche par l'opérande droit et affecte ce résultat à la variable représentée par l'opérande gauche.

{{InteractiveExample("JavaScript Demo: Expressions - Remainder assignment operator")}}

```js interactive-example
let a = 3;

console.log((a %= 2));
// Expected output: 1

console.log((a %= 0));
// Expected output: NaN

console.log((a %= "hello"));
// Expected output: NaN
```

## Syntaxe

```js
Opérateur: x %= y;
Signification: x = x % y;
```

## Exemples

### Utiliser l'opérateur de reste et d'affectation

```js
let truc = 5;
truc %= 2; // 1
truc %= "toto"; // NaN
truc %= 0; // NaN
```

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}

## Voir aussi

- [Les opérateurs d'affectation dans le guide JavaScript](/fr/docs/Web/JavaScript/Guide/Expressions_and_operators#assignment)
- [L'opérateur de reste](/fr/docs/Web/JavaScript/Reference/Operators/Remainder)
