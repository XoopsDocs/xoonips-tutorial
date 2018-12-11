# 1. ユーザの権限

<table>
  <thead>
    <tr>
      <th style="text-align:left">ゲスト</th>
      <th style="text-align:left">
        <p>未登録のユーザです。ユーザアカウントが無い状態です。</p>
        <ul>
          <li>Public領域に登録されているアイテムの検索と閲覧が出来ます。</li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">登録ユーザ</td>
      <td style="text-align:left">
        <p>登録済みのユーザです。サイトにログインするためのIDとパスワードが与えられています。</p>
        <ul>
          <li>Publicの他にPrivate領域とグループに参加している場合Group領域に登録されているアイテムの検索や閲覧が出来ます。</li>
          <li>Private領域にアイテムを登録することが出来ます。</li>
          <li>Public領域やGroup領域にアイテムを登録することが出来ます。</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">グループ管理者</td>
      <td style="text-align:left">
        <p>グループの管理を行うことの出来るユーザ権限です。</p>
        <ul>
          <li>ユーザをグループに対して参加や退会の管理が出来ます。</li>
          <li>Group領域のIndexTreeの編集が出来ます。</li>
          <li>Group領域に登録するアイテムを査読してグループでの公開を承認したり却下することが出来ます。</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">*モデレータ(webmaster)</td>
      <td style="text-align:left">
        <p>登録アイテムの品質管理や登録ユーザの承認などが行えるユーザ権限です。</p>
        <ul>
          <li>新規ユーザ登録の承認が行えます。</li>
          <li>Public領域のIndexTreeの編集が出来ます。</li>
          <li>新しいGroupを作成することが出来ます。</li>
          <li>Public領域に登録するアイテムを査読して公開を承認したり却下することが出来ます。</li>
          <li>サイトのアクセスログを閲覧することが出来ます。</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">*システム管理者</td>
      <td style="text-align:left">
        <p>システム管理を行えるユーザ権限です。</p>
        <ul>
          <li>データベースサイトとしてのポリシー決定や設定が行えます。</li>
          <li>他のデータベースサイトからメタデータを収集してくることが出来ます。</li>
          <li>サイト上のアイテムをインポートしてデータを保管することが出来ます。</li>
          <li>インポートしたデータは他のサイトにエクスポートして移動させることが出来ます。</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table> \*XooNIps はXOOPSの一モジュールとして開発されています。モデレータやシステム管理者としての役割はXOOPSに関する基本的な知識が備わっていた方が理解しやすいと思います。このマニュアルではXOOPSの基本的な部分は解説していませんのでXOOPS Cube公式ページ\(`http://xoopscube.jp/`\)や関連書籍を参考にしてください。

