### 4.9. Set up for PHP {#4-9-set-up-for-php}

Modify the PHP config files to set the environment for XooNIps.

| **[xoonips-server ~]# vi /etc/php.ini** | ← PHP config file editing. |
| --- | --- |
| **allow_url_fopen = On** |
| ↓ |
| **allow_url_fopen = Off** | ← Change it from &quot;On&quot; to &quot;Off&quot;. |

The following set values are the required memory sizes for uploading files to a XooNIps server. Adjust them according to the server&#039;s structure if necessary.

If it is expected to use files sized 128 MB or bigger on XooNIps, it requires bigger value than the indicated in this manual.

The range of set value have to be memory_limit &gt;= post_max_size &gt;= upload_max_filesize

| **memory_limit = 16M** |
| --- |
| ↓ |
| **memory_limit = 128M** | ← Set the value bigger. |
| **post_max_size = 8M** |
| ↓ |
| **post_max_size = 128M** | ← Set the value bigger. |
| **upload_max_filesize = 2M** |
| ↓ |
| **upload_max_filesize = 128M** | ← Set the value bigger. |
| **;session.use_only_cookies = 1** |
| ↓ |
| **session.use_only_cookies = 1** | ← Take out comments. |

Set up Multi-byte string functions

| **;mbstring.internal_encording = EUC-JP** |
| --- |
| ↓ |
| **mbstring.interlnal_encording = EUC-JP** | ← Take out comments. |
| **;mbstring.detect_order = auto** |
| ↓ |
| **mbstring.detect_order = ASCII,EUC-JP,UTF8** | ← Take out comments and add ASCII,EUC-JP,UTF8. |

Restart Apache to make the setup valid.

| **[xoonips-server ~]# /etc/init.d/httpd restart** | ← Restart the Apache to make the setup valid. |
| --- | --- |