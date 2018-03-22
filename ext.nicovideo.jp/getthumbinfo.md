# GET ttp://ext.nicovideo.jp/api/getthumbinfo/:video_id

動画情報を取得するAPI。
XMLで返ってくる。

# パラメータ

|name|description|
|---|---|
|:video_id|動画ID(e.g. sm9)|

# レスポンス

XML

`//nicovideo_thumb_response`の`status`属性が`ok`なら成功、`fail`なら失敗。

失敗時は`//nicovideo_thumb_response/error`に情報がある(`./code`にエラーコード、`description`にエラー内容の説明)。

成功時は`//nicovideo_thumb_response/thumb`に情報がある

|tag_name|description|
|---|---|
|video_id|動画ID(sm9とか)|
|title|動画タイトル|
|description|動画の説明文 (HTMLが使われていてもすべて削除されている)|
|thumbnail_url|サムネイルのURL(小)|
|first_retrieve|投稿時間?|
|length|動画の長さ(分:秒) 極端に長い動画(sm6948931など)はここが空になっていることがあるので信用するべきではない|
|movie_type|動画の拡張子 flvかmp4かswfだと思う|
|size_high|smileサーバーに保存されている非エコノミー動画のファイルサイズ|
|size_low|smileサーバーに保存されているエコノミー動画のファイルサイズ エコノミー動画が存在しない場合(エコノミー回避されている動画/nm動画など)は0になる|
|view_counter|再生数|
|comment_num|コメント数|
|mylist_counter|マイリスト数|
|last_res_body|最近付けられたコメントの一部?|
|watch_url|視聴ページ(`http://www.nicovideo.jp/watch/:video_id`)のURL|
|thumb_type|`video`のみ?(不明)|
|embeddable|`1`だと埋め込み可能 `0`だと不可|
|no_live_play|ニコニコ生放送での埋め込み不可かどうか?|
|tags|この子要素の`<tag>`に付けられているタグが入っている これ自体の属性のdomainはニコニコ動画のリージョンを表す?|
|`tags/tag`|`category`属性が1の場合はカテゴリータグ `lock`属性が1の場合は投稿者ロックがされているタグ|
|user_id|投稿者のユーザーID 投稿者が消えていても中身は入っている|
|user_nickname|投稿者のニックネーム 投稿者が消えていても中身は入っている|
|user_icon_url|投稿者のアイコンURL|
|ch_id|投稿チャンネルのID|
|ch_name|投稿チャンネルの名前|
|ch_icon_url|投稿チャンネルのアイコンURL|

## 生レスポンス

<details>

<summary>成功時(sm9)</summary>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<nicovideo_thumb_response status="ok">
  <thumb>
    <video_id>sm9</video_id>
    <title>新・豪血寺一族 -煩悩解放 - レッツゴー！陰陽師</title>
    <description>レッツゴー！陰陽師（フルコーラスバージョン）</description>
    <thumbnail_url>http://tn.smilevideo.jp/smile?i=9</thumbnail_url>
    <first_retrieve>2007-03-06T00:33:00+09:00</first_retrieve>
    <length>5:19</length>
    <movie_type>flv</movie_type>
    <size_high>21138631</size_high>
    <size_low>17436492</size_low>
    <view_counter>17069576</view_counter>
    <comment_num>4638994</comment_num>
    <mylist_counter>173151</mylist_counter>
    <last_res_body>どーまんせーまん ううう うううううううううう うううううううううう うううううううううう 修造かよ ララララララララララ </last_res_body>
    <watch_url>http://www.nicovideo.jp/watch/sm9</watch_url>
    <thumb_type>video</thumb_type>
    <embeddable>1</embeddable>
    <no_live_play>0</no_live_play>
    <tags domain="jp">
      <tag lock="1">陰陽師</tag>
      <tag lock="1">レッツゴー！陰陽師</tag>
      <tag lock="1">公式</tag>
      <tag lock="1">音楽</tag>
      <tag lock="1">ゲーム</tag>
      <tag>β時代の英雄</tag>
      <tag>最古の動画</tag>
      <tag>3月6日投稿動画</tag>
      <tag>ニコニコ文化を支えている人</tag>
    </tags>
    <user_id>4</user_id>
    <user_nickname>中の</user_nickname>
    <user_icon_url>https://secure-dcdn.cdn.nimg.jp/nicoaccount/usericon/s/0/4.jpg?1271141672</user_icon_url>
  </thumb>
</nicovideo_thumb_response>
```

</details>

<details>
<summary>成功時(nm2829323)</summary>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<nicovideo_thumb_response status="ok">
  <thumb>
    <video_id>nm2829323</video_id>
    <title>NMMでぽぽたんダンス×ｳｯｰｳｯｰｳﾏｳﾏ(ﾟ∀ﾟ)</title>
    <description>静止画を10ミリ秒単位で切り貼り（ただし、NMMは25fpsなので40ミリ秒まで余裕はあります）。タイミングは波形をみながら、アニメーションは楽曲の164.2BPMに合わせて一小節32コマになるように計算してます（16枚ループ）。めっちゃ疲れるから真似しない方がいいです。mylist/5848493■NMMとはニコニコムービーメーカーのことです。■u→ｳｯｰｳｯｰｳﾏｳﾏ(ﾟ∀ﾟ)4/20さらに高画質に[nm3053480]HTML5用[sm3991883]←CTRLキーを押しながらクリック</description>
    <thumbnail_url>http://tn.smilevideo.jp/smile?i=2829323</thumbnail_url>
    <first_retrieve>2008-03-29T23:06:23+09:00</first_retrieve>
    <length>2:54</length>
    <movie_type>swf</movie_type>
    <size_high>3929182</size_high>
    <size_low>0</size_low>
    <view_counter>72888</view_counter>
    <comment_num>4445</comment_num>
    <mylist_counter>1021</mylist_counter>
    <last_res_body>ウッーウッーウマウマ u u ウッーウッーウマウマ u ウッーウッーウマウマ uuuuuuuuuuuuuuuuuuuu u uuuuuu uuuuuuuuuuuuuuuuuuuu </last_res_body>
    <watch_url>http://www.nicovideo.jp/watch/nm2829323</watch_url>
    <thumb_type>video</thumb_type>
    <embeddable>1</embeddable>
    <no_live_play>0</no_live_play>
    <tags domain="jp">
      <tag lock="1">ニコニコムービーメーカー</tag>
      <tag lock="1">ｳｯｰｳｯｰｳﾏｳﾏ(ﾟ∀ﾟ)</tag>
      <tag>神芝居</tag>
      <tag>神画質</tag>
      <tag category="1" lock="1">その他</tag>
      <tag>ぽぽたん</tag>
      <tag>発想の勝利</tag>
      <tag>NMM</tag>
      <tag>ぬるぬる動く</tag>
      <tag>変態画質</tag>
      <tag>ニコニコ技術部</tag>
    </tags>
    <user_id>4080496</user_id>
    <user_nickname>新ドナP</user_nickname>
    <user_icon_url>https://secure-dcdn.cdn.nimg.jp/nicoaccount/usericon/s/408/4080496.jpg?1491755740</user_icon_url>
  </thumb>
</nicovideo_thumb_response>
```

</details>

<details>
<summary>成功時(so25307875, 1420774948)</summary>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<nicovideo_thumb_response status="ok">
  <thumb>
    <video_id>so25307875</video_id>
    <title>アイドルマスター シンデレラガールズ　第1話</title>
    <description>島村卯月はアイドルを夢見て養成所に通う普通の女の子。ある日卯月の前にやって来た３４６プロダクションのプロデューサーに、シンデレラプロジェクトの再選考枠三名のうちの一人として合格したと告げられる。喜ぶ卯月だがプロジェクトスタートにはメンバーがまだ二人足りず……。Ｐはもう一人のアイドル候補、渋谷凛をスカウトしようとしていた。しかし凛はアイドルに興味がないとスカウトを突っぱねていて……。コミカライズが今すぐ読める！動画一覧はこちら第2話 watch/1421383647</description>
    <thumbnail_url>http://tn.smilevideo.jp/smile?i=25307875.34887</thumbnail_url>
    <first_retrieve>2015-01-12T21:30:00+09:00</first_retrieve>
    <length>24:05</length>
    <movie_type>mp4</movie_type>
    <size_high>150680999</size_high>
    <size_low>50704837</size_low>
    <view_counter>1623967</view_counter>
    <comment_num>108231</comment_num>
    <mylist_counter>9004</mylist_counter>
    <last_res_body>うづりんすこ 割れる割れる! 怖すぎ おまえら は? ん? お前らニックネーム付 wwwww ああ… え? かわいい 草 かっわ かっわいい あっ かっわ リセマラは草 かわええ かっわいい・・・ かわいい かわいい・・・・ しぶりい... </last_res_body>
    <watch_url>http://www.nicovideo.jp/watch/1420774948</watch_url>
    <thumb_type>video</thumb_type>
    <embeddable>1</embeddable>
    <no_live_play>0</no_live_play>
    <tags domain="jp">
      <tag category="1" lock="1">アニメ</tag>
      <tag lock="1">アイドルマスター</tag>
      <tag lock="1">アイドルマスターシンデレラガールズ</tag>
    </tags>
    <ch_id>2602382</ch_id>
    <ch_name>アイドルマスター シンデレラガールズ</ch_name>
    <ch_icon_url>https://secure-dcdn.cdn.nimg.jp/comch/channel-icon/64x64/ch2602382.jpg?1445913049</ch_icon_url>
  </thumb>
</nicovideo_thumb_response>
```

</details>

<details>
<summary>失敗時(削除/運営削除/非公開動画)</summary>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<nicovideo_thumb_response status="fail">
  <error>
    <code>DELETED</code>
    <description>deleted</description>
  </error>
</nicovideo_thumb_response>
```

</details>

<details>

<summary>失敗時(存在しない動画ID)</summary>

```xml

<?xml version="1.0" encoding="UTF-8"?>
<nicovideo_thumb_response status="fail">
  <error>
    <code>NOT_FOUND</code>
    <description>not found or invalid</description>
  </error>
</nicovideo_thumb_response>
```

</details>