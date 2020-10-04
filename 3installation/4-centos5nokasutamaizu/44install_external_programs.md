# 4.4. 外部補助プログラムのインストール

XooNIpsを動作させる為に必要な外部プログラムをインストールします。

| 外部補助プログラムの取得 |  |
| :--- | :--- |
| `[root@xoonips-server ~]#` **wget http://prdownloads.sf.net/chicago/xlhtml-0.5.tgz** |  |
| `[root@xoonips-server ~]#` **tar -xzvf xlhtml-0.5.tgz** | ← 取得ファイルの展開 |
| `[root@xoonips-server ~]#` **cd xlhtml-0.5** |  |
| `[root@xoonips-server ~]#` **cp /usr/share/automake-1.9/depcomp ./** | ← 必要なファイルをコピー |
| `[root@xoonips-server ~]#` **./configure** | ← configureの実行 |
| `[root@xoonips-server ~]#` **make** | ← makeの実行 |
| `[root@xoonips-server ~]#` **make install** | ← インストールの実行 |
| `[root@xoonips-server ~]#` **cd** | ← 展開ディレクトリから抜ける |

| 外部補助プログラムの取得 |  |
| :--- | :--- |
| `[root@xoonips-server ~]#` **wget http://downloads.sourceforge.net/wvware/wv-1.2.4.tar.gz** |  |
| `[root@xoonips-server ~]#` **tar -xzvf wv-1.2.4.tar.gz** | ← 取得ファイルの展開 |
| `[root@xoonips-server ~]#` **cd wv-1.2.4** |  |
| `[root@xoonips-server ~]#` **./configure** | ← configureの実行 |
| `[root@xoonips-server ~]#` **make** | ← makeの実行 |
| `[root@xoonips-server ~]#` **make install** | ← インストールの実行 |
| `[root@xoonips-server ~]#` **cd** | ← 展開ディレクトリから抜ける |

| XooNIpsが外部補助プログラムを利用できるようにシンボリックリンクを作成します。 |
| :--- |
| `[root@xoonips-server ~]#` **ln -s /usr/local/bin/xlhtml /usr/bin/xlhtml** |
| `[root@xoonips-server ~]#` **ln -s /usr/local/bin/ppthtml /usr/bin/ppthtml** |
| `[root@xoonips-server ~]#` **ln -s /usr/local/bin/wvText /usr/bin/wvText** |

| 外部補助プログラムインストールの後始末をします |
| :--- |
| `[root@xoonips-server ~]#` **rm -rf xlhtml-0.5** |
| `[root@xoonips-server ~]#` **rm -rf wv-1.2.4** |
| `[root@xoonips-server ~]#` **rm -f xlhtml-0.5.tgz** |
| `[root@xoonips-server ~]#` **rm -f wv-1.2.4.tar.gz** |

