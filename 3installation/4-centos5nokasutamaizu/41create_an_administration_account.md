# 4.1. 管理用アカウントの作成

 以下の手順でサーバにrootでログインします。.

| `xoonips-server login:` **root** | ← ログインユーザ名としてrootと入力 |
| :--- | :--- |
| `Password:` | ← rootのパスワードを入力（表示はされない） |
| `[root@xoonips-server ~]#` | ← rootでログインした状態 |

 管理用アカウントを以下のコマンドで作成します。

| `[root@xoonips-server ~]#` **useradd admin** | ← 管理用アカウントadminの作成 |
| :--- | :--- |
| `[root@xoonips-server ~]#` **passwd admin** | ← adminのパスワード設定 |
| `Changing password for user admin.` |  |
| `New UNIX password:` | ← adminのパスワード入力 |
| `Retype new UNIX password:` | ← adminのパスワード再入力 |
| `passwd: all authentication tokens updated successfully.` |  |

## 4.1.1. **adminユーザのみsuが実行出来るように設定する** <a id="4-1-1-setup-for-authorizing-the-admin-user-to-execute-su"></a>

 root権限は何でも出来てしまう誤操作で重要なファイルを削除してしまったりすることがあるので、普段の作業は必ずadminユーザで行い、必要な時にだけsuコマンドを使ってroot権限を使用するように設定します。

| `[root@xoonips-server ~]#` **usermod -G wheel admin** | ← ユーザadminをwheelグループに追加 |
| :--- | :--- |
| `[root@xoonips-server ~]#` **vi /etc/pam.d/su** | ← viエディタでファイルを編集する。 |
| **\#auth required pam\_whell.so use\_uid** |  |
| ↓ |  |
| **auth required pam\_whell.so use\_uid** | ← コメント削除 |

viエディタの使用法についてはWEBや書籍などを参照してください。

ログアウトして次回以降ユーザadminで作業を行います。

| `[root@xoonips-server ~]#` **exit** | ← ログアウト |
| :--- | :--- |


