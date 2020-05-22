# 開発Plan

## DB - usersモデル -
|Column|Type|Options|
|------|----|-------|
|line_id|string|null: false|
### explain
- LINE botから定期的に天気予報をアナウンスするには、送信先の「ID」が必要となる。
- そして、このIDは友達登録された際に取得することができる。= IDをDBに保存する。


## RAKE File
- Heroku Schedulerを使用する。
- その実行内容をRakeファイルに書く。
- 気象庁の天気予報情報（福岡）がXMLで配信されているので、それを活用する。
- 決まった時間に連絡できる仕様。
- ifの条件式の中で降水確率によって送信されるメッセージを変更できる仕様としたい。


## Controller
- ユーザーのアクションに対しての反応を定義する。(公式ドキュメントを読み漁る)
- LINEでメッセージが送られてきた際の返信
- 友達登録した際のDBへのIDの登録
- 友達解除した際のDBからのIDの削除


## deploy
- 今回はHerokuを想定する。
- Heroku Schedulerを登録する。
