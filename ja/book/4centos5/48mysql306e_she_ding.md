### 4.8. MySQLの設定 {#4-8-mysql}

XooNIpsで使用するDatabaseシステムの設定を行います。

| `[root@xoonips-server ~]#` **vi /etc/my.cnf** | ← 設定ファイルの編集 |
| --- | --- |
| **[mysqld]**セクションに以下の2行を追加します。 |
| **default-character-set=ujis** |
| **skip-character-set-client-handshake** |

#### 4.8.1. MySQLの起動と自動起動設定 {#4-8-1-mysql}

| `[root@xoonips-server ~]#` **/etc/init.d/mysqld start** | ← MySQLサーバ起動 |
| --- | --- |
| `[root@xoonips-server ~]#` **chkconfig mysqld on** | ← MySQL自動起動設定 |

#### 4.8.2. MySQLパスワードの設定と不要データの削除 {#4-8-2-mysql}

| `[root@xoonips-server ~]#` **mysql -uroot** | ← MySQLサーバへrootユーザでログイン |
| --- | --- |
| rootユーザのパスワードを設定(例はmysqlroot@pass) |
| `mysql &gt;` **set password for root@localhost=password(&#039;mysqlroot@pass&#039;);** |
| `mysql &gt;` **delete from mysql.user where user=&#039;&#039;;** | ← 匿名ユーザを削除します。 |
| `mysql &gt;` **drop database test;** | ← testデータベースの削除 |

#### 4.8.3. XooNIps用データベースの作成 {#4-8-3-xoonips}

| xoonipsdbという名前でXooNIps用のデータベースを作成します。 |
| --- |
| `mysql &gt;` **create database xoonipsdb character set ujis;** |
| xoonipsdbにアクセスするユーザxoonipsuser,パスワードxoonips@passで作成します。 |
| `mysql &gt;` **grant all privileges on xoonipsdb.* to xoonipsuser@localhost identified by&#039;xoonips@pass&#039;;** |
| `mysql &gt;` **exit** | ← MySQLサーバからログアウトする。 |