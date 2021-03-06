## 00. HTML + CSS + JavaScript概観
----------------------------------
参考：http://liginc.co.jp/240644

> ### 1. HTMLとは
- マークアップ言語
- テキストをデザイン
- サンプルプログラム：sample00/sample_1.html

> ### 2. CSSとは
- HTMLの要素をどのように修飾して表示させるかを指定する
- 文字を大きくしたり、色を変えたりできる
- サンプルプログラム：sample00/sample_2.html,css
- htmlに埋め込むこともできるし、外部ファイル化してHTMLから読むこともできる

> ### 3. JavaScriptとは
- ブラウザの動的なエフェクトなどを実行できる（もはやそれだけではないが）
- htmlに埋め込むこともできるし、外部ファイル化してHTMLから読むこともできる
- サンプルプログラム：sample00/sample_3.html,css,js


## 01. HTML + CSS 基礎の基礎
----------------------------------
参考：https://liginc.co.jp/series/05engineer

> ### 1. 第１回 ブラウザとは？HTMLとは？
**結論は……**
- ブラウザとはhtmlで記述された内容に従って、
- デザインされた文字(あるいはオブジェクトなども)を表示する

次！

> ### 2. 第２回 HTMLだけで画像入りプロフィールページ
HTMLで画像を表示するのはすでに学習済みなので割愛。  
次！


> ### 3. 第３回 CSSを使って中央寄せ＋文字・背景色変更
00でやった内容で網羅済み  
次！


> ### 4. 第４回 ブラウザから世界中のWebページ(htmlファイル)が見られる理由
**ブラウザとは**
- HTMLとCSSとJavaScriptで記述されたファイル群を読み込んで、
- 指示通りに表示するソフトウェア

**世界中で見られる理由**
- サーバー上において公開されたhtmlをURLを基にアクセスできるから

まあ、常識  
WWWの仕組みとか書いているのかと思ったけど、当てが外れた  
次！


> ### 5. 第５回 classとidを使ってCSSを装飾＋CSSのファイル化
#### 1. class, idとは何か？
`h1`タグに対して  
```css
h1{
    /*命令の種類：命令の内容*/
    text-align:center
}
```
というように記述することで、h1タグに対して修飾することが可能  
しかし、これでは柔軟性が低い  
「ある場所のh1タグは青にしたいけど、他の場所では赤にしたい」などが**実現できない**  
そこで
<font color=orange>**同じタグでも異なる表現命令を出すための仕組み**</font>
としてclass,idが用意されている

#### 2. class, idの違い
分かりにくかったので他の参考サイトも  
https://lealog.hateblo.jp/entry/2011/12/06/202348

- class : 複数のタグに定義可能
- id    : 複数のタグに定義できない(idセレクタはhtmlの中で唯一の存在)

いまはこれだけでよいとする

```html
<!-- 良い例 -->
<h2 class="sub_title">コメント</h2>
<h2 class="sub_title">base_data</h2>
<!-- ダメな例 -->
<h2 id="sub_title">コメント</h2>
<h2 id="sub_title">base_data</h2>
```

#### 3. class, idの具体的な使い方（基本）
`html側`
```html
<h1 id="main_title">TITLE!!!</h1>
<h2 class="sub_title">base_data</h2>
```

`css側`
```css
/*idはシャープで書く*/
#main_title{
    text-align:center;
    color:white;
    background-color:black;
}

/*classはドットで書く*/
.sub_title{
    text-align:center;
}
```


> ### 6. 第６回 CSSでレイアウト：divタグで箱作り、floatで横並べ
**まとめ**
- `div`タグ
    - division(区分)を意味する
    - 単体では意味をなさない
    - HTMLタグを一つのグループにするもの
    - div class="hoge" などで命令を記述
- `float`命令
    - 要素を並べるためのCSSにおける命令
    - セレクタの定義に記述する
    - 何もないと、以降全てにおいて同じルールで並べてしまう
    - 並べる必要のないセレクタで`clear : both;`で無効化する
- サンプルプログラム
    - sample01/lecture06/profile.html
    - sample01/lecture06/profile.css

> ### 7. 第７回 ボックスモデルとは？：divで作った箱を整える

divで作った箱はボックスモデルと呼ばれる  
要素は下記
- border
- width
- height
- content
- padding
- margin
- background

イメージでいうと下記  

![ボックスモデル1](./doc_img/boxmodel_01.png "サンプル")

![ボックスモデル2](./doc_img/boxmodel_02.png "サンプル")

# <font color=orange>__サンプルプログラム作成から再開__</font>

- サンプルプログラム
    - sample01/lecture07/profile.html
    - sample02/lecture07/profile.css


> ### 8. 第８回 ボックスモデル応用：margin/paddingで視認性向上









## 02. HTML5 CSS3について
----------------------------------
参考：http://amarron.hatenablog.com/entry/2015/05/25/000334

> ### 1. HTML5とは
- HTML4/XHTML1は「文章定義」のマークアップ言語
- HTML5はWebアプリケーションのプラットフォーム

> ### 2. HTML5で追加された要素
- ドキュメント構造の要素が追加
- マルチメディア要素
    - 動画`video`タグや音楽`audio`タグ
    - `audio`タグはJSからアクセスできるAudioApiがあり、複雑な操作を可能にする

> ### 3. HTML5の新機能
- グラフィックス
    - Canvas：線や図を描く機能
        - これまではJPGやPNGの画像を用意する必要があったが
        - HTML5では絵が描ける
        - HTML5`canvas`タグ作る⇒jsでこの要素にDOMでアクセス、操作という流れ
    - SVG：が扱えるようになる
        - もちろんJSからDOMにアクセスできる
    - WebGL：が扱える
        - Canvasと同様にJSで実装し`canvas`要素に対して描画を行う
- 位置情報：Geolocation API
    - ユーザの位置情報を取り扱う機能
- 履歴：History API
    - ブラウザの履歴を管理・操作する機能
- ストレージ：Web Strage
    - ブラウザ側にデータを保持する機能
- オフライン対応：Application Cache
    - ブラウザにファイルをキャッシュさせ、オフラインでアクセスする機能
- ファイル操作：D&D API / File API
    - ブラウザ外のファイルをD&D、アクセスできる
- 並列処理：Web Workers
    - JavaScriptの処理を並列で実行できる

> ### 4. CSS3とは
- CSS2.1までは画像を使わざるを得なかった表現もCSSで表現できるようになった
- モジュール単位で仕様を策定している

> ### 5. CSS3で使える新機能
- アニメーション
- グラデーション
- ドロップシャドウ
- ボーダー
- その他いろいろ……


## 03. JavaScriptが動く仕組み
----------------------------------


