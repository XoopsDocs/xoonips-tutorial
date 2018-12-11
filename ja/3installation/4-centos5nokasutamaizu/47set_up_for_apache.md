# 4.7. Apacheの設定

 Webサーバ\(Apache\)の設定をします。

## 4.7.1. **設定ファイルの編集** <a id="4-7-1-config-file-editing"></a>

| `[root@xoonips-server ~]#` **vi /etc/httpd/conf/httpd.conf** | ← 設定ファイルの編集 |
| :--- | :--- |
| **AddDefaultCharset UTF-8** |  |
| ↓ |  |
| **\#AddDefaultCharset UTF-8** | ← コメントにする |

## 4.7.2. **Webサーバの起動と自動起動設定** <a id="4-7-2-automatic-startup-for-web-server"></a>

Set up for making the web server automatically started when the computer is restarted.

| **\[root@xoonips-server ~\]\# /etc/init.d/httpd start** | ← Startup web server. |
| :--- | :--- |
| **\[root@xoonips-server ~\]\# chkconfig httpd on** | ← Set up for automatic startup for web server. |

## 4.7.3. Check the performance of the web server. <a id="4-7-3-check-the-performance-of-the-web-server"></a>

他のコンピュータでブラウザを起動し、アドレスを入力します。

例えばhttp://\(OSインストールの時に決めたホスト名\)/と入力します。

以下のような画面がブラウザに表示されていればWebサーバの設定は完了です。

![](../../../.gitbook/assets/check01%20%281%29.png)

