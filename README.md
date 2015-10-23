# Misskey Design Note
https://docs.google.com/drawings/d/1vn0SF9QWRk9kqRUO77kSH-G6ol_GX3ykwDLki8MG3LM/edit?usp=sharing

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
* すべての画像はアルバムシステムで一元管理する

## API
* REST APIとStreaming APIを提供
* Streaming API内でSAuth可能
* 外部ツールへの依存
  * Node.js(npm)
  * MongoDB
  * GraphicsMagick
  * Redis
  * node-gyp
  * Python
* REST APIのエラーのJSONの型は `T | {id: string, message: string}[]`
  * エラーかどうかはステータスコードで判断
* API名には基本的に複数形を使用
* APIの結果の返却はJSONのみ

### データベースのコレクション
* User [#12](https://github.com/MissKernel/Misskey-DesignNote/issues/12)
* Status [#13](https://github.com/MissKernel/Misskey-DesignNote/issues/13)

<!-- * Image [#15](https://github.com/MissKernel/Misskey-DesignNote/issues/15) -->

* Application [#20](https://github.com/MissKernel/Misskey-DesignNote/issues/20)

## Web
* 外部ツールへの依存
  * Node.js(npm)
  * MongoDB
* SPAにする
* Stylusを利用
* デザイン(HTML, CSS)は可能な限り流用
* ブラウザ側で使うライブラリをbowerで管理 
* Webからのリクエストは全て公開APIを使う
* Webでしか必要とされない情報はWebでコレクションを作り対応する

## Image
* 外部ツールへの依存
  * Node.js(npm)
