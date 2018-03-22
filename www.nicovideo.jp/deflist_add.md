# POST ttp://www.nicovideo.jp/api/deflist/add

とりあえずマイリストに追加するAPI。
JSONが返ってくる。

# パラメータ

|name|description|
|---|---|
|item_id|動画ID(e.g. sm9)|
|token|APIトークン?|
|unwatched|`0`(不明)|

# レスポンス

`status`が`ok`なら成功、`fail`なら失敗。
`fail`の場合は`error.code`にエラーコード、`error.description`にエラーの説明が書いてある。

## 生レスポンス

<details>
<summary>成功時</summary>

```json
{"status":"ok"}
```

</details>

<details>
<summary>失敗時(すでに追加済み)</summary>

```json
{"error":{"code":"EXIST","description":"\u3059\u3067\u306b\u767b\u9332\u3055\u308c\u3066\u3044\u307e\u3059"},"status":"fail"}
```

</details>

<details>
<summary>失敗時(マイリストする対象がない場合)</summary>

```json
{"error":{"code":"NONEXIST","description":"\u30a2\u30a4\u30c6\u30e0\u304c\u5b58\u5728\u3057\u307e\u305b\u3093"},"status":"fail"}
```

</details>
