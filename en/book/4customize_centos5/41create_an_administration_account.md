### 4.1.�Create an administration account. {#4-1-create-an-administration-account}

Log into the server as root by the following procedure.

| **xoonips-server login: root** | ← Enter &quot;root&quot; as a login user. |
| --- | --- |
| **Password:** | ← Enter root password（not shown） |
| **[root@xoonips-server ~]#** | ← (Logged in as root) |

Create an administration account by the following commands.

| **[root@xoonips-server ~]# useradd admin** | ← Create an admin account. |
| --- | --- |
| **[root@xoonips-server ~]# passwd admin** | ← Set an admin password. |
| **Changing password for user admin.** |
| **New UNIX password:** | ← Enter the admin password. |
| **Retype new UNIX password:** | ← Reenter the admin password. |
| **passwd: all authentication tokens updated successfully.** |

#### 4.1.1.�Setup for authorizing the admin user to execute su. {#4-1-1-setup-for-authorizing-the-admin-user-to-execute-su}

Under the root authority, which is unrestricted to execute any commands, it may cause critical operation errors such as deleting important files, etc. The following shows how to set it as it takes user admin for usual operations and the root authority by using su command for inevitable cases.

| **[root@xoonips-server ~]# usermod -G wheel admin** | ← Add user admin to wheel group |
| --- | --- |
| **[root@xoonips-server ~]# vi /etc/pam.d/su** | ← Edit file by vi editor |
| **#auth required pam_whell.so use_uid** |
| ↓ |
| **auth required pam_whell.so use_uid** | ← Delete comments |

Please refer to web or study guides for the usage of vi editor.

Log out now. Log in as a user admin for the following procedures.

| **[root@xoonips-server ~]# exit** | ← Log out |
| --- | --- |