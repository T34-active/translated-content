---
title: アクセシビリティ
slug: Learn_web_development/Core/Accessibility
original_slug: Learn/Accessibility
l10n:
  sourceCommit: 26e2f9883e0e73def04c0e86fec6da3ec42e66b3
---

{{LearnSidebar}}

ウェブ開発者になりたい場合、HTML, CSS, JavaScript の学習は役立ちます。しかし知識は単に技術を使うよりも前に進める必要があります。それらを責任を持って使う必要があり、その結果ウェブサイトの聴衆を増やし、またそれを使わないことに縛らないことになります。これを達成するには、一般的な成功事例 ([HTML](/ja/docs/Learn/HTML), [CSS](/ja/docs/Learn/CSS), [JavaScript](/ja/docs/Learn/JavaScript) のトピックに示されています) を積み上げ、[ブラウザー横断テスト](/ja/docs/Learn/Tools_and_testing/Cross_browser_testing)を行って、最初からアクセシビリティを考慮しておきます。このモジュールでは後者を詳しく扱います。

## 概要

あるサイトが「アクセシビリティがある」と記述されている場合、それは、ユーザーがどのようにウェブにアクセスしているかにかかわらず、すべてのユーザーがその機能やコンテンツを使用することができることを意味しています。

- ウェブサイトは、キーボード、マウス、タッチ画面のユーザー、そしてスクリーンリーダーや Alexa や Google Home のような音声アシスタントを含む、ユーザーがウェブにアクセスする他のどんな方法でもアクセス可能であるべきです。
- アプリケーションは、聴覚、視覚、身体、認知能力に関係なく、理解しやすく、利用しやすいものでなければなりません。
- また、ウェブサイトは害を発生させるものであってはなりません。動きのようなウェブ機能は、片頭痛やてんかん発作を引き起こす可能性があります。

**既定では、HTML は正しく使用すればアクセシブルです。** ウェブアクセシビリティには、誰が、どのようにウェブにアクセスするかに関係なく、コンテンツがアクセシブルであり続けることを保証することが含まれます。

Firefox のアクセシビリティインスペクターは、ウェブページのアクセシビリティの課題を調べるのにとても有益なツールです。以下の動画は、このツールの素晴らしい紹介です。

{{EmbedYouTube("7mqqgIxX_NU")}}

## 前提知識

このモジュールの大半の理解には、少なくとも [HTML](/ja/docs/Learn/HTML), [CSS](/ja/docs/Learn/CSS), [JavaScript](/ja/docs/Learn/JavaScript) の最初の 2 モジュールを通して読むのが良いでしょうし、 たぶんもっと良いのは、関連するテクノロジートピックを進めるにつれて、関連するアクセシビリティの部分を進めるのが良いでしょう。

> [!NOTE]
> 自分のファイルを作れない コンピューター/タブレット/その他の端末で作業する場合、コードの実例の大半を [JSBin](https://jsbin.com/) や [Glitch](https://glitch.com/) などのオンラインコーディングプログラム内で試すことができます。

## ガイド

- [アクセシビリティとは](/ja/docs/Learn/Accessibility/What_is_accessibility)
  - : この記事では実際アクセシビリティとは何かについてよく観察するモジュールから開始します — これには考慮が必要な人のグループや、いろいろな人がウェブとやり取りするのになぜ、どんなツールを使うのかや、アクセシビリティをウェブ開発の作業フローに取り組む方法が含まれます。
- [HTML: アクセシビリティの良き基本](/ja/docs/Learn/Accessibility/HTML)
  - : ウェブコンテンツをアクセシビリティ高くすることの多くの部分は、どんなときも正しい HTML 要素を正しい目的で使うことです。 この記事ではアクセシビリティを最大化するためにどう HTML が使われるかの詳細を見ていきます。
- [CSS と JavaScript のアクセシビリティのベストプラクティス](/ja/docs/Learn/Accessibility/CSS_and_JavaScript)
  - : CSS と JavaScript も、適切に使うと、アクセシビリティの高いウェブ体験を可能にする力を持っていますが、誤用されると目立ってアクセシビリティを害することもあります。この記事では、複雑なコンテンツでもなるべくアクセシビリティ高める CSS と JavaScript のいくつかの成功事例をざっと見ます。
- [WAI-ARIA の基本](/ja/docs/Learn/Accessibility/WAI-ARIA_basics)
  - : 前の記事に続いて、複雑な UI に非セマンティックな HTML や動的な JavaScript-更新コンテンツを作ることは難しいかもしれません。WAI-ARIA は、そうした問題をブラウザーと補助技術が認識できるセマンティクスを追加することで補助し、ユーザーに何が起きているのかを知らせるのに使うテクノロジーです。ここではアクセシビリティを改善する基本レベルの使用方法を示します。
- [アクセシブルなマルチメディア](/ja/docs/Learn/Accessibility/Multimedia)
  - : アクセシビリティの問題を起こす可能性がある他のカテゴリーは、マルチメディアです。ビデオ、オーディオ、およびイメージのコンテンツには、補助技術とユーザーが理解できるような、適切な代替テキストを付与する必要があります。どのように表示されるべきか分かるように。
- [モバイルのアクセシビリティ](/ja/docs/Learn/Accessibility/Mobile)
  - : モバイル端末でのウェブへのアクセスが増えるとともに、アクセシビリティのツールが本格的に提供されている iOS や Android のような一般的なプラットフォームが普及しています。これらのプラットフォームでのあなたのウェブコンテンツのアクセシビリティを考えることが重要です。モバイル特有のアクセシビリティについて検討しましょう。

## 評価

- [アクセシビリティのトラブルシューティング](/ja/docs/Learn/Accessibility/Accessibility_troubleshooting)
  - : このモジュールの評価では、分析と修正が必要な多くのアクセシビリティの問題があるシンプルなサイトを紹介します。

## 関連情報

- [Start Building Accessible Web Applications Today](https://egghead.io/courses/start-building-accessible-web-applications-today) — Marcy Sutton によるすばらしい動画チュートリアル
- [Deque University resources](https://dequeuniversity.com/resources/) — コードサンプルやスクリーンリーダーリファレンスやその他の役立つリソースを含む
- [WebAIM resources](https://webaim.org/resources/) — ガイド、チェックリスト、ツールなどを含む
