### 4.3. Installing the required packages {#4-3-installing-the-required-packages}

XooNIps requires to be installed the following packages.

| gcc | gcc-c++ | glib-devel |
| --- | --- | --- |
| glib2-devel | libgsf-devel | php-mysql |
| php-gd | php-mbstring | php-devel |
| php-xml | php-pear | php-pecl-Fileinfo |
| poppler-utils | lynx | mysql-server |
| wget |   |   |

Execute the following commands to install the packages.

| **[root@xoonips-server ~]# yum -y install gcc gcc-c++ glib-devel glib2-devel libgsf-devel** |
| --- |
| **[root@xoonips-server ~]# yum -y install php-mysql php-gd php-mbstring php-devel php-xml php-pear** |
| **[root@xoonips-server ~]# yum -y install php-pecl-Fileinfo poppler-utils lynx** |
| **[root@xoonips-server ~]# yum -y install mysql-server wget make** |