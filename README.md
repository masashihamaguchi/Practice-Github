# Practice Github
Practice Github for L4S 8th WebD  
Github練習用のリポジトリです。ターミナルやコマンドプロンプトに慣れていない人も実際に手を動かしてやってみましょう。  
あみたんが書いた**git/GitHub基礎**を読みながら進めるのがオススメ。

# コマンドの確認

| | Mac(ターミナル) | Windows(cmd) |
| :--: | :--: | :--: |
| ディレクトリの移動 | `cd [移動したいディレクトリ]` | `cd [移動したいディレクトリ]` |
| ディレクトリの中身の表示 | `ls` | `dir` |
| 現在のディレクトリを表示 | `pwd` | `cd` |

続きは下のサイトをチェック
> for Mac  
> https://www.alloneslife-0to1work.jp/code/command-line/terminal  
> for Windows  
> https://proengineer.internous.co.jp/content/columnfeature/5007  


# Exercise
実際にやってみよう！

## 1. 自分用のリポジトリを作成する
まずはSlackに送った招待用リンクをクリックして自分専用のリポジトリを作成しましょう。（Githubにログインした状態でリンクを踏めば自動的に作られるはず）  
作成が完了したらそのリンクをクリックしてリポジトリページを開きます。  
L4S WebDチームの中にリポジトリが新しく作られます。

=== たぶんいまはここにいるはず ===

## 2. プロジェクトをクローンする
右上の**Code**をクリックしてリンクをコピー。
<img width="669" alt="スクリーンショット 2020-09-19 15 59 14のコピー" src="https://user-images.githubusercontent.com/21216852/93663654-7f90d480-faa4-11ea-90a0-aa7ac8fdfdc6.png"><br>  

**※今回は`HTTPS`を使用しているが、SSH設定をしている人は`SSH`のリンクをコピー！**  

ssh設定をするとpushする時にいちいちユーザー名とパスワードを入力することなく簡単にできるようになります。詳しく書くと長くなるので、とりあえず簡単にGithubとやりとりできるようになると覚えておけばOK！ssh設定をしてない人は参考ページを最後に載せているので、設定するのがオススメ！

<img alt="image" width="400"  src="https://user-images.githubusercontent.com/21216852/93662450-240e1900-fa9b-11ea-994e-a3ffc3731fca.png"><br>

ターミナルでプロジェクトをダウンロードしたい場所に移動する。
（今回はデスクトップにプロジェクトファイルを保存します）
![image](https://user-images.githubusercontent.com/21216852/93661409-8c0c3180-fa92-11ea-849c-098ddb70f890.png)

プロジェクトをクローンする。
```
$ git clone [コピーしたリンク]
```  
ex) `git clone https://github.com/L4S-8th-WebD/practice-github-xxxxxxxxxx.git`

正常に終了すると任意の場所にプロジェクトファイルがクローンされているはず。  
ブラウザで`index.html`を開いてみよう！  

## 3. エディターでプロジェクトを開いて編集する
Bracketsなどでプロジェクトファイルを開く。
`index.html`を開いて`<h1>`タグで囲まれた部分に自分のニックネームを書く。

<img alt="image" height="70" src="https://user-images.githubusercontent.com/21216852/93661608-0a1d0800-fa94-11ea-863b-caa955fc0311.png">

ニックネームを書いたら保存する。  
ここからターミナルを使ってコミット&プッシュをする。

このときエディターによっては`index.html`の文字の色がわかっているはず。
![image](https://user-images.githubusercontent.com/21216852/93661836-0ab69e00-fa96-11ea-87ee-05a67424d403.png)

## 4. ターミナルでcommit&push
ターミナルに戻って作業ディレクトリを移動する。  
（デスクトップからプロジェクトファイルに移動する）
```
$ cd [プロジェクトファイルの名前]
```

あとはいつも通りにgit操作をする
```
$ git add .
$ git commit -m "任意のコメント（日付と実装した昨日など？）"
$ git push origin master
```

プロジェクトのページを開いて最新の状態になっていることを確認する。
![image](https://user-images.githubusercontent.com/21216852/93661936-ce377200-fa96-11ea-9c36-5efe7372fdca.png)

## 5. branchを使ってみる

branchとはバージョンを分岐させることで、本番環境に影響を与えずに開発を行える機能のこと。branchを作成することで本番環境と開発環境を切り分けることができるため、プロジェクト本体に影響を与えることなく開発を行うことができる。
とりあえずやってみよう！

`develop`ブランチを作成する
```
$ git branch develop
```
`develop`ブランチに移動する
```
$ git checkout develop
```
いま行った作成&移動の2つの作業は下のコードで同時に行うことができる。
```
$ git checkout -b develop
```

エディターに戻って`index.heml`を編集しよう。  
`h2`タグで囲まれた部分にリーダーズの期とコースを書こう。

<img alt="image" height="70" src="https://user-images.githubusercontent.com/21216852/93662165-f4f6a800-fa98-11ea-82ed-29d34a7219a2.png">

できたらファイルを保存。同じようにcommit&pushする。

```
$ git add .
$ git commit -m "任意のコメント"
$ git push origin develop
```
※pushする時は`master`ではなく`develop`になるので注意！

githubを確認すると新しくdevelopブランチが出来ているはず。  
このときmasterブランチを確認するとさっきの変更内容が反映されていないはず。（リーダーズの期とコースが書かれていない状態）  
ブラウザでもリロードすると違いが確認できるはず。  

### Tips
ブランチで使えるコマンドまとめときます。

今のブランチを確認する
```
$ git branch
```
ブランチを切り替える
```
$ git checkout <branch>
```
ブランチの名前を変更する
```
$ git branch -m <oldbranch> <newbranch>
```
ブランチを削除する
```
$ git branch -d <branchname>
```

詳しくは下の参考リンクを参照。

## 6. mergeしてみる

今度は`develop`ブランチで更新した内容を`master`ブランチに反映させてみよう。この作業をmergeという。（開発環境を本番環境に反映さえる）

まずは`master`ブランチに移動。
```
$ git checkout master
```
`master`ブランチにいることを確認してdevelopブランチをマージする。
```
$ git merge develop
```
`master`ブランチが上書きされて最新の状態になる。

## 7. conflictを起こしてみる
conflictとはブランチをマージしたときにそれぞれのブランチで同じ場所に変更があると発生する競合エラーのこと。branchを作成したcommitからどちらも変更されているため、どちらが活かすべき正しいコードなのかわからない状態。詳しくは**git/GitHub基礎**を参照。
とりあえず実際にconflictを発生させてどのようなときに発生するか見てみよう。

新たに`color`ブランチを作成する。
```
$ git branch color
```

`master`ブランチのまま`index.html`を編集する。  
`body`タグに`color`セレクタを指定。

<img alt="image" height="70" src="https://user-images.githubusercontent.com/21216852/93663053-dc3dc080-fa9f-11ea-8b8e-9ed52fa9e63d.png"><br>

commitする。
```
$ git add .
$ git commit -m "color"
```

`color`ブランチに移動する。  
```
$ git checkout color
```
（エディターでプロジェクトファイルを開いた状態のままブランチを変更しても、そのブランチの内容に合わせてエディター上でファイルの中身が変わっていることが確認できる。つまり、ターミナルで`color`ブランチに変えてからエディターに戻るとさっき`body`タグに指定した`color`セレクタが消えているはず）  
<img alt="image" height="70" src="https://user-images.githubusercontent.com/21216852/93663234-368b5100-faa1-11ea-8256-c2d63358025e.png">

`master`ブランチと`color`ブランチを往復すれば分かるはず。

今度は`body`タグに`gradation`セレクタを指定。

<img alt="image" height="70" src="https://user-images.githubusercontent.com/21216852/93663201-e8764d80-faa0-11ea-8b00-a1eed150e571.png"><br>

さっきと同じようにcommitする。
```
$ git add .
$ git commit -m "gradation"
```
`master`ブランチに移動する。
```
$ git checkout master
```
さっきと同様に`color`ブランチを`master`ブランチにマージする。
```
$ git merge color
```

すると`CONFLICT`と表示されて、`index.html`でconflictが起きていることがわかる。
![image](https://user-images.githubusercontent.com/21216852/93663362-5e2ee900-faa2-11ea-8c3f-6c2c9415ec5e.png)

エディターをみると競合が発生している箇所をわかりやすく表示してくれている。上のピンクが`master`ブランチで下の水色が`color`ブランチのコードを表している。

<img width="448" alt="スクリーンショット 2020-09-19 18 03 35" src="https://user-images.githubusercontent.com/21216852/93663374-7dc61180-faa2-11ea-8696-33cec282d68c.png"><br>  


これがconflictが発生した状態。別々のブランチで同じ箇所を変更したの後にマージをするとこのようなエラーが発生する。スクショのようにエディター上でconflictが発生した場所を丁寧に示してくれている場合は自分が使用したい方の`Use me`を押せば解決してくれる。  

しかし今回はgitの練習なのでターミナルを使って解決してみよう！  
`master`ブランチを1つ前のcommitの状態に戻す。`color`ブランチは1つ前のcommitのときに作成したのでそこまでバージョンを戻せばconflictは発生しない。（**git/GitHub基礎**にわかりやすい絵があります）  

commitの履歴を確認する。
```
$ git log
```
1番上が現在のcommit、2つ目が1つ前のcommitなので2つ目のcommit IDをコピーする。（赤線のハッシュ）
<img width="682" alt="スクリーンショット 2020-09-19 18 25 55のコピー" src="https://user-images.githubusercontent.com/21216852/93663943-46596400-faa6-11ea-97c4-a165e0c94687.png">

commitを戻す。
```
$ git revert [コピーしたcommit ID]
```
もう一度mergeをする。
```
$ git merge color
```
今度はマージが成功する。

## 8. 復習
`develop`ブランチに移動して`<h2>`タグの下に`<p>`タグを追加して好きな一言を書いた後、保存・commitをして`master`ブランチにマージしてみよう。

このようになればマージ成功。
![image](https://user-images.githubusercontent.com/21216852/93666591-6dba2c00-faba-11ea-979a-6c02600a97cc.png)

ブラウザで確認してみよう。  
ここまで一通りできたらOK！
<img width="1792" alt="スクリーンショット 2020-09-19 20 13 33" src="https://user-images.githubusercontent.com/21216852/93665850-cdadd400-fab4-11ea-9156-9257753530bf.png">

# 参考リンク
## Git / GitHub

- git/GitHub基礎（リンクはSlackから）  

- サル先生のGit入門
> https://backlog.com/ja/git-tutorial/

## コマンドライン
- for Mac
> https://www.alloneslife-0to1work.jp/code/command-line/terminal  

- for Windows
> https://proengineer.internous.co.jp/content/columnfeature/5007  

## SSH設定
sshは簡単にいうとローカル（自分のPC）からサーバー（Githubのサーバー）を遠隔操作する仕組みのことで、暗号化した通信を行う。公開鍵と秘密鍵の2つを作成し、公開鍵をサーバーに渡すことでクライアントからサーバーサイドへ簡単に接続できるようになるもの。とりあえず、pushするとかpullが楽になると覚えておけばOK！  
僕自身もそんなに詳しいわけではないので記事を参考にしながら設定してみだください。

> https://qiita.com/shizuma/items/2b2f873a0034839e47ce  
> https://qiita.com/0ta2/items/25c27d447378b13a1ac3



<br><br><br>

質問やその他わからないことがあったらいつでも聞いてください〜
