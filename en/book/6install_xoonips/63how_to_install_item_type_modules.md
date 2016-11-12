### 6.3.�How to install item type modules: {#6-3-how-to-install-item-type-modules}

Install item type modules.

| Copy the item type module to the module directory. |
| --- |
| **[root@xoonips-server ~]# cp -R xoonips-3.44/itemtypes/* /var/www/html/modules/** |

#### 6.3.1.�Setup for item type modules {#6-3-1-setup-for-item-type-modules}

The procedure is the same as XooNIps module.

The types of item type module vary with the structure of the website.

![](../../assets/xoonips-install03.png)

Click on [Module Installation]

![](../../assets/xoonips-install32.png)

Click on the install icon at &quot;Control&quot;. (same as XooNIps installation)

#### 6.3.2.�Close the XooNIps installation {#6-3-2-close-the-xoonips-installation}

| **[root@xoonips-server ~]# rm -f xoonips-3.44.tar.gz** | ← Delete downloaded files. |
| --- | --- |
| **[root@xoonips-server ~]# rm -rf xoonips-3.44** | ← Delete expanded directories. |