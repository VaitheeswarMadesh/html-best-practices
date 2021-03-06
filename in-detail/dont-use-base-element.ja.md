# `base`要素を使わない

絶対パスや絶対URLの方が開発者とユーザーの双方に安全です。

悪い例:

    <head>
      ...
      <base href="/blog/">
      <link href="hello-world" rel="canonical">
      ...
    </head>

良い例:

    <head>
      ...
      <link href="/blog/hello-world" rel="canonical">
      ...
    </head>


## 解説

`base`要素で指定した`href`属性はHTML文書内のハイパーリンクの解決に、`target`属性はハイパーリンクの開き方に利用されます。うまく使えばHTML文書全体でのURLの書き方などを簡潔にできるでしょう。しかし同時に`a`要素や`form`要素などを書く時は常に`base`要素にどのような値が指定されているかを意識する必要がでてきます。

今は断片的なHTML文書を書き、何かしらのツールがそれをまとめウェブページとして完成させる時代です。そのような環境で他の断片的なHTML文書に書かれている（かもしれない）`base`要素を意識するのは苦痛でしょう。外部のリソースには意味がありませんし、内部リソースにはスラッシュで始まる絶対パスを、外部リソースには`https:`などで始まる絶対URLを利用するのが単純でわかりやすいはずです。

`target`属性の利用については難しいところです。とりあえずすべて`target=_blank`になるようにするのはなかなか興味深いアプローチです。ただ`form`要素での`target=_self`の指定忘れといった事態を考えると、やはり全面的に利用しない方が無難ではないでしょうか。
