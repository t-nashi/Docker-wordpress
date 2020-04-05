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
