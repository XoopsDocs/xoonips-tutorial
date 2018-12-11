## 5. XOOPS Cubeのインストール {#5-xoops-cube}

XooNIpsを利用するための基盤となるXOOPS Cubeのインストールを行います。

| XOOPS Cube公式サイトから最新版をダウンロードしてください(執筆時のバージョンは2.1.7) |
| --- |
| `[root@xoonips-server ~]#` **wget http://downloads.sourceforge.net/xoopscube/Package_Legacy_2_1_7.zip** |
| `[root@xoonips-server ~]#` **unzip Package_Legacy_2_1_7.zip** | ← ダウンロードファイルを展開する |
| 展開ファイルをWebサーバドキュメントルートにコピー |
| `[root@xoonips-server ~]#` **cp -R Package_Legacy/html/ /var/www/** |
| `[root@xoonips-server ~]#` **rm -rf Package_Legacy** | ← 展開ディレクトリを削除 |
| `[root@xoonips-server ~]#` **rm -f Package_Legacy_2_1_7.zip** | ← ダウンロードファイルを削除 |
| `[root@xoonips-server ~]#` **chmod 777 /var/www/html/uploads** | ← パーミッションを変更 |
| `[root@xoonips-server ~]#` **chmod 777 /var/www/html/cache** | ← パーミッションを変更 |
| `[root@xoonips-server ~]#` **chmod 777 /var/www/html/templates_c** | ← パーミッションを変更 |
| `[root@xoonips-server ~]#` **chmod 666 /var/www/html/mainfile.php** | ← パーミッションを変更 |