# Misskey Design Note

## 共通
* TypeScriptを使用
* notice -> notification

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

## Web
* SPAにする
* Stylusを利用
* デザイン(HTML, CSS)は可能な限り流用
* ブラウザ側で使うライブラリをbowerで管理 
* Webからのリクエストは全て公開APIを使う
