---
title: "ARIA: feed ロール"
slug: Web/Accessibility/ARIA/Reference/Roles/feed_role
original_slug: Web/Accessibility/ARIA/Roles/feed_role
---

フィード (`feed`) は動的にスクロール可能な記事 (`article`) のリスト (`list`) で、ユーザーがスクロールすると記事がリストのどちらかの端から追加または削除されます。 フィード (`feed`) により、スクリーンリーダーは閲覧モードの読み取りカーソルを使用して、リッチコンテンツのストリームを読み込みながらスクロールすることを可能にし、ユーザーが読むにつれてコンテンツをさらにロードすることで無限にスクロールし続けることができます。

```html
<section role="feed" aria-busy="false">
  ...
  <article aria-posinset="427" aria-setsize="-1">...</article>
  <article aria-posinset="428" aria-setsize="-1">...</article>
  <article aria-posinset="429" aria-setsize="-1">...</article>
  ...
</section>
```

## 説明

フィードは、スクロール可能な記事 ([`article`](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/article_role)) のリスト ([list](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/list_role)) のためのページ構造であり、スクロールすることで、リストの先頭または末尾に記事が追加される場合があります。 このリストは、ウェブページと支援技術との間の相互運用契約を確立するもので、支援技術のユーザーが記事を読み、記事を前後にジャンプし、読み取りモードで新しい記事を確実にロードできるように、スクロールのインタラクションを管理します。 例としては、RSS フィード、ニュースフィード、Facebook (フェイスブック) 、Instagram (インスタグラム) 、Twitter (ツイッター) などのソーシャルメディアフィード、さらには電子商取引ページ上の関連商品のリストなどがあります。 これらのストリームは有限か無限であり、ユーザーがスクロールするにつれてコンテンツをさらにロードします。 フィードパターンを実装することで、スクリーンリーダーは読み取りモードでフィードコンテンツを確実に読み取り、ロードをトリガーすることができます。

フィード (`feed`) は、コンテナー要素であり、その子は {{htmlelement("article")}} であるか、記事 (`article`) ロールを持ちます。 フィード内の各記事は、`tabindex` が 0 または -1 でフォーカス可能であるべきです。 記事またはその子孫要素にフォーカスが移ったときに、記事をスクロールして表示するべきです。 記事の追加がブラウザーのメインスレッドを占有する場合は、フィード自体に `aria-busy="true"` を設定し、処理が終了したら必ず `false` に戻すようにしてください。 そうしないと、ユーザーに更新が表示されない場合があります。

優れたユーザーエクスペリエンスを確保するため、フィード (`feed`) の途中で記事を挿入または削除しないようにし、ユーザーがフィードの末端に到達する前に新しい記事をロードし、キーボードユーザーがフィード内をナビゲートできるように記事間でフォーカスを移動するためのキーボードコマンドを提供します。 下記のキーボードインタラクションを参照してください。

記事の数がわかっている場合は、記事自体に `aria-setsize` を設定してください。 ただし、総数が非常に大きい場合、不明確な場合、または頻繁に変わる場合は、`aria-setsize="-1"` を設定してフィードのサイズがわからないことを示します。

フィードパターンのもう 1 つの特徴は、斜め読みです。 フィード内の記事には、`aria-label` によるアクセス可能な名前と `aria-describeby` による説明の両方を含めることで、記事をナビゲートするときに、ラベルの後にどの要素を話すべきかをスクリーンリーダーに提案することができます。 タイトルと主要コンテンツを提供する記事内の要素を特定することで、支援技術は、ユーザーが記事から記事へとジャンプし、読みたい記事を効率的に見分けることを可能にする機能を提供できます。

フィードパターンは、ウェブページと支援技術の間に次の相互運用性に関する合意を確立することによって、信頼できる支援技術の読み取りモードでのインタラクションを可能にします。

1. フィードのコンテキストでは、ウェブページのコードは次の責任を負います。
   - どの記事に DOM フォーカスが含まれているかに基づいて、コンテンツを適切に視覚的にスクロールします。
   - どの記事に DOM フォーカスが含まれているかに基づいて、フィード記事をロードまたは削除します。

2. フィードのコンテキストでは、読み取りモードを持つ支援技術は次の責任を負います。
   - 記事要素またはその子孫の 1 つに DOM フォーカスがあることを保証することで、どの記事に読み取りカーソルがあるかを示します。
   - DOM フォーカスを次の記事および前の記事に移動するための読み取りモードキーを提供します。
   - 読み取りカーソルと DOM フォーカスをフィードの終わりより後ろとフィードの始まりより前に移動するための読み取りモードキーを提供します。

### キーボードインタラクション

フォーカスがフィード内にある場合は、次のような、または同様のインターフェイスをサポートすることをお勧めします。

- <kbd>Page Down</kbd>

  : 次の記事にフォーカスを移動します。

- <kbd>Page Up</kbd>

  : 前の記事にフォーカスを移動します。

- <kbd>Control + End</kbd>

  : フィードの後方で最初にフォーカス可能な要素にフォーカスを移動します。

- <kbd>Control + Home</kbd>

  : フィードの前方で最初にフォーカス可能な要素にフォーカスを移動します。

ブログ投稿のフィード内のコメントフィードなど、フィードがフィード内にネストしている場合、慣例では、<kbd>Tab</kbd> キーでネストしているフィードにタブ移動で入り、「外側の」記事からその記事内にネストしているフィードの最初の項目にナビゲートするための <kbd>Alt + Page Down</kbd> などの別のキーを提供します。 ネストしているフィードとメインフィードの間をナビゲートするには、<kbd>Control + End</kbd> で内側のフィードから外側のフィードの次の記事にフォーカスを移動します。

### 関連する WAI-ARIA のロール、ステート、プロパティ

- aria-label
  - : フィードに目に見えるタイトルがない場合、フィード (`feed`) 要素は [`aria-label`](https://w3c.github.io/aria/#aria-label) で指定されたラベルを持ちます。 もしそうしている場合は、`aria-labelledby` を参照してください。
- aria-labelledby
  - : フィードに目に見えるタイトルがある場合、フィード (`feed`) 要素はタイトルを含む要素を参照する [`aria-labelledby`](https://w3c.github.io/aria/#aria-labelledby) を持ちます。 そうでない場合は、`aria-label` を追加してください。
- aria-busy
  - : 記事をフィード (`feed`) に追加または削除しているときなど、忙しい場合は、更新操作中に `aria-busy="true"` を設定します。 操作が完了したら、必ず `false` にリセットしてください。 そうしないと、変更結果を見ることができないかもしれません。
- article
  - : フィード内のコンテンツの各セクションは、{{htmlelement("article")}} または記事 ([`article`](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/article_role)) ロールを持つ要素に含まれているべきです。 各記事 (`article`) は、その記事のタイトルまたは識別ラベルとしての機能を果たすその他の子を参照する [`aria-labelledby`](https://w3c.github.io/aria/#aria-labelledby) を持つべきです。 各記事は、好ましくは、その記事の主要コンテンツとしての機能を果たす記事内の１つ以上の要素を参照する [`aria-describedby`](https://w3c.github.io/aria/#aria-describedby) を持つべきです。 各記事 (`article`) 要素は、フィード内の位置を表す値に設定された [`aria-posinset`](https://w3c.github.io/aria/#aria-posinset) と、ロード済みの記事の総数またはフィード内の総数を表す値のどちらかに設定された [`aria-setsize`](https://w3c.github.io/aria/#aria-setsize) を持ちます。 それは、どちらの値がユーザーにとってより役立つかによって異なります。 フィード内の総数がわからない場合は、`aria-setsize="-1"` を設定してください。

### 必要な JavaScript 機能

なし (任意の属性が必要とする場合を除く。 例えば、必要に応じて更新操作中に `aria-busy` を `true` に設定し、完了したら `false` に設定します。)

## 例

[フィードパターンの実装例](https://w3c.github.io/aria-practices/examples/feed/feed.html) (英語)

## 仕様書

{{Specifications}}

## スクリーンリーダーのサポート

Coming soon

## 関連情報

- HTML {{htmlelement("article")}} 要素
- [HTML のリスト](/ja/docs/Web/HTML/Reference/Elements/ul)
- [ARIA: article ロール](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/article_role)
- [ARIA: list ロール](/ja/docs/Web/Accessibility/ARIA/Reference/Roles/list_role)
- [WAI-ARIA Authoring Practices](https://www.w3.org/TR/wai-aria-practices-1.1/#feed) — フィードデザインパターンの実装に関する詳細。 (英語)

1. [**WAI-ARIA ロール**](/ja/docs/Web/Accessibility/ARIA/Reference/Roles){{ListSubpagesForSidebar("/ja/docs/Web/Accessibility/ARIA/Roles")}}
