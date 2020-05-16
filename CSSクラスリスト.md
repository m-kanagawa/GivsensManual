# CSSクラスリスト

# 目次
1. [テキスト関係](#a01)
1. [レスポンシブ用クラス](#a02)
1. [その他](#a03)

<a id="a01"></a>
## テキスト関係
-----
### ●文字スタイル
クラス名 | 説明 | 定義場所
---------|----------|----------
bold | テキスト太字| _general.scss
underline | テキスト下線| _general.scss

### ●文字サイズ
クラス名 | 説明 | 定義場所
---------|----------|----------
text-xxlarge | PC:36px SP:24px | _general.scss
text-xlarge | PC:28px SP:20px | _general.scss
text-large | PC:20px SP:16px | _general.scss
text-small | PC:12px SP:12px | _general.scss
text-xsmall | PC:10px SP:10px | _general.scss

### ●配置
クラス名 | 説明 | 定義場所
---------|----------|----------
text-left | テキスト左寄せ | _general.scss
text-center | テキストセンタリング | _general.scss
text-right | テキスト右寄せ | _general.scss
pc-text-left | PCのみテキスト左寄せ | _general.scss
pc-text-center | PCのみテキストセンタリング | _general.scss
pc-text-right | PCのみテキスト右寄せ | _general.scss
sp-text-left | SPのみテキスト左寄せ | _general.scss
sp-text-center | SPのみテキストセンタリング | _general.scss
sp-text-right | SPのみテキスト右寄せ | _general.scss

<a id="a02"></a>
## レスポンシブ用クラス
-----
デバイスごとに要素の表示・非表示を切り替えるために使用する。
クラス名 | 説明 | 定義場所
---------|----------|----------
pc-only | PCのみ表示、SPでは非表示。 | _general.scss
sp-only | SPのみ表示、PCでは非表示。 | _general.scss

<a id="a03"></a>
## その他
-----
クラス名 | 説明 | 定義場所
---------|----------|----------
mk | ホバー時に透過。バナーなどでよく使う | _general.scss
clerfix | floatプロパティによる回り込みを解除 | _general.scss

<a id="a04"></a>
## グリッドシステムについて
軽量なResponsive Grid Systemというcssフレームワークを利用しています。
```html
<section>
  <div class="container">
    <div class="row">
      <div class="col span_6">
        <figure>
          <img src="" alt="">
        </figure>
      </div>
      <div class="col span_6">
        <p>テキストテキストテキストテキスト</p>
      </div>
    </div>
  </div>
</section>
```

