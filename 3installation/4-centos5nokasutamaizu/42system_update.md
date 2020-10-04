# 4.2. システムのアップデート

 以下のコマンドでユーザadminでログインします。

| `xoonips-server login:` **admin** | ← ログインユーザ名としてadminと入力 |
| :--- | :--- |
| `Password:` | ← adminのパスワードを入力\(表示はされない\) |
| `[admin@xoonips-server ~]$` | ← adminでログインした状態 |

以下のコマンドでrootユーザになり、システムのアップデートを実行します。

| `[admin@xoonips-server ~]$` **su -** | ← suコマンドでrootになる |
| :--- | :--- |
| `Password:` | ← rootのパスワードを入力 |
| `[root@xoonips-server ~]#` | ← rootになった状態 |

以後、指定があるまでroot権限のまま作業を行います。

| `[root@xooinps-server ~]#` **yum -y update** | ← システムのアップデートコマンドを実行 |
| :--- | :--- |


ネットワークの状態やコンピュータの性能によっては実行に時間がかかります。

システムが最新の状態に更新されます。

