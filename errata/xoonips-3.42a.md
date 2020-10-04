# XooNIps 3.42a

このドキュメントは XooNIps 3.42a のリリース以降に見つかった既知の不具合および修正方法に関する一覧を掲載しています．

### 既知の問題および修正方法

#### d3forum によるコメント機能利用時のテンプレート変数の誤り \(2009/2/12\)

d3forum モジュールによるコメント機能を利用する際，テンプレート "xoonips\_detail.html" を編集しコメントアウトされている箇所を有効にしますが，この時コメントのタイトルに割り当てられた変数に誤りがあります．正しく動作させるには以下のように修正します．

```text
<{d3forum_comment dirname=$dir_name forum_id=$forum_id itemname=item_id subject=$xoops_pagetitle}>
```

#### インポートしたアイテムの Preview のサムネイル作成に失敗する \(2009/3/6\)

アイテムをインポートする際にそのアイテムが Preview を持つ場合，サムネイル画像の作成に失敗する不具合があります．正しく動作させるためには "class/orm/file.class.php" を以下のように修正します．

```text
--- class/orm/file.class.php    9 Dec 2008 04:09:31 -0000       1.1.4.1.2.16
+++ class/orm/file.class.php    6 Mar 2009 06:09:53 -0000       1.1.4.1.2.17
@@ -329,7 +329,7 @@
       $new_width = round( $width * $scale );
       $new_height = round( $height * $scale );
       // resize
-      $new_Image_id = imagecreatetruecolor( $new_width, $new_height );
+      $new_image_id = imagecreatetruecolor( $new_width, $new_height );
       $result = imagecopyresized( $new_image_id, $image_id, 0, 0, 0, 0, $new_width, $new_height, $width, $height );
       imagedestroy( $image_id );
       $image_id = $new_image_id;
```

#### "Paper" アイテムが編集できない \(2009/3/25\)

Paper アイテムでアイテムを編集できない場合があります．正しく動作させるためには "xnppaper/include/view.php" を以下のように修正します．

```text
--- xnppaper/include/view.php   21 Jan 2009 02:59:37 -0000      1.50.2.1.2.29
+++ xnppaper/include/view.php   25 Mar 2009 17:44:46 -0000      1.50.2.1.2.30
@@ -274,6 +274,7 @@
 function xnppaperGetEditBlock( $item_id ) {
   global $xoopsDB;
   $formdata =& xoonips_getutility( 'formdata' );
+  $textutil =& xoonips_getutility( 'text' );
 
   // retrieve blocks of BasicInformation / index
   $basic = xnpGetBasicInformationEditBlock( $item_id );
```

#### アカウント情報ページ "userinfo.php" でユーザ情報のボタンが動作しない \(2009/3/30\)

アカウント情報ページ "userinfo.php" で自身の情報を表示させるもしくは管理者で他人の情報を表示させた際，ユーザ情報のボタンが正常に動作しない不具合があります．（han さんからの報告：[参照](http://xoonips.sourceforge.jp/modules/forum/index.php?post_id=285)）．正しく動作させるには以下のように修正します．

```text
--- userinfo.php.orig
+++ userinfo.php
@@ -86,6 +86,7 @@
 $textutil =& xoonips_getutility( 'text' );
 
 // assign basic user information
+$xoopsTpl->assign( 'user_uid', $thisUser->getVar( 'uid', 's' ) );
 $xoopsTpl->assign( 'lang_basicInfo', _US_BASICINFO );
 $xoopsTpl->assign( 'lang_allaboutuser', sprintf( _US_ALLABOUT, $thisUser->getVar( 'uname', 's' ) ) );
 $xoopsTpl->assign( 'lang_avatar', _US_AVATAR );
```

#### アイテム編集で日付の箇所が1970になってしまう \(2009/4/9\)

Paper などいくつかのアイテムタイプにおいて，アイテムを編集しようとすると日付の箇所が 1970 になってしまう不具合があります．正しく動作させるためには include/lib.php を以下のように修正します．

```text
--- lib.php.orig	2009-01-21 11:59:38.000000000 +0900
+++ lib.php	2009-06-25 14:46:47.351216000 +0900
@@ -4280,8 +4280,11 @@
     }
     // publication date (year, month, mday)
     $tpl = new XoopsTpl();
-    $gmtime = xnpISO8601( $basic['publication_year'], $basic['publication_month'], $basic['publication_mday'] );
-    $tpl->assign( 'gmtime', $gmtime != '0000' ? $gmtime : '' );
+    $pubyear = isset( $basic['publication_year'] ) ? intval( $basic['publication_year'] ) : 0;
+    $pubmonth = isset( $basic['publication_month'] ) ? intval( $basic['publication_month'] ) : 0;
+    $pubmday = isset( $basic['publication_mday'] ) ? intval( $basic['publication_mday'] ) : 0;
+    $gmtime = $pubyear == 0 ? '' : sprintf( '%04d-%02d-%02d', $pubyear, $pubmonth, $pubmday );
+    $tpl->assign( 'gmtime', $gmtime );
     $publcation_date = $tpl->fetch( "db:xoonips_publication_date.html" );
     $publication_year = $tpl->fetch( "db:xoonips_publication_year.html" );
     $publication_month = $tpl->fetch( "db:xoonips_publication_month.html" );
```

#### UTF-8 で動作させている際にファイル検索がうまく動作しない \(2009/4/15\)

XooNIps を UTF-8 文字コードで動作させる際，アイテムに添付されたファイルの中身の検索インデックスの作成に問題があり，3文字以上の文字列がうまく検索できない不具合があります．修正箇所が広範囲に渡りますので正常に動作させるためには次のリリース版をお待ち下さい．

#### アカウント情報ページ "userinfo.php" の検索結果のリンク切れ \(2009/6/12\)

アカウント情報ページ "/modules/xoonips/userinfo.php" において各モジュールの投稿記録等の検索結果が表示される箇所がありますが，このリンクが正常に機能しない不具合があります（ktym9814 さんからの報告：[参照](http://xoonips.sourceforge.jp/modules/forum/index.php?post_id=295)）．正しく動作させるには以下のように修正します．

```text
--- userinfo.php.org
+++ userinfo.php
@@ -218,16 +218,16 @@
       $modname = $module->getVar( 'name', 's' );
       for ( $i = 0; $i < $count; $i++ ) {
         if ( isset( $results[$i]['image'] ) && $results[$i]['image'] != '' ) {
-          $results[$i]['image'] = 'modules/'.$dirname.'/'.$results[$i]['image'];
+          $results[$i]['image'] = '../'.$dirname.'/'.$results[$i]['image'];
         } else {
-          $results[$i]['image'] = 'images/icons/posticon2.gif';
+          $results[$i]['image'] = '../../images/icons/posticon2.gif';
         }
-        $results[$i]['link'] = 'modules/'.$dirname.'/'.$results[$i]['link'];
+        $results[$i]['link'] = '../'.$dirname.'/'.$results[$i]['link'];
         $results[$i]['title'] = $myts->makeTboxData4Show( $results[$i]['title'] );
         $results[$i]['time'] = $results[$i]['time'] ? formatTimestamp( $results[$i]['time'] ) : '';
       }
       if ( $count == 5 ) {
-        $showall_link = '<a href="search.php?action=showallbyuser&mid='.$mid.'&uid='.$thisUser->getVar('uid').'">'._US_SHOWALL.'';
+        $showall_link = '<a href="../../search.php?action=showallbyuser&mid='.$mid.'&uid='.$thisUser->getVar('uid').'">'._US_SHOWALL.'';
       } else {
         $showall_link = '';
       }
```

#### アイテム編集時に公開承認状態および OAI-PMH の変更日時が更新されない \(2009/7/13\)

アイテムを修正した際，モデレータによる公開承認のモードの際に再承認が必要かどうかのチェックが正しく行われていない不具合，および，OAI-PMH でハーベストされた際の最終変更日時が更新されていない不具合があります．正しく動作させるには以下のように修正します．

```text
--- lib.php.orig        2009-01-21 11:59:38.000000000 +0900
+++ lib.php     2009-07-09 17:22:26.949147000 +0900
@@ -5156,6 +5156,7 @@
   function insertBasicInformation( $itemlib_obj ) {
     $item_basic_obj =& $itemlib_obj->getItemBasicObject();
     $is_new = ( $item_basic_obj->get( 'item_id' ) == 0 );
+    $certify_required_onupdate = $is_new ? false : $itemlib_obj->isCertifyRequired();
     $itemlib_obj->truncateObject();
     // transaction
     $transaction =& XooNIpsTransaction::getInstance();
@@ -5186,6 +5187,23 @@
       return false;
     }
 
+    // update certify state on update
+    if ( $certify_required_onupdate ) {
+      $xconfig_handler =& xoonips_getormhandler( 'xoonips', 'config' );
+      $certify_item = $xconfig_handler->getValue( 'certify_item' );
+      $certify_state = $certify_item == 'auto' ? CERTIFIED : CERTIFY_REQUIRED;
+      $index_item_link_handler =& xoonips_getormhandler( 'xoonips', 'index_item_link' );        
+      $index_item_link_objs =& $index_item_link_handler->getByItemId( $item_id, array( OL_PUBLIC, OL_GROUP_ONLY ) );
+      foreach ( $index_item_link_objs as $index_item_link_obj ) {
+        $index_item_link_obj->set( 'certify_state', $certify_state );
+        $index_item_link_handler->insert( $index_item_link_obj );
+      }
+    }
+
+    // update item status
+    $item_status_handler =& xoonips_getormhandler( 'xoonips', 'item_status' );
+    $item_status_handler->updateItemStatus( $item_id );
+
     // success
     $transaction->commit();
 
@@ -5198,10 +5216,8 @@
     } else {
       // record event log (update item)
       $eventlog_handler->recordUpdateItemEvent( $item_id );
-      if ( $itemlib_obj->isCertifyRequired() ) {
-        // notification
-        xoonips_insert_event_and_send_notification_of_certification( $item_id );
-      }
+      // notification
+      xoonips_insert_event_and_send_notification_of_certification( $item_id );
     }
     return true;
   }
```

