# できる限り`div`要素は避ける

`div`要素は最後の手段です。

悪い例:

    <div class="chapter">
      ...
    </div>

良い例:

    <section>
      ...
    </section>


## 解説

仕様では`div`と`span`要素は何も意味しないとなっています。歴史的には様々な形でコンテンツをグルーピングするために利用されてきましたが、それらの多くはもはや必要のないものと言えるでしょう。

    <div id="contents">
      <div class="entry">
        ... <span class="published">1905年</span> ...
      </div><!-- /.entry -->
      ...
    </div><!-- /#contents -->

このようなHTMLで構成されているブログは今も時おり見かけるものです。理論上は`div`と`span`要素に加えて`a`要素及びフォーム・コントロール要素だけでウェブページを制作することは可能です。しかしこういったHTMLはメンテナンス性に大きく欠けます。開始タグについては概ね特徴的なクラス名が振られていることからあまり問題ないことと思いますが、終了タグは常に`</div>`でしょうから、その対応を把握するのはなかなか難しくなります。そのため例のように終了タグ付近にその対応をコメントとして埋め込む、といった対処をする必要に迫られます。

    <main>
      <article>
        ... <time datetime="1905">1905年</time> ...
      </article>
      ...
    </main>

恣意的な例ではありますが、公開日時は`time`要素で、記事全体は`article`要素で、複数の記事をまとめるには`main`要素というようにできます。これならば容易にHTML文書の構造を把握でき、保守できるでしょう。

もちろんスタイル目的でそれぞれに改めて`class`属性を振ることになるので、`div`要素でも同じではないかと考えがちですが、HTMLはCSSのためだけにあるわけではありません。適切な要素を利用することで、正しくコンテンツを解釈する機会を公平に与えられます。ブラウザーのリーダー・モード、スクリーン・リーダー、そしてもしかしたらGoogleにも、です。

仕様でも`div`要素の項にて「最後の手段の要素としてdiv要素を検討する」ことが強く推奨されています。できうる限り既存の他の適切な要素を探し利用するようにしましょう。
