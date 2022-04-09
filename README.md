# Docker-wordpress
Docker で wordpress 環境を構築
<br><br><br>



## 使用法 （Usage）

1. このページの `Clone or download` ボタンよりリポジトリのクローンもしくはZIPダウンロード
2. ZIPダウンロードの場合は解凍
3. 解凍して出来たフォルダをDockerコマンドが有効な場所に置く
4. コマンドプロンプト（win）/ ターミナル（mac）を起動し、「3」のフォルダ内へ移動
5. `docker-compose up -d` コマンドを実行（しばらくインストールが走る）
6. ブラウザからwordpressの初期設定画面を確認 → http://localhost:8000/
<br><br><br>



## wordpress(WP)をdockerにインストール後、サイトをローカルで再現

1. 元サイトWPの管理画面で「**All-in-One WP Migration**」プラグインをインストール ＞ 有効化
2. 「All-in-One WP Migration - エクスポート - ファイル」を実行
3. docker-WPの管理画面で「**WP Htaccess Editor**」プラグインをインストール ＞ 有効化
4. 設定 - WP Htaccess Editor で **.htaccess**に以下の記述を追加・保存（WPのファイルアップロード上限設定上げ）  
\# BEGIN WordPress  
php_value upload_max_filesize 2000M  
php_value post_max_size 2000M  
php_value memory_limit 256M  
php_value max_execution_time 300  
php_value max_input_time 300  
\# END WordPress  

5. docker-WPの管理画面で「**All-in-One WP Migration**」プラグインをインストール ＞ 有効化  
6. 「All-in-One WP Migration」インポート - 「2」で保存したファイルを選択  
7. 成功したら画面の手順に従ってパーマネント設定画面で「保存」を実行 ※この時のログインID・PWは元サイトと同じものとなる  
<br><br>
※ WordPressを旧エディターに戻すプラグイン「Classic Editor」  
https://souken-blog.com/2019/04/02/wordpress-plugin-classic-editor/

<br><br><br>



## wordpress(WP)環境をリセットしたいとき
1. 「**$ docker-compose down**」でコンテナの停止を行う
2. 「**$ docker images**」でインストールされたイメージを確認（wordpressとmysqlの確認）
3. 「**$ docker rmi xxxxx**」でwordpressとmysqlを削除 ※mysqlはIMAGE IDじゃないと消せないかも
4. 「**$ docker volume ls**」で作成されたボリュームを確認（例： docker_wordpress_db_data）
5. 「**$ docker volume rm xxxxx**」でwordpressのボリュームを削除
6. publicフォルダ削除
7. 「docker-compose.yml」がある階層で「**docker-compose up -d**」を実行して再度wordpressをインストール
<br><br><br>



## コマンド一覧

<table>
 <tr>
 	<td><b>$ docker version<br>$ docker -v</b></td>
  <td>Docker のバージョン確認</td>
 </tr>
 <tr>
  <td><b>$ docker-compose version<br>$ docker-compose -v</b></td>
  <td>docker-compose のバージョン確認</td>
 </tr>
 <tr>
  <td><b>$ docker-machine version<br>$ docker-machine -v</b></td>
  <td>docker-machine のバージョン確認</td>
</tr>
</table>  
<br>


<table>
<tr>
  <td><b>$ docker-compose up -d</b></td>
  <td>コンテナの作成と開始</td>
 </tr>
 <tr>
  <td><b>$ docker-compose ps</b></td>
  <td>起動中のコンテナ一覧表示（docker-compose）</td>
 </tr>
 <tr>
  <td><b>$ docker ps</b></td>
  <td>起動中のコンテナ一覧表示（docker）</td>
 </tr>
 <tr>
  <td><b>$ docker ps -a</b></td>
  <td>起動してないものも含む全てのコンテナ一覧表示 （docker）</td>
 </tr>
 <tr>
  <td><b>$ docker rm xxxxx</b></td>
  <td>コンテナの削除 （docker）</td>
 </tr>
</table>  
<br>


<table>
<tr>
  <td><b>$ docker images</b></td>
  <td>イメージ一覧 （docker）</td>
 </tr>
 <tr>
  <td><b>$ docker rmi xxxxx</b></td>
  <td>イメージの削除 （docker）</td>
 </tr>
 <tr>
  <td><b>$ docker rmi xxxxx -f</b></td>
  <td>強制的なイメージの削除 （docker）</td>
 </tr>
</table>  
<br>


<table>
<tr>
  <td><b>$ docker volume ls</b></td>
  <td>ボリューム一覧</td>
 </tr>
 <tr>
  <td><b>$ docker volume rm xxxxx</b></td>
  <td>ボリュームの削除</td>
 </tr>
</table>  
<br>


<table>
<tr>
  <td><b>$ docker stop</b></td>
  <td>サービスの停止</td>
 </tr>
 <tr>
  <td><b>$ docker down</b></td>
  <td>コンテナの停止</td>
 </tr>
</table>  
<br><br><br>




## 参考
◆Quickstart: Compose and WordPress | Docker Documentation  
https://docs.docker.com/compose/wordpress/  

◆【初心者向け】Dockerで手軽にNode.js開発環境構築 (1) - Qiita  
https://qiita.com/yukin01/items/f597f06cb5a05b3fe82e  

◆【初心者向け】Dockerで手軽にNode.js開発環境構築 (2) - Qiita  
https://qiita.com/yukin01/items/4f54496fd2f577c56b1d  

◆Docker環境でLaravelを構築するまで、わずか15分。 - Qiita  
https://qiita.com/hosono/items/dd404f3f074722ef989d  
