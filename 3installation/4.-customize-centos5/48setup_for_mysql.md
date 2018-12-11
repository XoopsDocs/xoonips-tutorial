# 4.8. Setup for MySQL

Set up for a database system to be used on XooNIps:

| **\[root@xoonips-server ~\]\# vi /etc/my.cnf** | ← Config file editing. |
| :--- | :--- |
| Add the following two lines in the section of \[mysqld\]. |  |
| **default-character-set=ujis** |  |
| **skip-character-set-client-handshake** |  |

## 4.8.1. MySQL startup and automatic startup. <a id="4-8-1-mysql-startup-and-automatic-startup"></a>

| **\[root@xoonips-server ~\]\# /etc/init.d/mysqld start** | ← MySQL server startup. |
| :--- | :--- |
| **\[root@xoonips-server ~\]\# chkconfig mysqld on** | ← MySQL automatic startup |

## 4.8.2. Set a MySQL password and delete unnecessary data. <a id="4-8-2-set-a-mysql-password-and-delete-unnecessary-data"></a>

| **\[root@xoonips-server ~\]\# mysql -uroot** | ← Log into the MySQL server as root user. |
| :--- | :--- |
| Define the password for root user. \(Example: mysqlroot@pass\) |  |
| **mysql &gt; set password for root@localhost=password\('mysqlroot@pass'\);** |  |
| **mysql &gt; delete from mysql.user where user='';** | ← Delete anonymous users. |
| **mysql &gt; drop database test;** | ← Delete test database. |

## 4.8.3. Create a database for XooNIps. <a id="4-8-3-create-a-database-for-xoonips"></a>

| Create a database for XooNIps and name it xoonipsdb. |  |
| :--- | :--- |
| **mysql &gt; create database xoonipsdb character set ujis;** |  |
| Create it with the user name: xoonipsuser, the password: xoonips@pass to access xoonipsdb. |  |
| **mysql &gt; grant all privileges on xoonipsdb.\* to xoonipsuser@localhost identified by'xoonips@pass';** |  |
| **mysql &gt; exit** | ← Log out of MySQL server. |

