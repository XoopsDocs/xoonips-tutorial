# 4.6. Make SELinux invalid

SELinux has to be invalid to operate XOOPS.

| **\[root@xoonips-server ~\]\# getenforce** | ← SElinux status check. |
| :--- | :--- |
| **Enforcing** | ← SELinux is valid. |
| **\[root@xoonips-server ~\]\# setenforce 0** | ← SELinux is invalid. |
| **\[root@xoonips-server ~\]\# getenforce** | ← SELinux status check. |
| **Permissive** | ← SELinux is invalid. |
| **\[root@xoonips-server ~\]\# vi /etc/sysconfig/selinux** | ← SELinux config file editing. |
| **SELINUX=enforcing** |  |
| ↓ |  |
| **SELINUX=disabled** | ← On system startup, make SELinux invalid |

