# XooNIps 3.43

このドキュメントは XooNIps 3.43 のリリース以降に見つかった既知の不具合および修正方法に関する一覧を掲載しています．

### 既知の問題および修正方法

#### ユーザ定義のIDを用いたファイルのダウンロードの際 404 エラーが表示される \(2009/9/25\)

ユーザが定義したアイテムIDを用いてファイルをダウンロードする際，正常にダウンロードできず "404 Not Found" エラーが表示されます．正しく動作させるには以下のように修正します．

```text
--- xoonips/class/xoonips_file.class.php.orig	31 Jul 2009 08:11:31 -0000	1.1.4.2
+++ xoonips/class/xoonips_file.class.php	25 Sep 2009 12:58:37 -0000	1.1.4.3
@@ -106,7 +106,7 @@
     $mimetypes = explode( ',', XNP_CONFIG_DOWNLOAD_FILE_TYPE_LIMIT );
     $mimetypes = array_map( array( &$GLOBALS['xoopsDB'], 'quoteString' ), $mimetypes );
     $criteria->add( new Criteria( 'mime_type', '('.implode( ',', $mimetypes ).')', 'IN' ) );
-    $criteria->add( new Criteria( 'doi', $doi, 'ib' ) );
+    $criteria->add( new Criteria( 'doi', $doi, '=', 'ib' ) );
     $xf_objs =& $xf_handler->getObjects( $criteria, false, 'file_id', false, $join );
     if ( count( $xf_objs ) == 0 ) {
       return false;
```

#### アイテム編集時に関連アイテムが消えてしまう \(2009/9/28\)

アイテムを編集する際，既存の関連アイテムが「関連を残す」のチェックボックスの状態に関わらず消えてしまう不具合があります．正しく動作させるには以下のように修正します．

```text
--- xoonips/include/lib.php     29 Jul 2009 12:05:22 -0000      1.147.2.1.2.73
+++ xoonips/include/lib.php     25 Sep 2009 17:58:46 -0000      1.147.2.1.2.74
@@ -4094,6 +4094,16 @@
   }
 
   /**
+   * get related to check item ids
+   *
+   * @access public
+   * @param array
+   */
+  function getRelatedToCheck() {
+    return $this->_related_to_check_ids;
+  }
+
+  /**
    * set related to check (for edit)
    *
    * @access public
@@ -4587,7 +4597,7 @@
       return false;
     }
     // related to
-    $related_to_ids = $itemlib_obj->getRelatedTo();
+    $related_to_ids = array_unique( array_merge( $itemlib_obj->getRelatedTo(), $itemlib_obj->getRelatedToCheck() ) );
     if ( ! $this->_related_to_handler->insertChildItemIds( $item_id, $related_to_ids ) ) {
       $transaction->rollback();
       return false;
```

