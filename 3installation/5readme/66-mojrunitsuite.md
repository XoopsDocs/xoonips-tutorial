# 6.6. 支援モジュールについて

標準状態では使いにくいシステムモジュールの代わりに利用できるモジュールや悪意のある攻撃から守るProtecterモジュールなどがあります

アイテムへのコメント機能を利用する際にはaltsysモジュールとD3forumモジュールのインストールが必要です。

ここではXooNIpsでコメント機能を利用するためにaltsysモジュールとD3forumモジュールのインストールの簡単な説明を行います。

詳細な情報は配布サイトを確認してください。http://xoops.peak.ne.jp/

## **6.6.1. altsysモジュールのインストール**

標準システムモジュールの代替モジュールであるaltsysモジュールのインストールを行います。

mainfile.phpを一点修正します

| `[xoonips-server ~]#` **vi /var/www/html/mainfile.php** | ← mainfile.phpファイルの編集 |
| :--- | :--- |
| **define\('XOOPS\_TRUST\_PATH',''\);** |  |
| ↓ |  |
| **define\('XOOPS\_TRUST\_PATH','/var/www/xoops\_trust\_path'\);** | ← XOOPS\_TRUST\_PATHの設定を行う |

配布サイトから最新版モジュールをダウンロードします。

| `[root@xoonips-server ~]#` **tar -xzvf altsys-0.6.tar.gz** | ← 取得ファイルの展開 |
| :--- | :--- |
| `[root@xoonips-server ~]#` **cp -R xoops\_trust\_path /var/www/** | ← 展開ファイルのコピー |
| `[root@xoonips-server ~]#` **cp -R html/modules/altsys /var/www/html/modules** | ← 展開ファイルのコピー |
| `[root@xoonips-server ~]#` **cp html/preload /\* vaw/www/html/preload/** | ← 展開ファイルのコピー |

この後はXooNIpsやアイテムタイプモジュールと同様に管理者メニューのモジュールインストールからインストールを行ってください。

## **6.6.2. D3forumのインストール**

アイテムへのコメント機能を利用するために必要なd3モジュールのインストールを行います。

あらかじめaltsysモジュールのインストールを済ませておく必要があります。

配布サイトから最新版モジュールをダウンロードします。

| `[root@xoonips-server ~]#` **tar -xzvf d3forum-0.8.tar.gz** | ← 取得ファイルの展開 |
| :--- | :--- |
| `[root@xoonips-server ~]#` **cp -R xoops\_trust\_path/modules /var/www/xoops\_trust\_path** | ← 展開ファイルのコピー |
| `[root@xoonips-server ~]#` **cp -R html/modules/d3forum /var/www/html/modules** | ← 展開ファイルのコピー |
| `[root@xoonips-server ~]#` **cp html/class/smarty/plugins/\* var/www/html/class/smarty/plugins/** | ← 展開ファイルのコピー |

この後はXooNIpsやアイテムタイプモジュールと同様に管理者メニューのモジュールインストールからインストールを行ってください。

