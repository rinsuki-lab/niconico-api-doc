# GET ttp://www.nicovideo.jp/api/mylistgroup/list

自分のマイリスト一覧を取得するAPI。
JSONで返ってくる。

# レスポンス

`status`が`ok`なら成功、`fail`なら失敗。

失敗時は`error.code`にエラーコード、`error.description`にエラーの説明が書いてある。
成功時は`mylistgroup`が配列になっている。

|name|description|
|---|---|
|id|マイリストID。`http://nico.ms/mylist/`を頭に付けるとアクセスできるURLになる。|
|user_id|マイリストを所持しているユーザーID?|
|name|マイリスト名|
|description|マイリストの説明文?|
|public|マイリストを他人に公開するかどうか。`"1"`なら公開|
|default_sort|開いたときのデフォルトソート順|
|create_time|マイリストを作った時間のUNIXタイムスタンプ|
|update_time|マイリストを更新した時間?のUNIXタイムスタンプ|
|sort_order|マイリスト一覧での表示場所|
|icon_id|アイコンのID `http://nicovideo.cdn.nimg.jp/uni/img/zero_my/icon_folder_default.png`のy座標にicon_id*23pxすると対象アイコンが取れる?|

## 生レスポンス

<details>
<summary>成功時</summary>

諸事情により手動で一部編集しています

```json
{"mylistgroup":[{"id":"59382040","user_id":"51694632","name":"\u30a2\u30a4\u30de\u30b9\u95a2\u9023","description":"","public":"1","default_sort":"6","create_time":1499052705,"update_time":1499052721,"sort_order":"3","icon_id":"0"}],"status":"ok"}
```

</details>

<details>
<summary>失敗時(未ログイン)</summary>

```json
{"error":{"code":"NOAUTH","description":"\u8a8d\u8a3c\u3067\u304d\u307e\u305b\u3093\u3067\u3057\u305f"},"status":"fail"}
```

</details>