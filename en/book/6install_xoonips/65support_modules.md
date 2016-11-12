### 6.5.�Support modules {#6-5-support-modules}

Supporting modules are, for example, alternative modules for the system modules whose standard status can not satisfy by itself, and protector modules against malicious attacks.

For using the function to comment, install an altsys module and a D3forum module.

The following briefly shows how to install an altsys module and a D3forum module, which are required for utilizing the comment functions on XooNIps.

For detailed information, check the website http://xoops.peak.ne.jp/

#### 6.5.1.�Install an altsys module {#6-5-1-install-an-altsys-module}

How to install an altsys module, an alternative module for standard system modules:

Modify mainfile.php

| **[xoonips-server ~]# vi /var/www/html/mainfile.php** | ← mainfile.php file edition. |
| --- | --- |
| **define(&#039;XOOPS_TRUST_PATH&#039;,&#039;&#039;);** |
| ↓ |
| **define(&#039;XOOPS_TRUST_PATH&#039;,&#039;/var/www/xoops_trust_path&#039;);** | ← Set up for XOOPS_TRUST_PATH |

Download the most updated module from the website.

| **[root@xoonips-server ~]# tar -xzvf altsys-0.6.tar.gz** | ← Expand the obtained files. |
| --- | --- |
| **[root@xoonips-server ~]# cp -R xoops_trust_path /var/www/** | ← Copy the expanded files. |
| **[root@xoonips-server ~]# cp -R html/modules/altsys /var/www/html/modules** | ← Copy the expanded files. |
| **[root@xoonips-server ~]# cp html/preload /* vaw/www/html/preload/** | ← Copy the expanded files. |

Perform installation from the &quot;Module Installation&quot; at &quot;Legacy System&quot; on the Administration menu (same as XooNIps and item type module).

#### 6.5.2.�Install D3forum {#6-5-2-install-d3forum}

How to install d3 modules, which is required for using comment functions .:

It is necessary to have completed installing an altsys module in advance.

Download the most updated module from the website.

| **[root@xoonips-server ~]# tar -xzvf d3forum-0.8.tar.gz** | ← Expand the obtained files. |
| --- | --- |
| **[root@xoonips-server ~]# cp -R xoops_trust_path/modules /var/www/xoops_trust_path** | ← Copy the expanded files. |
| **[root@xoonips-server ~]# cp -R html/modules/d3forum /var/www/html/modules** | ← Copy the expanded files. |
| **[root@xoonips-server ~]# cp html/class/smarty/plugins/* var/www/html/class/smarty/plugins/** | ← Copy the expanded files. |

Perform installation from &quot;Module Installation&quot; at &quot;Legacy System&quot; on the Administration menu (same as XooNIps and item type module).

| ![Prev](../../assets/etc\prev.gif)� | � | �![Next](../../assets/etc\next.gif) |
| --- | --- | --- |
| � | ![Home](../../assets/etc\home.gif)  | � |

Last updated: 2011/07/12