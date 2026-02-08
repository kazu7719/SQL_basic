### アプリケーションサーバー(EC2)の作成手順

①サーバーにログインするための鍵を作成
②サーバーを作成するために必要な情報を選ぶ
③サーバーを作成する
④サーバーを全世界へ公開する準備をする
⑤サーバーの設定を変更する
⑥サーバーの設定ができたか確認する


## ①について
CloudShellを開き、キーペアを作成。
aws ec2 create-key-pair コマンドを使う

## ②について
EC2を作成するためのAMIというなの設計図を取得
AMIには以下の情報がまとまっている
・サーバーを始めるために必要なアプリケーション
・サーバーについての情報の保管場所
・AWSアカウントがAMIを使ってサーバーを始めるための許可

AMIの取得にはaws ec2 describe-images コマンドうぃ使用

## ③について
aws ec2 run-instances コマンドを使ってEC2を作成

## ④について
サーバーを全世界へ公開するために前段階として、
Elastic IPを作成・割り当てをする。
aws ec2 allocate-address コマンドを使う

Elastic IPが取得できたら、aws ec2 associate-address コマンドで
EC2インスタンスとElastic IPを紐付けする。

EC2インスタンスにElastic IPが設定されているか確認するために、
aws ec2 describe-addresses コマンドを使用する 

## ⑤について
立ちあげたばかりのEC2インスタンスはsshでアクセスできるが、HTTPなどの他の接続は一切つながらないようになってるためHTTPに繋がるポート(玄関)が必要。
ポートを設定するためにはセキュリティグループの設定が必要

aws ec2 create-security-group コマンドでセキュリティグループを作成
その後、外部からEC2へのアクセスを制御するためのインバウンドルールでポートを
aws ec2 authorize-security-group-ingress コマンドで設定
次に、aws ec2 modify-instance-attributeコマンドを使ってセキュリティグループをEC2インスタンスに紐づける　