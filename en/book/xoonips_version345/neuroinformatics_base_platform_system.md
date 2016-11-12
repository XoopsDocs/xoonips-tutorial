## Neuroinformatics Base Platform System {#neuroinformatics-base-platform-system}

Jul 12, 2011

![](../../assets/xoonips_slogo.png)

Copyright � 2011 Neuroinformatics Japn Center, RIKEN BSI.

**Table of Contents**

*   1\. Overview
*   *   1\. What is XooNIps ？
    *   2\. Main features
    *   *   2.1\. Flexible database construction
        *   2.2\. Data classification
        *   2.3\. Quality-maintenance workflow
        *   2.4\. Metadata distribution
        *   2.5\. Variety of accessory functions
*   2\. Start guide
*   *   1\. User&#039;s authority
    *   2\. Navigator
*   3\. Installation of XooNIps
*   *   1\. Plan and design a website
    *   *   1.1\. Describe specific purposes of the website.
        *   1.2\. Decide functions of the website
        *   1.3\. Select software and hardware
        *   1.4\. Make a specification document
    *   2\. Server structure components
    *   3\. OS installation
    *   *   3.1\. Obtain CentOS5
        *   3.2\. Procedure of installation
    *   4\. Customize CentOS5
    *   *   4.1\. Create an administration account.
        *   4.2\. System Update
        *   4.3\. Installing the required packages
        *   4.4\. Install external programs
        *   4.5\. Set up iptables
        *   4.6\. Make SELinux invalid
        *   4.7\. Set up for Apache
        *   4.8\. Setup for MySQL
        *   4.9\. Set up for PHP
    *   5\. Install XOOPS
    *   *   5.1\. Set up for XOOPS
        *   5.2\. Close the XOOPS installation.
    *   6\. Install XooNIps
    *   *   6.1\. Set up for XooNIps
        *   6.2\. Initial setting and confirmation on XooNIps
        *   6.3\. How to install item type modules:
        *   6.4\. Precautions on updating XooNIps
        *   6.5\. Support modules
*   4\. Site policy and maintenance
*   *   1\. &quot;Site Policies&quot;
    *   *   1.1\. &quot;Site Policies&quot; (XooNIps &gt;&gt; Site Policies)
        *   1.2\. &quot;User information&quot; (XooNIps&gt;&gt;Site Policies&gt;&gt;User Information)
        *   1.3\. &quot;Group information&quot; (XooNIps&gt;&gt;Site Policies&gt;&gt;Group Information)
        *   1.4\. &quot;Item Information&quot; (XooNIps&gt;&gt;Site Policies&gt;&gt;Item Information)
        *   1.5\. &quot;Item Types&quot; (XooNIps&gt;Site Policies&gt;Item Information&gt;Item Types)
        *   1.6\. &quot;Import/Export&quot; (XooNIps&gt;&gt;Site Policies&gt;&gt;Item Information&gt;&gt;Import/Export)
        *   1.7\. &quot;Item Comment&quot; (XooNIps&gt;&gt;Site Policies&gt;&gt;Item Information&gt;&gt;Item Comment)
        *   1.8\. &quot;Moderators Privileges&quot; (XooNIps&gt;&gt;Site Policies&gt;&gt;Moderators Privileges)
        *   1.9\. &quot;Positions&quot; (XooNIps&gt;&gt;Site Policies&gt;&gt;Positions)
        *   1.10\. &quot;Rankings&quot; (XooNIps&gt;&gt;Site Policies&gt;&gt;Rankings)
    *   2\. &quot;Maintenance&quot;
    *   *   2.1\. &quot;Maintenance&quot; (XooNIps&gt;&gt;Maintenance)
        *   2.2\. &quot;User Management&quot; (XooNIps&gt;&gt;Maintenance&gt;&gt;User Management)
        *   2.3\. &quot;Item Management&quot; (Maintenance&gt;&gt;Item Management)
        *   2.4\. &quot;User List&quot; (XooNIps&gt;&gt;Maintenance&gt;&gt;User List)
        *   2.5\. &quot;Access Rankings&quot; (XooNIps&gt;&gt;Maintenance&gt;&gt;Access Rankings)
        *   2.6\. &quot;File Search&quot; (XooNIps&gt;&gt;Maintenance&gt;&gt;File Search)
        *   2.7\. &quot;OAI-PMH&quot; (XooNIps&gt;&gt;Maintenance&gt;&gt;OAI-PMH)
*   5\. How to operate a XooNIps database website
*   *   1\. Guest
    *   *   1.1\. How to search and browse the published items (information):
        *   1.2\. Advanced search
        *   1.3\. XooNIps Ranking
        *   1.4\. Admission/registration
    *   2\. Registered user
    *   *   2.1\. Login
        *   2.2\. Logout
        *   2.3\. Edit private (index) trees
        *   2.4\. Item management
        *   2.5\. Item publication
        *   2.6\. Group
        *   2.7\. Item transfer
    *   3\. Group administrator
    *   *   3.1\. Manage group members:
        *   3.2\. Review and certify shared items
        *   3.3\. Withdraw shared items in a group index
        *   3.4\. Edit group indexes
        *   3.5\. Publish a group index
        *   3.6\. Transfer a group administrator&#039;s authority
        *   3.7\. Change the disk capacity
        *   3.8\. Cancel a group
    *   4\. Moderator
    *   *   4.1\. Edit Public Index Trees
        *   4.2\. Certify users
        *   4.3\. Review and certify items
        *   4.4\. Withdraw items in public area
        *   4.5\. Create/delete a group
        *   4.6\. Access log analysis
        *   4.7\. Transfer the moderator&#039;s authority
    *   5\. System administrator
    *   *   5.1\. Change the site policy
        *   5.2\. Switch User Accounts
        *   5.3\. Export
        *   5.4\. Import
        *   5.5\. Harvest metadata
        *   5.6\. Change the moderator
*   6\. Copyright notice
*   A.
*   *   1\. Organizations
    *   2\. XooNIps based Online Databases

| � | � | �![Next](../../assets/etc\next.gif) |
| --- | --- | --- |

Last updated: 2011/07/12