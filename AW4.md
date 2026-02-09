### webサーバーの設定方法

①Nginxのwebサーバーを導入し、静的コンテンツのみの取り出す処理を行い、
動的コンテンツの生成はアプリケーションサーバーに依頼する仕組みを作る

②Nginxの設定ファイルを編集
③Nginxを介した処理に変更したため、Unicornの設定も必要
④プロセスを確認
⑤「unicorn_rails master」のプロセスをkill
⑥unicorn_railsコマンドを実行

### デプロイの自動化

## Capistrano(キャピストラーノ)を導入する

①gemファイルを修正
②Capfileを編集
③config/deploy/production.rbファイルを編集
④config/deploy.rbを編集
⑤Unicornの設定ファイルを編集
⑥Nginxの設定ファイルを編集
⑦Unicornのプロセスをkillする
⑧Gemfile.lockの設定を追加
⑨ローカルでの修正をすべてpushする
10bundle exec cap production deployで自動デプロイを実行
11ブラウザからElastic IPでアクセスして、アプリの挙動を確認


## アプリケーション修正から自動デプロイまでの流れ

状況	自動デプロイ前にやること	必要性の有無
①ローカルでVSCodeを修正した場合	変更点をリモートリポジトリにcommit→pushする
（ブランチを切っている場合はmergeまで実行）	該当時のみ
②ローカルでデータベース関連の内容を修正した場合	本番環境で「rails db:drop RAILS_ENV=production」「rails db:create RAILS_ENV=production」を実行
（※実行する際、「DISABLE_DATABASE_ENVIRONMENT_CHECK=1」というオプションが必要です）	該当時のみ
③Nginxを修正した場合	「sudo systemctl restart nginx」を実行	該当時のみ
④再度自動デプロイを実行する場合
（本番環境でサーバー再起動をする場合）	一度プロセスをkillした上で「bundle exec cap production deploy」を実行	①②の場合のみ
