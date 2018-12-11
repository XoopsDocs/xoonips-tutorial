# 6. Install XooNIps

Install XOOPS, the platform of XooNIps.

| Download the most updated version of XOOPS from the official website.\(Currently the most updated version is 2.1.7. as of March 2009.\) |  |
| :--- | :--- |
| **\[root@xoonips-server ~\]\# wget** [http://downloads.sourceforge.net/xoopscube/Package\_Legacy\_2\_1\_7.zip](http://downloads.sourceforge.net/xoopscube/Package_Legacy_2_1_7.zip) |  |
| **\[root@xoonips-server ~\]\# unzip Package\_Legacy\_2\_1\_7.zip** | ← Expand the downloaded files. |
| Copy the expanded files to the web server document root. |  |
| **\[root@xoonips-server ~\]\# cp -R Package\_Legacy/html/ /var/www/** |  |
| **\[root@xoonips-server ~\]\# rm -rf Package\_Legacy** | ← Delete the expanded directories. |
| **\[root@xoonips-server ~\]\# rm -f Package\_Legacy\_2\_1\_7.zip** | ← Delete the downloaded files. |
| **\[root@xoonips-server ~\]\# chmod 777 /var/www/html/uploads** | ← Change permissions. |
| **\[root@xoonips-server ~\]\# chmod 777 /var/www/html/cache** | ← Change permissions. |
| **\[root@xoonips-server ~\]\# chmod 777 /var/www/html/templates\_c** | ← Change permissions. |
| **\[root@xoonips-server ~\]\# chmod 666 /var/www/html/mainfile.php** | ← Change permissions. |

