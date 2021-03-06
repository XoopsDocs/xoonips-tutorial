# 4.5. Set up iptables

Set up for packet filtering.

At the initial condition, the access to the web server is controlled. The following shows how to set up for access permission.

| **\[root@xoonips-server ~\]\# vi /etc/sysconfig/iptables** |  |
| :--- | :--- |
| Copy the line below. |  |
| **-A RH-Firewall-l-INPUT -m state --state NEW -m tcp -p tcp --dport 22 -j ACCEPT** |  |
| ↓ Change the "22" in the line to "80". |  |
| **-A RH-Firewall-l-INPUT -m state --state NEW -m tcp -p tcp --dport 80 -j ACCEPT** |  |
| **\[root@xoonips-server ~\]\# /etc/init.d/iptables restart** | ← Restart the packet filtering software. |

