### 4.9. PHPの設定 {#4-9-php}

XooNIpsの動作に必要な環境にするためPHPの設定ファイルを修正します。

| `[xoonips-server ~]#` **vi /etc/php.ini** | ← PHP設定ファイルの編集 |
| --- | --- |
| **allow_url_fopen = On** |
| ↓ |
| **allow_url_fopen = Off** | ← Offに修正する |

以下の設定値はXooNIpsサーバにファイルをアップロードする際に必要なメモリーサイズです。サーバの設計・構築に従って大きめの値を設定してください。

128MB以上のファイルをXooNIpsで扱う計画がある場合は本解説よりも大きな値を設定する必要があります。

設定値の範囲は memory_limit &gt;= post_max_size &gt;= upload_max_filesize である必要があります。

| **memory_limit = 16M** |
| --- |
| ↓ |
| **memory_limit = 128M** | ← 値を大きく設定する |
| **post_max_size = 8M** |
| ↓ |
| **post_max_size = 128M** | ← 値を大きく設定する |
| **upload_max_filesize = 2M** |
| ↓ |
| **upload_max_filesize = 128M** | ← 値を大きく設定する |
| **;session.use_only_cookies = 1** |
| ↓ |
| **session.use_only_cookies = 1** | ← コメントを外す |

マルチバイト文字列関数の設定

| **;mbstring.internal_encording = EUC-JP** |
| --- |
| ↓ |
| **mbstring.interlnal_encording = EUC-JP** | ← コメントを外す |
| **;mbstring.detect_order = auto** |
| ↓ |
| **mbstring.detect_order = ASCII,EUC-JP,UTF8** | ← コメントを外し、ASCII,EUC-JP,UTF8を追加する |

変更した設定を有効にするため、Apacheの再起動をします。

| **[xoonips-server ~]# /etc/init.d/httpd restart** | ← 設定を有効にするためApacheを再起動する |
| --- | --- |