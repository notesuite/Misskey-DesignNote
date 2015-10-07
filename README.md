# Misskey Design Note

## 共通
* TypeScriptを使用
* notice → notification
* レポジトリ
  * Core - 副作用のない関数が集まる場所
  * API
  * Web
  * Image - イメージサーバー
* スクリーンネーム
  * `/^[a-zA-Z0-9\-]{1,20}$/`
  * 保存時には大文字と小文字を区別しないが、表示時には大文字と小文字を区別する

## API
* promised-mongoを使用
* mongooseを使用しない
* Userコレクションにフォロー数/フォロワー数は保持しない
* ユーザー/ステータスの削除
  * コレクションにisDeletedフラグをつけて管理
* REST APIとStreaming APIを提供
* Streaming API内でSAuth可能
* 外部ツールへの依存
  * Node.js(npm)
  * MongoDB
  * GraphicsMagick
* REST APIのエラーのJSONの型は `T | {id: string, message: string}[]`
  * エラーかどうかはステータスコードで判断
* API名には基本的に複数形を使用
* APIの結果の返却はJSONのみ
* DB接続時にコレクションが存在しなければ作成する

## Web
* SPAにする
* Stylusを利用
* デザイン(HTML, CSS)は可能な限り流用
* ブラウザ側で使うライブラリをbowerで管理 
* Webからのリクエストは全て公開APIを使う
