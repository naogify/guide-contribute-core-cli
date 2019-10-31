# [WordPress] CoreとCLIのコントリビュートの仕方

## Core
### ローカル開発環境を用意

VVV （varyingvagrantvagrants）

https://varyingvagrantvagrants.org/

#### インストールの仕方
配布したフォルダ内の `instructions.html`を参照。

### Ticketを探す

https://make.wordpress.org/core/reports/

https://core.trac.wordpress.org/tickets/good-first-bugs

### パッチを送る
#### 修正
`cd ./WCTOKYO2019/vvv/www/wordpress-develop/public_html/src/`

バグを修正。

#### テスト
```
vagrant ssh
cd /srv/www/wordpress-develop/public_html/

//gruntが使えることを確かめる
grunt --help

cp wp-tests-config-sample.php wp-tests-config.php

//wp-config.phpの設定値をコピー&ペースト
vi wp-tests-config.php

grunt test
```

#### パッチを作成

変更をadd

`svn add /src/modified-file.php`

パッチを作成

`svn diff /src/modified-file.php > 00000.diff`

パッチファイルをTicketにアップロード + コメントを書く。

### 参考
#### 始め方
https://make.wordpress.org/core/handbook/tutorials/getting-started/
#### テスト
https://make.wordpress.org/core/handbook/testing/patch/
#### パッチを作成
https://make.wordpress.org/core/handbook/tutorials/working-with-patches/#creating-and-applying-patches-withthe-command-line
#### パッチをアップロード
https://make.wordpress.org/core/handbook/tutorials/trac/submitting-a-patch/


## WP-CLI
### 参考
#### コントリビュートの仕方
https://make.wordpress.org/cli/handbook/contributing/
#### プルリクエスト
https://make.wordpress.org/cli/handbook/pull-requests/
#### Good First Issue
https://github.com/wp-cli/wp-cli/labels/good-first-issue

