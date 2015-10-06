# Misskey Design Note

## 決まったこと
### 共通
* TypeScriptを使用
* notice -> notification

### API
* MongoDBを使用
* promised-mongoを使用
* mongooseを使用しない
* Userコレクションにフォロー数/フォロワー数は保持しない
* ユーザー/ステータスの削除
  * コレクションにisDeletedフラグをつけて管理
* REST APIとStreaming APIを提供
* Streaming API内でSAuth可能

### Web
* SPAにする
* Stylusを利用
* デザイン(HTML, CSS)は可能な限り流用
* ブラウザ側で使うライブラリをbowerで管理 
