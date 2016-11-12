### 4.4.�Install external programs {#4-4-install-external-programs}

Install the external programs required to make XooNIps operable.

| Obtain the external support programs. |
| --- |
| **[root@xoonips-server ~]# wget http://prdownloads.sf.net/chicago/xlhtml-0.5.tgz** |
| **[root@xoonips-server ~]# tar -xzvf xlhtml-0.5.tgz** | ← Expand the obtained files. |
| **[root@xoonips-server ~]# cd xlhtml-0.5** |
| **[root@xoonips-server ~]# cp /usr/share/automake-1.9/depcomp ./** | ← Copy the commands required for installing. |
| **[root@xoonips-server ~]# ./configure** | ← Execute the configuration. |
| **[root@xoonips-server ~]# make** | ← Execute the make. |
| **[root@xoonips-server ~]# make install** | ← Execute the installation. |
| **[root@xoonips-server ~]# cd** | ← Escape from the expand directory. |

| Obtain the external support programs. |
| --- |
| **[root@xoonips-server ~]# wget http://downloads.sourceforge.net/wvware/wv-1.2.4.tar.gz** |
| **[root@xoonips-server ~]# tar -xzvf wv-1.2.4.tar.gz** | ← Expand the obtained files. |
| **[root@xoonips-server ~]# cd wv-1.2.4** |
| **[root@xoonips-server ~]# ./configure** | ← Execute the configuration. |
| **[root@xoonips-server ~]# make** | ← Execute the make. |
| **[root@xoonips-server ~]# make install** | ← Perform installation. |
| **[root@xoonips-server ~]# cd** | ← Escape from the expanded directory. |

| Create symbolic links to make the external programs operable to XooNIps. |
| --- |
| **[root@xoonips-server ~]# ln -s /usr/local/bin/xlhtml /usr/bin/xlhtml** |
| **[root@xoonips-server ~]# ln -s /usr/local/bin/ppthtml /usr/bin/ppthtml** |
| **[root@xoonips-server ~]# ln -s /usr/local/bin/wvText /usr/bin/wvText** |

| Close the installation of the external programs. |
| --- |
| **[root@xoonips-server ~]# rm -rf xlhtml-0.5** |
| **[root@xoonips-server ~]# rm -rf wv-1.2.4** |
| **[root@xoonips-server ~]# rm -f xlhtml-0.5.tgz** |
| **[root@xoonips-server ~]# rm -f wv-1.2.4.tar.gz** |