# 1.7. 'Item Comment' \(XooNIps&gt;&gt;Site Policies&gt;&gt;Item Information&gt;&gt;Item Comment\)

Comment settings for the item. This function depends on d3forum module.

It has to be installed d3forum module and create forum before setting these options.

* "Directory setting"

  Set the directory name of d3forum used by comment function.

* "Forum ID setting"

  Set the forum ID made with d3forum.

![&quot;Item Comment&quot;](../../../.gitbook/assets/xoonips-policy9.png)

**Figure 4.9. "Item Comment"**

Other settings:

Modify the last line of "xoonips\_detail.html" by using the template editing function of altsys module.

Delete &lt;_{3 letters and the last 3 letters}_&gt; at the beginning.

![Item Comment \(Setting 2\)](../../../.gitbook/assets/xoonips-policy10.png)

**Figure 4.10. Item Comment \(Setting 2\)**

![Item Comment \(Setting - 3\)](../../../.gitbook/assets/xoonips-policy11.png)

**Figure 4.11. Item Comment \(Setting - 3\)**

Enter the line below at the "Format for comment-integration" field \(Item comment&gt;&gt;Forum Manager\).

**{XOOPS\_URL}/modules/xoonips/detail.php?item\_id=%s**

![Item Comment \(Setting - 4\)](../../../.gitbook/assets/xoonips-policy12.png)

**Figure 4.12. Item Comment \(Setting - 4\)**

Now, comments can be added to an item on its "Detail" screen.

