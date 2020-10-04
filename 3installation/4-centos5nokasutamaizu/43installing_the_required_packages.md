# 4.3. 必要パッケージのインストール

XooNIpsのインストールには以下のパッケージをインストールする必要があります。

| gcc | gcc-c++ | glib-devel |
| :--- | :--- | :--- |
| glib2-devel | libgsf-devel | php-mysql |
| php-gd | php-mbstring | php-devel |
| php-xml | php-pear | php-pecl-Fileinfo |
| poppler-utils | lynx | mysql-server |
| wget | make | unzip |

以下のコマンドで必要パッケージをインストールします。

| `[root@xoonips-server ~]#` **yum -y install gcc gcc-c++ glib-devel glib2-devel libgsf-devel** |
| :--- |
| `[root@xoonips-server ~]#` **yum -y install php-mysql php-gd php-mbstring php-devel php-xml php-pear** |
| `[root@xoonips-server ~]#` **yum -y install php-pecl-Fileinfo poppler-utils lynx** |
| `[root@xoonips-server ~]#` **yum -y install mysql-server wget make unzip** |

