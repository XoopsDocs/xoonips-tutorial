# 6.2. XooNIpsの初期設定と確認

 XooNIpsを使用するための設定をします。

![](../../../.gitbook/assets/xoonips-install08%20%281%29.png)

 管理者メニューで\[XooNIps\]をクリックします。

![](../../../.gitbook/assets/xoonips-install09%20%281%29.png)

 \[システム設定\]をクリックします。

## 6.2.1. **ファイルアップロードディレクトリの変更** <a id="6-2-1-change-the-file-upload-directory"></a>

Webサーバの権限で書き込みが出来るディレクトリを指定する必要があります。

| `[root@xoonips-server ~]#` **mkdir /var/www/xoonipsupload** | ← ディレクトリを作成 |
| :--- | :--- |
| `[root@xoonips-server ~]#` **chmod a+w /var/www/xoonipsupload** | ← パーミッションを変更する。 |

|  |
| :--- |


![](../../../.gitbook/assets/xoonips-install10%20%281%29.png)

 \[基本設定\]をクリックします。

![](../../../.gitbook/assets/xoonips-install11%20%281%29.png)

\[ファイルアップロードディレクトリ\]の項目に**/var/www/xoonipsupload**と入力します。

更新ボタンをクリックして変更した設定を有効にします。

## 6.2.2. **インラインフレーム設定** <a id="6-2-2-setup-inline-frame"></a>

 ここではインデックスツリーの表示領域を変更することが出来ます。

![](../../../.gitbook/assets/xoonips-install12%20%281%29.png)

 \[インラインフレーム表示設定\]をクリックします。

![](../../../.gitbook/assets/xoonips-install13%20%281%29.png)

インデックスツリーの幅とインデックスツリーの高さを数値で入力して更新ボタンを押します。

インデックスツリーの幅を割合（％）で指定することによりブロック内での表示領域の割合を変更できます。

| Width indicated in 100%. | Width indicated in 50%. |
| :--- | :--- |
| ![](../../../.gitbook/assets/xoonips-install14%20%281%29.png) | ![](../../../.gitbook/assets/xoonips-install15.png) |

 インデックスツリーの高さをピクセルで指定することにより表示領域の大きさを変更できます。

| Height indicated in 400 pixels. | Height indicated in 200 pixels. |
| :--- | :--- |
| ![](../../../.gitbook/assets/xoonips-install16.png) | ![](../../../.gitbook/assets/xoonips-install17.png) |

## 6.2.3. **印刷設定** <a id="6-2-3-setup-print-formats"></a>

 ここではページを印刷する際にヘッダとして表示させる情報を入力することが出来ます。

![](../../../.gitbook/assets/xoonips-install18%20%281%29.png)

 \[印刷設定\]をクリックします。

![](../../../.gitbook/assets/xoonips-install19%20%281%29.png)

 入力した情報は詳細画面などを印刷の際ヘッダ情報として同時に印刷されます。

## 6.2.4. **RSS配信設定** <a id="6-2-4-set-up-for-rss-distribution"></a>

XooNIpsはRSS1.0\(RDF\)、RSS2.0、Atom1.0の３種類のフィード形式をサポートしています。

設定画面で表示されるURLを公開することでアイテムの更新情報及びグループの新規作成状況がアナウンス出来ます。

![](../../../.gitbook/assets/xoonips-install20%20%281%29.png)

 \[RSS設定\]をクリックします。

![](../../../.gitbook/assets/xoonips-install21.png)

 利用するフィード形式のテキストボックスの内容をコピーして公開してください。

## 6.2.5. **OAI-PMH設定** <a id="6-2-5-set-up-oai-pmh"></a>

XooNIpsはメタデータの情報を機械的に収集する仕組みとしてOAI-PMHを採用しています。

ここではOAI-PMHに対応した別のサーバにメタデータを提供するための設定（リポジトリ設定）とOAI-PMHに対応した別のサーバからメタデータを収集するための設定（ハーベスタ設定）の両方が行えます。.

![](../../../.gitbook/assets/xoonips-install22.png)

 \[OAI-PMH設定\]をクリックします。

![](../../../.gitbook/assets/xoonips-install23%20%281%29.png)

*  リポジトリ設定はメタデータを他のサーバに提供する為の設定です。

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p></p>
        <ul>
          <li>ハーベスタ設定はメタデータを他のサーバから収集するための設定です。</li>
        </ul>
        <p>メタデータを収集するサーバのURLを改行区切りで入力します。</p>
        <p>行の先頭に(セミコロン);を付けた場合はその行はコメントになります。</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>## 6.2.6. **プロキシ設定** <a id="6-2-6-proxy-configuration"></a>

 XooNIpsから他のサーバへアクセスする際プロキシを利用する場合に設定します。

![](../../../.gitbook/assets/xoonips-install24.png)

 \[プロキシ設定\]をクリックします。

![](../../../.gitbook/assets/xoonips-install25.png)



| ホスト名 | プロキシサーバのホスト名を設定します |
| :--- | :--- |


| ポート番号 | プロキシサーバのポート番号を設定します |
| :--- | :--- |


| ユーザ名 | ユーザ認証が必要な場合にユーザ名を設定します |
| :--- | :--- |


| パスワード | ユーザ認証のパスワードを設定します |
| :--- | :--- |


## 6.2.7. **イベント通知設定** <a id="6-2-7-setup-for-event-notification"></a>

 XOOPSが本来持っているイベント通知機能を利用してXooNIpsがユーザに対して伝えることの出来るイベントを指定します。

![](../../../.gitbook/assets/xoonips-install26.png)

\[イベント通知設定\]をクリックします。

イベント通知設定は以下の４つから選択します。

* この機能を無効にする
* イベント選択オプションをブロックに表示する
* イベント選択オプションをメインコンテンツ下部に表示する
* イベント選択オプションをブロックおよびメインコンテンツ下部の両方に表示する

特定イベントを有効にするの項目は複数の選択が可能です。

| 通知する相手 | 画面での表示 | 設定される内容 |
| :--- | :--- | :--- |
| XooNIps管理者 | 管理者：アイテム移譲通知 | アイテムが移譲されたことを通知します。 |
| 管理者：アカウント承認通知 | アカウントが承認されたことを通知します。 |  |
| 管理者：アイテム承認通知 | 公開アイテムが承認されたことを通知します。 |  |
| 管理者：グループアイテム承認要求通知 | グループ領域へのアイテム承認要求があることを通知します。 |  |
| ユーザ | XooNIpsユーザ：アイテム移譲通知 | アイテムが移譲されたことを通知します。 |
| XooNIpsユーザ：アイテム更新通知 | アイテムが更新されたことを通知します。 |  |
| XooNIpsユーザ：アイテム承認通知 | 公開アイテムが承認されたことを通知します。 |  |
| XooNIpsユーザ：アイテム承認拒否通知 | 公開アイテムの承認が拒否されたことを通知します。 |  |
| XooNIpsユーザ：ファイルのダウンロードを通知 | ファイルがダウンロードされたことを通知します。 |  |
| XooNIpsユーザ：グループアイテム承認通知 | グループ領域に登録したアイテムが承認されたことを通知します。 |  |
| XooNIpsユーザ：グループアイテム承認拒否通知 | グループ領域へのアイテム登録が拒否されたことを通知します。 |  |

## 6.2.8. **XOOPS拡張** <a id="6-2-8-xoops-extension"></a>

XOOPSのユーザーモジュールでユーザの登録を行った場合、そのユーザがXooNIpsの機能を使えるようにします。

XOOPSのユーザーモジュールでユーザの削除を行った場合、XooNIpsに残っているユーザ情報を削除します。

![](../../../.gitbook/assets/xoonips-install27.png)

 \[XOOPS拡張\]をクリックします。

![](../../../.gitbook/assets/xoonips-install28.png)

 操作欄にあるアイコンをクリックすることでユーザの追加や削除が行えます。

## 6.2.9. **動作確認** <a id="6-2-9-configuration-test"></a>

 XooNIpsの動作設定を確認します。

![](../../../.gitbook/assets/xoonips-install29.png)

 \[動作確認\]をクリックします。

![](../../../.gitbook/assets/xoonips-install30.png)

 \[テスト\]をクリックします。

![](../../../.gitbook/assets/xoonips-install31%20%281%29.png)

XooNIpsの設定情報が表示されます。

総合判定がOKになっていればXooNIps動作前の設定は終了です。

赤色で表示された場所がある場合には、画面のコメントに従って修正する必要があります。

