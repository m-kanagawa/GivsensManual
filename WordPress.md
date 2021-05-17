#  WordPressネタ

# 目次
1. [サブディレクトリ(/wp/)にインストールしたWordPressをドメイン直下に表示する](#a01)
1. [郵便番号自動入力](#a02)

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

<a id="a02"></a>
##郵便番号自動入力（MW WP Form）
`scripts.php`に下記を入力（コメントアウトされている）
`\lib\functions\scripts.php`
```
if (!is_admin()) {
	function register_script(){
		//自動住所入力を設置
		wp_register_script('ajaxzip3-js', 'https://ajaxzip3.github.io/ajaxzip3.js', false, '1.0', true);
	}
	function add_script() {
		register_script();
		if(is_page('entry')) {
			wp_enqueue_script('ajaxzip3-js');
		}
	}
	add_action('wp_enqueue_scripts', 'add_script');
}
```
`main.js`に下記を入力
```
$( '#zip_code' ).keyup( function() {
	AjaxZip3.zip2addr( this, '', 'address','address' );
});
```
HTMLに下記を入力
```
<dl>
	<dt><label for="zip_code">郵便番号</label></dt>
	<dd>[mwform_text name="zip_code" id="zip_code" class="zip_code" conv_half_alphanumeric="false"]</dd>
</dl>
<dl>
	<dt><label for="address">住所</label></dt>
	<dd>[mwform_text name="address" id="address"]</dd>
</dl>
```

