---
title: devtools.network
slug: Mozilla/Add-ons/WebExtensions/API/devtools/network
---

{{AddonSidebar}}

> [!NOTE]
> このページは Firefox 54 に存在する WebExtensions devtools APIs を記述しています。この API は [Chrome devtools APIs](https://developer.chrome.com/extensions/devtools) に基づいていますが、Firefox では実装されていない多くの機能があり、よってここに文書化されていません。現在欠けている機能を見るには、 [Limitations of the devtools APIs](/ja/docs/Mozilla/Add-ons/WebExtensions/Using_the_devtools_APIs#limitations_of_the_devtools_apis) を見てください。

`devtools.network` API によって開発ツール拡張機能では開発ツールが付属しているウィンドウ(インスペクト対象ウィンドウ)に関連するネットワークリクエストの情報を取得できます。

すべての `devtools` API と同様に、この API は manifest.json [devtools_page](/ja/docs/Mozilla/Add-ons/WebExtensions/manifest.json/devtools_page) キー内に定義されたドキュメントや、拡張機能が作成するその他の開発ツールドキュメント(例えば拡張機能が作ったパネル自身のドキュメント)の中だけでコードを利用できます。これ以上は [開発ツールを拡張する](/ja/docs/Mozilla/Add-ons/WebExtensions/Extending_the_developer_tools)を見てください。

## Events

- [`devtools.network.onNavigated`](/ja/docs/Mozilla/Add-ons/WebExtensions/API/devtools.network/onNavigated)
  - : ユーザーが新規ページのインスペクト対象ウィンドウに移動した時に発火します

## ブラウザーの互換性

{{Compat}}

{{WebExtExamples("h2")}}

> [!NOTE]
> この API は Chromium の [`chrome.devtools.network`](https://developer.chrome.com/extensions/devtools_network) API に基づいています。また、このドキュメントは bookmarks.json における Chromium のコードに基づいています。

<!--
// Copyright 2015 The Chromium Authors. All rights reserved.
//
// Redistribution and use in source and binary forms, with or without
// modification, are permitted provided that the following conditions are
// met:
//
//    * Redistributions of source code must retain the above copyright
// notice, this list of conditions and the following disclaimer.
//    * Redistributions in binary form must reproduce the above
// copyright notice, this list of conditions and the following disclaimer
// in the documentation and/or other materials provided with the
// distribution.
//    * Neither the name of Google Inc. nor the names of its
// contributors may be used to endorse or promote products derived from
// this software without specific prior written permission.
//
// THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
// "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
// LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
// A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
// OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
// SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
// LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
// DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
// THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
// (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
// OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
-->
