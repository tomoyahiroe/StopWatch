---
marp: true
theme: default
paginate: true
style: |
    section {
        background-color: #fff;
        font-size: 36px;
        font-family: 'Helvetica', 'ヒラギノ丸ゴ'
    }
---
# ストップウォッチ作成体験会
presented by Lumos

---
## ツールのインストール
* Google Chrome
(https://www.google.com/intl/ja/chrome/)
* Visual Studio Code
(https://code.visualstudio.com/download)

---
## 作業フォルダの作成
自分の使いやすい場所に、作業用のフォルダを作ってください。
名前はstop-watchにしましょう。

---
## HTMLファイルの作成
* VScodeで新しいファイルを作成
* cmd+S/ctr+Sで、ファイル名をindex.htmlに。
* !入力後、tabキーを押してテンプレートを作成

---
すると...
![width:1000px](images/templete.png)
こんな感じに。

---
## htmlを書いてみよう
以下のように、htmlファイルはタグを使って文章を記述していきます。実際に書いてブラウザに表示されるか確認しましょう。
* &lt;p&gt;こんにちは。&lt;/p&gt;
* &lt;button&gt;押してね&lt;/button&gt;
* &lt;h1&gt;大見出しだよ&lt;/h1&gt;

---
## ボタンとディスプレイを設置しよう
ストップウォッチに必要になる要素を設置していきましょう。
* タイトル
* 秒数が映るディスプレイ
* スタート/ストップ/リセットボタン

---
## タグにidをつけよう
* pタグにはid='display'
* スタートボタンにはid='start'
* ストップボタンにはid='stop'
* リセットボタンにはid='reset'

---
完成形
![](images/visual.png)

---
## JavaScriptを使ってみよう
* now = new Date();
* console.log([出力したいもの])
* 関数の書き方
function 関数名(){処理}
* setInterval([関数],[ミリ秒数])

---
## やりたいことを考えてみよう
* スタートボタンを押したらカウントが始まる。スタートボタンは押せなくなる。
* ストップボタンを押したらカウントが止まる。ストップボタンは押せなくなる。
* リセットボタンを押したら0.00になる。
* ストップボタンを押してからもう一度スタートボタンを押すと、ストップした秒数からカウントが再度始まる。

---
##　下準備をしよう
* window.onload() // ページが読み込まれた時に、()内の処理を実行する。
これから書くコードは全てこの()内に記述します。
* 引数、定数の定義をしよう
![](images/start_define.png)

---
## カウンターを作ろう

1. let startTime = new Date(); //開始時刻を記録
1. counter = setInterval(function(){
    const now = new Date();
    display.innerHTML = ((now - startTime)/1000).toFixed
}, 20); //現在時刻と開始時刻の差をdisplayに反映

---
## start()関数を作ろう。
スタート関数はスタートボタンが押された時に起動し、カウントの開始とスタートボタンの無効化を担う。
![height:12cm](images/start_function.png)

---
## スタートボタンを押してみよう
うまくいけばこのようになります。
![](images/start_motion.png)

---


