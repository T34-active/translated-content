---
title: hyphens
slug: Web/CSS/hyphens
l10n:
  sourceCommit: 14515827c44f3cb814261a1c6bd487ae8bfcde1b
---

**`hyphens`** は [CSS](/ja/docs/Web/CSS) のプロパティで、文字列を複数行にわたって折り返す際に、単語のハイフネーションを行う方法を指定します。ハイフネーションをまったく行わなかったり、手動で指定された位置で文字列のハイフネーションを行ったり、ブラウザーに適切な位置にハイフンを挿入させたりすることができます。

{{InteractiveExample("CSS デモ: hyphens")}}

```css interactive-example-choice
hyphens: none;
```

```css interactive-example-choice
hyphens: manual;
```

```css interactive-example-choice
hyphens: auto;
```

```html interactive-example
<section id="default-example">
  <p id="example-element">An extra­ordinarily long English word!</p>
</section>
```

```css interactive-example
#example-element {
  border: 2px dashed #999;
  font-size: 1.5rem;
  text-align: left;
  width: 7rem;
}
```

> [!NOTE]
> 上記のデモでは、 "An extra­ordinarily long English word!" に非表示の `&shy;` （ソフトハイフン）の文字が含まれており、 `An extra&shy;­ordinarily long English word!` のようになっています。この文字は `hyphens: manual;` が指定された場合にハイフンを挿入することができる位置を示しています。

ハイフネーションの規則は言語に依存します。 HTML では言語は [`lang`](/ja/docs/Web/HTML/Reference/Global_attributes/lang) 属性で特定され、ブラウザーはこの属性が存在し、適切なハイフネーション辞書が利用できる場合にのみハイフネーションを行います。 XML では、[`xml:lang`](/ja/docs/Web/SVG/Reference/Attribute/xml:lang) 属性を使用する必要があります。

> [!NOTE]
> どのようにハイフネーションを行うかの規則は仕様書で明確に定義されていないため、厳密なハイフネーションの方式はブラウザーにより異なります。

対応していれば、 {{cssxref("hyphenate-character")}} を使用して、分割された行の終わりに使用する代替のハイフン文字を指定することができます。

## 構文

```css
/* キーワード値 */
hyphens: none;
hyphens: manual;
hyphens: auto;

/* グローバル値 */
hyphens: inherit;
hyphens: initial;
hyphens: revert;
hyphens: revert-layer;
hyphens: unset;
```

`hyphens` プロパティは、以下に挙げたキーワード値のうちの一つで指定します。

### 値

- `none`
  - : 単語内で分割が提案されている文字の位置であっても、改行で単語を分割しません。行はホワイトスペースの位置のみで折り返します。
- `manual`
  - : 単語内で分割が提案されている文字の位置でのみ、行の折り返しで単語を分割します。詳しくは[改行候補位置の提案](#改行候補位置の提案)を参照してください。
- `auto`
  - : ブラウザーは自身が選択した規則に従って、ハイフネーションを行うのに適切な位置で自動的に単語を分割します。しかし、改行候補位置 ([改行候補位置の提案](#改行候補位置の提案)を参照) があれば、自動的な改行位置の選択を上書きします。

> [!NOTE]
> `auto` を設定したときの動作は、正しくタグ付けされた言語に依存して、適切なハイフネーション規則が選択されます。選択した言語で自動的なハイフネーションが適用されるようにすることを保証するために、 HTML の `lang` 属性を必ず指定してください。

> [!NOTE]
> [`word-break: break-all`](/ja/docs/Web/CSS/word-break#break-all) を適用すると、と、単語がハイフネーションポイントで区切られていても、ハイフンはまったく表示されません。

## 改行候補位置の提案

文字列中で改行が可能な位置を手動で指定するために使用できる Unicode 文字は 2 つあります。

- U+2010 (HYPHEN)
  - : 「ハード」ハイフン文字は、目に見える改行候補位置を示します。実際はその位置で改行されない場合でも、ハイフンが表示されます。
- U+00AD (SHY)
  - : 不可視の「ソフト」ハイフン ("**s**oft" **hy**phen) です。この文字は表示されませんが、ブラウザーが必要に応じて単語を分割できる位置を示します。 HTML では、 `&shy;` を使用してソフトハイフンを挿入することができます。

> [!NOTE]
> HTML の [`<wbr>`](/ja/docs/Web/HTML/Reference/Elements/wbr) 要素によって改行が行われた場合、ハイフンは挿入されません。

## 公式定義

{{cssinfo}}

## 形式文法

{{csssyntax}}

## 例

### テキストのハイフネーションの指定

以下の例では 3 つのクラスを使用し、それぞれの `hyphens` プロパティの設定を示します。

#### HTML

```html-nolint
<dl>
  <dt><code>none</code>: ハイフンなし、必要に応じてあふれさせる</dt>
  <dd lang="en" class="none">An extreme&shy;ly long English word</dd>
  <dt>
    <code>manual</code>: &amp;hyphen; または &amp;shy; のところだけ（必要に応じて）折り返す
  </dt>
  <dd lang="en" class="manual">An extreme&shy;ly long English word</dd>
  <dt><code>auto</code>: アルゴリズムで決めた場所で（必要に応じて）折り返す</dt>
  <dd lang="en" class="auto">An extreme&shy;ly long English word</dd>
</dl>
```

#### CSS

```css
dd {
  width: 55px;
  border: 1px solid black;
}
dd.none {
  hyphens: none;
}
dd.manual {
  hyphens: manual;
}
dd.auto {
  hyphens: auto;
}
```

#### 例

{{EmbedLiveSample("Specifying_text_hyphenation", "100%", 490)}}

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- {{Cssxref("content")}}
- {{cssxref("overflow-wrap")}} (formerly `word-wrap`)
- {{cssxref("word-break")}}
- [テキストの分割と折り返しのガイド](/ja/docs/Web/CSS/CSS_text/Wrapping_breaking_text)
