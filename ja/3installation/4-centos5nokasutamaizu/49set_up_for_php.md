# 4.9. PHPの設定

XooNIpsの動作に必要な環境にするためPHPの設定ファイルを修正します。

| `[xoonips-server ~]#` **vi /etc/php.ini** | ← PHP設定ファイルの編集 |
| :--- | :--- |
| **allow\_url\_fopen = On** |  |
| ↓ |  |
| **allow\_url\_fopen = Off** | ← Offに修正する |

以下の設定値はXooNIpsサーバにファイルをアップロードする際に必要なメモリーサイズです。サーバの設計・構築に従って大きめの値を設定してください。

128MB以上のファイルをXooNIpsで扱う計画がある場合は本解説よりも大きな値を設定する必要があります。

設定値の範囲は memory\_limit &gt;= post\_max\_size &gt;= upload\_max\_filesize である必要があります。

| **memory\_limit = 16M** |  |
| :--- | :--- |
| ↓ |  |
| **memory\_limit = 128M** | ← 値を大きく設定する |
| **post\_max\_size = 8M** |  |
| ↓ |  |
| **post\_max\_size = 128M** | ← 値を大きく設定する |
| **upload\_max\_filesize = 2M** |  |
| ↓ |  |
| **upload\_max\_filesize = 128M** | ← 値を大きく設定する |
| **;session.use\_only\_cookies = 1** |  |
| ↓ |  |
| **session.use\_only\_cookies = 1** | ← コメントを外す |

マルチバイト文字列関数の設定

| **;mbstring.internal\_encording = EUC-JP** |  |
| :--- | :--- |
| ↓ |  |
| **mbstring.interlnal\_encording = EUC-JP** | ← コメントを外す |
| **;mbstring.detect\_order = auto** |  |
| ↓ |  |
| **mbstring.detect\_order = ASCII,EUC-JP,UTF8** | ← コメントを外し、ASCII,EUC-JP,UTF8を追加する |

変更した設定を有効にするため、Apacheの再起動をします。

| **\[xoonips-server ~\]\# /etc/init.d/httpd restart** | ← 設定を有効にするためApacheを再起動する |
| :--- | :--- |


