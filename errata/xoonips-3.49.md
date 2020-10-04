# XooNIps 3.49

このドキュメントは XooNIps 3.49 のリリース以降に見つかった既知の不具合および修正方法に関する一覧を掲載しています．

### 既知の問題および修正方法

#### 添付ファイルを持つアイテムの削除に失敗する \(2020/8/25\)

添付ファイルを持つアイテムの削除に失敗します。正しく動作させるには以下のように修正します。

```text
--- xoonips/class/orm/file.class.php.orig
+++ xoonips/class/orm/file.class.php
@@ -175,7 +175,7 @@ class XooNIpsOrmFileHandler extends XooNIpsTableObjectHandler
      */
     public function delete(&$obj, $force = false)
     {
-        if (parent::delete($file)) {
+        if (parent::delete($obj)) {
             return true;
         }
```

#### 添付ファイルを持つアイテムの登録に失敗する \(2020/8/27\)

添付ファイルを持つアイテムの削除に失敗します。正しく動作させるには以下のように修正します。

```text
--- xoonips/include/lib.php.orig
+++ xoonips/include/lib.php
@@ -470,7 +470,7 @@ function xnpGetPreviewDetailBlock($item_id)
     $imageHtml2 = array();
     $fileIDs = array();
     foreach ($files as $files_) {
-        list($dummy, list($fileID, $caption)) = $files_;
+        list($fileID, $caption) = $files_;
         $thumbnailFileName = XOOPS_URL."/modules/xoonips/image.php?file_id=$fileID&amp;thumbnail=1";
         $imageFileName = XOOPS_URL."/modules/xoonips/image.php?file_id=$fileID";
         $htmlCaption = $textutil->html_special_chars($caption);
@@ -933,13 +933,12 @@ function xnpUploadFile($name, $keyval)
     $escOriginalFileName = $xoopsDB->quoteString($ar['original_file_name']);
     $escMimeType = $xoopsDB->quoteString($ar['mime_type']);
     $fileSize = (int) $file['size'];
-    $escKeys = array();
-    $escVals = array();
+    $escKeys = '';
+    $escVals = '';
     if (is_array($keyval) && 0 != count($keyval)) {
-        foreach ($keyval as $keyval_) {
-            list($key, $val) = $keyval_;
-            $escKeys[] = '`'.str_replace('`', '``', $key).'`';
-            $escVals[] = $xoopsDB->quoteString($val);
+        foreach ($keyval as $key => $val) {
+            $escKeys .= ', '.'`'.str_replace('`', '``', $key).'`';
+            $escVals .= ', '.$xoopsDB->quoteString($val);
         }
     }
     $error = (int) $file['error'];
@@ -953,8 +952,8 @@ function xnpUploadFile($name, $keyval)
         return array(false, $errorMessage);
     }
     $sql = 'INSERT INTO '.$xoopsDB->prefix('xoonips_file').
-        ' (`original_file_name`, `mime_type`, `file_size`, `sess_id`, `item_id`, `file_type_id`, '.implode(', ', $escKeys).')'.
-        ' VALUES ('.$escOriginalFileName.', '.$escMimeType.', '.$fileSize.', '.$esc_sess_id.', NULL, '.$fileTypeID.', '.implode(', ', $escVals).')';
+        ' (`original_file_name`, `mime_type`, `file_size`, `sess_id`, `item_id`, `file_type_id`'.$escKeys.')'.
+        ' VALUES ('.$escOriginalFileName.', '.$escMimeType.', '.$fileSize.', '.$esc_sess_id.', NULL, '.$fileTypeID.$escVals.')';
     $result = $xoopsDB->queryF($sql);
     if (false === $result) {
         xoonips_error_exit(500);
@@ -1076,7 +1075,7 @@ function xnpGetPreviewEditBlock($item_id)
     $ar = array();
     reset($files);
     foreach ($files as $files_) {
-        list($key, list($fileID, $caption)) = $files_;
+        list($fileID, $caption) = $files_;
         $ar[] = $fileID;
     }
     $previewFileID = implode(',', $ar);
@@ -1101,7 +1100,7 @@ function xnpGetPreviewEditBlock($item_id)
     $imageHtml3 = array();
     reset($files);
     foreach ($files as $files_) {
-        list($dummy, list($fileID, $caption)) = $files_;
+        list($fileID, $caption) = $files_;
         $thumbnailFileName = XOOPS_URL."/modules/xoonips/image.php?file_id=$fileID&amp;thumbnail=1";
         $imageFileName = XOOPS_URL."/modules/xoonips/image.php?file_id=$fileID";
         $htmlCaption = $textutil->html_special_chars($caption);
@@ -1148,7 +1147,7 @@ function xnpGetAttachmentEditBlock($item_id, $name)
            ' <input class="formButton" type="button" name="file_delete_button_'.$fileID.'" value="'._MD_XOONIPS_ITEM_DELETE_BUTTON_LABEL.'" onclick="xnpSubmitFileDelete(this.form, \''.$name.'\', '.$fileID.')" />';
     }
     $html = '<input type="hidden" name="'.$name.'FileID" value="'.$fileID.'" />'.
-        '<input type="file" name="'.$name.' size="50" /><br />'.
+        '<input type="file" name="'.$name.'" size="50" /><br />'.
         $fileInfoLine;
 
     return array('name' => _MD_XOONIPS_ITEM_ATTACHMENT_LABEL, 'value' => $html);
@@ -1428,7 +1427,7 @@ function xnpGetPreviewConfirmBlock($item_id)
         $imageHtml1 = array();
         $imageHtml2 = array();
         foreach ($files as $files_) {
-            list($dummy, list($fileID, $caption)) = $files_;
+            list($fileID, $caption) = $files_;
             $thumbnailFileName = XOOPS_URL."/modules/xoonips/image.php?file_id=$fileID&amp;thumbnail=1";
             $imageFileName = XOOPS_URL."/modules/xoonips/image.php?file_id=$fileID";
             $htmlCaption = $textutil->html_special_chars($caption);
@@ -1736,7 +1735,7 @@ function xnpUpdateAttachment($item_id, $name)
     }
 
     if (!empty($fileID)) {
-        $sql = 'UPDATE $table SET `sess_id`=NULL, `item_id`='.$item_id.' WHERE `sess_id`='.$esc_sess_id.' AND `file_id`='.$fileID.' AND `file_type_id`='.$file_type_id;
+        $sql = 'UPDATE '.$table.' SET `sess_id`=NULL, `item_id`='.$item_id.' WHERE `sess_id`='.$esc_sess_id.' AND `file_id`='.$fileID.' AND `file_type_id`='.$file_type_id;
         $result = $xoopsDB->queryF($sql);
         if (false === $result) {
             xoonips_error_exit(500);

```

#### OAI-PMH によるメタデータハーベスト時にエラーが出る \(2020/9/11\)

OAI-PMH によるメタデータハーベストのリクエスト（ListRecordsやListIdentifiersなど）の応答に失敗します。正しく動作させるには以下のように修正します。

```text
--- xoonips/xoonips/include/lib.php.orig
+++ xoonips/xoonips/include/lib.php
@@ -3715,7 +3715,7 @@ function xnpListIndexTree($mode = XOONIPS_LISTINDEX_MODE_ALL, $assoc_array_mode
     }
 
     $sql = 'SELECT tx.`index_id`, tx.parent_index_id, tx.uid, tx.gid, tx.open_level, tx.sort_number, ti.item_type_id, tt.title'.
-        ' FROM $item_title AS tt, '.$index.' AS `tx`'.
+        ' FROM '.$item_title.' AS tt, '.$index.' AS `tx`'.
         ' LEFT JOIN '.$item_basic.' AS `ti` ON `tx`.`index_id`=`ti`.`item_id`'.
         ' WHERE ('.$where_level.')'.
         ' AND `tt`.`title_id`='.DEFAULT_ORDER_TITLE_OFFSET.' AND `tt`.`item_id`=`ti`.`item_id`'.
```



