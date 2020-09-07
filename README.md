
# このサイトについて

URL: https://kun153.github.io

## Umi

"Umi" は "Honoka"を元にした日本語も美しく表示できるBootstrapテーマです。

## jekyll

URL: http://127.0.0.1:4000/

## 文法メモ

### 画像の載せ方
```html
<!--4枚画像-->
<div class="row img-padding row-bottom">
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="hoge.jp" alt="" title="サンプル"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  <div class="col-lg-4"></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  <div class="col-lg-4"></div>
</div>

<!--3枚画像-->
<div class="row img-padding">
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
</div>

<!--2枚画像-->
  <div class="row img-padding">
    <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
    <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
    <div class="col-lg-4"></div>
  </div>

   <!--1枚画像-->
  <div class="row img-padding">
    <div class="col-lg-4 col-sm-6"><img  class="img-fluid" src="" alt="" title=""></div>
  </div>
```

### 表
```html
<table class="table table-striped">
  <thead>
    <tr>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>
```


### フロントマター

```markdown
---
layout: post
title:  "Potatoes"
date:   2015-11-25
lastchange : 2017-08-13
categories: writing
---
```

## 各ページのメモ

### days

[2020-02-25]準備中<br>
[2020-04-30]2020week17からパスを変える。いずれ全部移行したい。<br>
[2020-05-25]形式が変わってしまったので記事側の変更もしないと。<br>

### anime

[2020-02-25]準備中

### movie

[2020-02-25]準備中

## 改訂履歴

### サイトの進捗
[2020-02-25]カテゴリ整備(movies TVdrama tokushu anime music の追加) ナビバーにドロップダウンリスト追加 archiveの実装　フッターを作成<br>
[2020-02-27]フッターやめる。<br>
[2020-03-08]見出しのbottom-topを2remに。<br>
[2020-03-18]gamesの追加<br>
[2020-04-13]board 廃止 検討<br>
[2020-04-13]v2.0の構想を固め始める パンくずリスト archivesの廃止とindexを活躍させる 画像置き場を作る　pタグ brの使い方について 体裁を整えたい<br>
[2020-05-25]v2.0.0完成

### サイトの課題
- フッターの作成(？)
- 画像の表示
- 画像の管理方法
  - evernoteからのリンク
  - 別リポジトリにアップロード
  - issueにアップロードして形成されたURL
    - [GitHubのissueを悪用して画像をホストする - Qiita](https://qiita.com/kotet/items/a2203a400136ba50b41e)
  - imgurなどアップローダーを利用する(2020-04-13 採用中)
- ページによって表示がずれる→スクロールバーの差だった。 
- 日付の付け方
  - 202002 or 2020-02 など　(2020-04-13 ハイフン採用中)
- 引用文の明示
- マークダウンが正しく変換されない→パーティカルバーがtableとして認識されていた。
- サイドバーの実装
- bookに加えて○○の実装(hobby？)
  - drama movie anime のドロップダウンリスト
- アーカイブは複数形か否か
- 色使い
- URLの命名の悩み
  - tvdrama
- ちょっと複雑なことをしようとすると結局HTMLで書いたほうが良い
- cssを上書きしてしまう。そのうち分離する必要がある?
- table-striped が利かない
- 好きな画像をはりたい
- pタグ brの使い方について 体裁を整えたい
- 相対リンク
  - ひいてはリダイレクト設定をして「戻るボタンの実装」

### v2.0.0(2020-05-25)
#### 修正点
- _postの設置
- _draftの設置
- _includeの設置
- docsの設定
- layoutの刷新
- 記事タイトルの形式変更　date
- ギャラリーの追加
- gamesなどの調整

#### 未実装　アイデア
- categoryやtagの設定
- パンくずリスト
- 戻るボタンなど
- linksの廃止
- specialの改造
- index.html構想

### v2.1.0(2020-05-29)
- tvprogramsの設置

### v3.0.0(2020-05-30)
- "kun153"にユーザ―名を変更
  - 全てのユーザー名を置換

### v3.0.1(2020-06-08)
- スマホに対応したレスポンシブデザインを志向

### v3.1.0(2020-06-20)
- archive廃止 → READEMEに移動
- links廃止 → pocketに移動

### v3.1.1(2020-07-30)
- navbarのリンクを相対パスにしてみる
