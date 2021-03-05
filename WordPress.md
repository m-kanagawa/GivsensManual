#  WordPressネタ

# 目次
1. [サブディレクトリ(/wp/)にインストールしたWordPressをドメイン直下に表示する](#a01)

<a id="a01"></a>

## サブディレクトリ(/wp/)にインストールしたWordPressをドメイン直下に表示する
例:`https://example.com/wp/` → `https://example.com/`
1. 管理画面＞設定＞一般
サイトアドレス(URL)を変更<br>
※WordPressアドレス(URL)はそのまま<br>


1. サブディレクトリ（WordPressの一番上の階層）の中にある、<br>index.php をエディタで開く
※念のため、バックアップをとる<br>
17行目あたりの「/wp-blog-header.php」を「/wp/wp-blog-header.php」に変更して保存<br>
※「/wp/」は実際にwordpressが入っているサブディレクトリ名<br>
```
require( dirname( __FILE__ ) . '/wp-blog-header.php' );
↓
require( dirname( __FILE__ ) . '/wp/wp-blog-header.php' );
```
<br>

1. index.phpと.htaccess(index.phpと同じ階層にある)をドメイン直下に移動<br>
※ドメイン直下に.htaccessがある場合は確認が必要（上書きではなく追記になると思います）<br><br>
