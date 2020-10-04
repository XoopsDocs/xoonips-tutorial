# 4.8. MySQLの設定

XooNIpsで使用するDatabaseシステムの設定を行います。

| `[root@xoonips-server ~]#` **vi /etc/my.cnf** | ← 設定ファイルの編集 |
| :--- | :--- |
| **\[mysqld\]**セクションに以下の2行を追加します。 |  |
| **default-character-set=ujis** |  |
| **skip-character-set-client-handshake** |  |

## 4.8.1. **MySQLの起動と自動起動設定** <a id="4-8-1-mysql-startup-and-automatic-startup"></a>

| `[root@xoonips-server ~]#` **/etc/init.d/mysqld start** | ← MySQLサーバ起動 |
| :--- | :--- |


| `[root@xoonips-server ~]#` **chkconfig mysqld on** | ← MySQL自動起動設定 |
| :--- | :--- |


## 4.8.2. **MySQLパスワードの設定と不要データの削除** <a id="4-8-2-set-a-mysql-password-and-delete-unnecessary-data"></a>

| `[root@xoonips-server ~]#` **mysql -uroot** | ← MySQLサーバへrootユーザでログイン |
| :--- | :--- |
| rootユーザのパスワードを設定\(例はmysqlroot@pass\) |  |
| `mysql >` **set password for root@localhost=password\('mysqlroot@pass'\);** |  |
| `mysql >` **delete from mysql.user where user='';** | ← 匿名ユーザを削除します。 |
| `mysql >` **drop database test;** | ← testデータベースの削除 |

## 4.8.3. **XooNIps用データベースの作成** <a id="4-8-3-create-a-database-for-xoonips"></a>

| xoonipsdbという名前でXooNIps用のデータベースを作成します。 |  |
| :--- | :--- |
| `mysql >` **create database xoonipsdb character set ujis;** |  |
| xoonipsdbにアクセスするユーザxoonipsuser,パスワードxoonips@passで作成します。 |  |
| `mysql >` **grant all privileges on xoonipsdb.\* to xoonipsuser@localhost identified by'xoonips@pass';** |  |
| `mysql >` **exit** | ← MySQLサーバからログアウトする。 |

