# 4.9. Set up for PHP

Modify the PHP config files to set the environment for XooNIps.

| **\[xoonips-server ~\]\# vi /etc/php.ini** | ← PHP config file editing. |
| :--- | :--- |
| **allow\_url\_fopen = On** |  |
| ↓ |  |
| **allow\_url\_fopen = Off** | ← Change it from "On" to "Off". |

The following set values are the required memory sizes for uploading files to a XooNIps server. Adjust them according to the server's structure if necessary.

If it is expected to use files sized 128 MB or bigger on XooNIps, it requires bigger value than the indicated in this manual.

The range of set value have to be memory\_limit &gt;= post\_max\_size &gt;= upload\_max\_filesize

| **memory\_limit = 16M** |  |
| :--- | :--- |
| ↓ |  |
| **memory\_limit = 128M** | ← Set the value bigger. |
| **post\_max\_size = 8M** |  |
| ↓ |  |
| **post\_max\_size = 128M** | ← Set the value bigger. |
| **upload\_max\_filesize = 2M** |  |
| ↓ |  |
| **upload\_max\_filesize = 128M** | ← Set the value bigger. |
| **;session.use\_only\_cookies = 1** |  |
| ↓ |  |
| **session.use\_only\_cookies = 1** | ← Take out comments. |

Set up Multi-byte string functions

| **;mbstring.internal\_encording = EUC-JP** |  |
| :--- | :--- |
| ↓ |  |
| **mbstring.interlnal\_encording = EUC-JP** | ← Take out comments. |
| **;mbstring.detect\_order = auto** |  |
| ↓ |  |
| **mbstring.detect\_order = ASCII,EUC-JP,UTF8** | ← Take out comments and add ASCII,EUC-JP,UTF8. |

Restart Apache to make the setup valid.

\| **\[xoonips-server ~\]\# /etc/init.d/httpd restart** \| ← Restart the Apache to make the setup valid. \| \| --- \| --- \|

