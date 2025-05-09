---
title: log ロールの使用
slug: Web/Accessibility/ARIA/Reference/Roles/log_role
original_slug: Web/Accessibility/ARIA/Roles/log_role
---

{{AccessibilitySidebar}}

### 説明

このテクニックは、[`log`](https://www.w3.org/TR/wai-aria/#log) ロールを使用する方法を示し、ブラウザーと支援技術に与える影響について説明します。

`log` ロールは、新しい情報が意味のある順序で追加され、古い情報が消える[ライブリージョン](https://www.w3.org/WAI/PF/aria/terms#def_liveregion)を作成する要素を識別するために使用されます。 たとえば、チャットログ、メッセージ履歴、エラーログなどです。 他のタイプのライブリージョンとは対照的に、このロールは順番に並べられ、新しい情報はログの末尾にのみ追加されます。 このロールが要素に追加されると、ブラウザーは支援技術製品にアクセス可能なログイベントを送信し、ユーザーにそれを通知することができます。

デフォルトでは、更新にはライブリージョンの変更のみが含まれ、ユーザーがアイドル状態のときにアナウンスされます。 変更の際にライブリージョン全体を聞く必要がある場合、 `aria-atomic="true"` を設定するべきです。 できるだけ早くアナウンスし、ユーザーが中断する可能性がある場合は、より積極的な更新のために `aria-live="assertive"` を設定することができます。

### ユーザーエージェントと支援技術への影響

要素に `log` ロールが追加されたとき、またはそのような要素が可視になるとき、ユーザーエージェントは以下を行うべきです。

- オペレーティングシステムのアクセシビリティ API で `log` ロールを持つ要素を公開します。
- オペレーティングシステムのアクセシビリティ API がサポートされている場合は、アクセシビリティ API を使用してアクセス可能なログイベントを発生させます。

支援技術製品は、そのようなイベントをリスンし、それに応じてユーザーに以下を通知するべきです。

- `aria-live="assertive"` が設定されておらず、ユーザーが中断されている場合を除き、スクリーンリーダーは、ユーザーがアイドル状態のときにログ内の変更をアナウンスするべきです。
- スクリーン拡大鏡は、ログ更新が発生したことを視覚的に示すことができます。

> [!NOTE]
> 支援技術がどのようにこの技術を扱うべきかについての意見は異なる場合があります。 上記の情報は、これらの意見の 1 つで、したがって規範的ではありません。

### 例

#### 例 1: HTML コードにロールを追加する

以下のスニペットは、`log` ロールを HTML ソースコードに直接追加する方法を示しています。

```html
<div id="liveregion" class="region" role="log"></div>
```

#### 例 2: サンプルアプリケーションからのスニペット

このスニペットは AJAX チャットアプリケーションにおいてチャットログを作成します。

```html
<div id="chatArea" role="log">
  <ul id="chatRegion" aria-live="polite" aria-atomic="false">
    <li>AJAX チャットの使用を開始するには、ユーザー名を選択してください。</li>
  </ul>
  <ul
    id="userListRegion"
    aria-live="off"
    aria-relevant="additions removals text"></ul>
</div>
```

#### 動作する例

- <http://websiteaccessibility.donaldevans.com/2011/07/12/aria-log/>

### 注

- 要素に `log` ロールを使用すると、その要素には `aria-live="polite"` が暗黙で含まれます。
- 株式相場表示機のようにスクロールするテキストがある領域では、`marquee` ロールを代わりに使用するべきです。

### 使用された ARIA 属性

- [log](https://www.w3.org/TR/wai-aria/#log)

### 関連する ARIA 技術

- [marquee](https://www.w3.org/TR/wai-aria/#marquee) ロール

### 互換性

TBD: 一般的な UA と AT 製品の組み合わせに関するサポート情報を追加する

### その他のリソース

- ARIA のベストプラクティス - ライブリージョンの実装: <http://www.w3.org/TR/wai-aria-practices/#LiveRegions>
