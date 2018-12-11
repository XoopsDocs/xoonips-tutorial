# 1.7. コメント機能

コメント機能を利用するには外部モジュールのaltsys,d3forumモジュールのインストールが必須です。

d3forumモジュールであらかじめフォーラムを作成しておくことも必須です。

* ディレクトリ名の設定

  コメント機能で利用するd3forumのディレクトリ名を指定します。

* フォーラムIDの設定

  あらかじめコメント用にd3forumで作成したフォーラムID番号を指定します。

![&quot;Item Comment&quot;](../../../.gitbook/assets/xoonips-policy9%20%281%29.png)

**Figure 4.9.**  **コメント機能の設定**

その他に必要な設定として

altsysモジュールのテンプレート編集機能等を利用してxoonips\_detail.htmlの最終行を修正します。

先頭の&lt;{\* 3文字と最後の3文字 \*}&gt; を削除します。

![Item Comment \(Setting 2\)](../../../.gitbook/assets/xoonips-policy10%20%281%29.png)

**Figure 4.10.**  **コメント機能の設定2**

![Item Comment \(Setting - 3\)](../../../.gitbook/assets/xoonips-policy11.png)

**Figure 4.11.**  **コメント機能の設定3**

d3forumのフォーラム管理画面で「コメント統合時の参照方法」の欄に

**{XOOPS\_URL}/modules/xoonips/detail.php?item\_id=%s**と入力します。

![Item Comment \(Setting - 4\)](../../../.gitbook/assets/xoonips-policy12%20%281%29.png)

**Figure 4.12.**  **コメント機能の設定4**

 アイテムの詳細画面でアイテムに対してコメントを付けることが出来るようになります。

