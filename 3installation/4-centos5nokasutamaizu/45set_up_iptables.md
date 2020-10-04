# 4.5. iptablesの設定

パケットフィルタリングの設定をします。

初期状態ではWebサーバへのアクセスが制限された状態になっているため、接続を許可する設定を行います。

| `[root@xoonips-server ~]#` **vi /etc/sysconfig/iptables** |
| :--- |
| 以下の行をコピーします。 |
| **-A RH-Firewall-l-INPUT -m state --state NEW -m tcp -p tcp --dport 22 -j ACCEPT** |
| ↓ コピーした行の22を80に変更する。 |
| **-A RH-Firewall-l-INPUT -m state --state NEW -m tcp -p tcp --dport 80 -j ACCEPT** |
| `[root@xoonips-server ~]#` **/etc/init.d/iptables restart** |

