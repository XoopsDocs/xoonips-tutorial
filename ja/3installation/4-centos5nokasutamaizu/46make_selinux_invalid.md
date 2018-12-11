# 4.6. SELinuxの無効化

XOOPSの利用にはSELinuxを無効にする必要があります。

| `[root@xoonips-server ~]#` **getenforce** | ← SElinux状態確認 |
| :--- | :--- |
| **Enforcing** | ← SELinux有効 |
| `[root@xoonips-server ~]#` **setenforce 0** | ← SELinux無効化 |
| `[root@xoonips-server ~]#` **getenforce** | ← SELinux状態確認 |
| **Permissive** | ← SELinux無効 |
| `[root@xoonips-server ~]#` **vi /etc/sysconfig/selinux** | ← SELinux設定ファイル編集 |
| **SELINUX=enforcing** |  |
| ↓ |  |
| **SELINUX=disabled** | ← システム起動時にSELinuxを無効化 |

