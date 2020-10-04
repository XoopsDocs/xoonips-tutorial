# 6.5. Support modules

Supporting modules are, for example, alternative modules for the system modules whose standard status can not satisfy by itself, and protector modules against malicious attacks.

For using the function to comment, install an altsys module and a D3forum module.

The following briefly shows how to install an altsys module and a D3forum module, which are required for utilizing the comment functions on XooNIps.

For detailed information, check the website [http://xoops.peak.ne.jp/](http://xoops.peak.ne.jp/)

## 6.5.1. Install an altsys module <a id="6-5-1-install-an-altsys-module"></a>

How to install an altsys module, an alternative module for standard system modules:

Modify mainfile.php

| **\[xoonips-server ~\]\# vi /var/www/html/mainfile.php** | ← mainfile.php file edition. |
| :--- | :--- |
| **define\('XOOPS\_TRUST\_PATH',''\);** |  |
| **define\('XOOPS\_TRUST\_PATH','/var/www/xoops\_trust\_path'\);** | ← |

Set up for XOOPS\_TRUST\_PATH

Download the most updated module from the website.

| **\[root@xoonips-server ~\]\# tar -xzvf altsys-0.6.tar.gz** | ← Expand the obtained files. |
| :--- | :--- |
| **\[root@xoonips-server ~\]\# cp -R xoops\_trust\_path /var/www/** | ← Copy the expanded files. |
| **\[root@xoonips-server ~\]\# cp -R html/modules/altsys /var/www/html/modules** | ← Copy the expanded files. |
| **\[root@xoonips-server ~\]\# cp html/preload /\* vaw/www/html/preload/** | ← Copy the expanded files. |

Perform installation from the "Module Installation" at "Legacy System" on the Administration menu \(same as XooNIps and item type module\).

## 6.5.2. Install D3forum <a id="6-5-2-install-d3forum"></a>

How to install d3 modules, which is required for using comment functions .:

It is necessary to have completed installing an altsys module in advance.

Download the most updated module from the website.

| **\[root@xoonips-server ~\]\# tar -xzvf d3forum-0.8.tar.gz** | ← Expand the obtained files. |
| :--- | :--- |
| **\[root@xoonips-server ~\]\# cp -R xoops\_trust\_path/modules /var/www/xoops\_trust\_path** | ← Copy the expanded files. |
| **\[root@xoonips-server ~\]\# cp -R html/modules/d3forum /var/www/html/modules** | ← Copy the expanded files. |
| **\[root@xoonips-server ~\]\# cp html/class/smarty/plugins/\* var/www/html/class/smarty/plugins/** | ← Copy the expanded files. |

Perform installation from "Module Installation" at "Legacy System" on the Administration menu \(same as XooNIps and item type module\).

