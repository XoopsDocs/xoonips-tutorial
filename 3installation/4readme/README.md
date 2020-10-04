# 5. XOOPS Cubeのインストール

XooNIpsを利用するための基盤となるXOOPS Cubeのインストールを行います。

| XOOPS Cube公式サイトから最新版をダウンロードしてください\(執筆時のバージョンは2.1.7\) |  |
| :--- | :--- |
| `[root@xoonips-server ~]#` **wget http://downloads.sourceforge.net/xoopscube/Package\_Legacy\_2\_1\_7.zip** |  |
| `[root@xoonips-server ~]#` **unzip Package\_Legacy\_2\_1\_7.zip** | ← ダウンロードファイルを展開する |
| 展開ファイルをWebサーバドキュメントルートにコピー |  |
| `[root@xoonips-server ~]#` **cp -R Package\_Legacy/html/ /var/www/** |  |
| `[root@xoonips-server ~]#` **rm -rf Package\_Legacy** | ← 展開ディレクトリを削除 |
| `[root@xoonips-server ~]#` **rm -f Package\_Legacy\_2\_1\_7.zip** | ← ダウンロードファイルを削除 |
| `[root@xoonips-server ~]#` **chmod 777 /var/www/html/uploads** | ← パーミッションを変更 |
| `[root@xoonips-server ~]#` **chmod 777 /var/www/html/cache** | ← パーミッションを変更 |
| `[root@xoonips-server ~]#` **chmod 777 /var/www/html/templates\_c** | ← パーミッションを変更 |
| `[root@xoonips-server ~]#` **chmod 666 /var/www/html/mainfile.php** | ← パーミッションを変更 |

#### Warning

最新版のダウンロードURLは公式サイトで確認してください。

[ダウンロードページ\(Legacy2.1.7\)](http://downloads.sourceforge.net/xoopscube/Package_Legacy_2_1_7.zip)

