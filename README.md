# MCC Git-C 言語講座

今回は Git を使って C言語 でリバーシプログラムを作ります。

## Git の環境構築

vscode の拡張昨日から検索欄に`git`と入れ、 Git Graph 、 Git History の2つをインストールしてください。

![git検索](./markDownResource/git1.png)

インストールしている間に Git の概要を話したいと思います。

## Git とは

Git とは、ソースコードなどの変更履歴を記録・追跡するための**バージョン管理システム**です。Git を使うことで、**誰が、いつ、どのような変更を行ったかを記録**することができます。

覚えてほしい単語

```
repository
- local repository
- remote repository
clone
commit
branch
- local branch
- remote branch
checkout
marge
push
pull
pull request
fetch
conflict
gitingore
Github
```

## repository (リポジトリ)

リポジトリとは、バージョン管理システムで管理したい範囲のファイルやディレクトリと、それらの**変更履歴データなどをまとめたもの**です。基本的に、1つのアプリケーションを作るときなど、1つのプロジェクトに対して1つのリポジトリを作成します。

リポジトリはローカルリポジトリとリモートリポジトリの2種類があります。サーバー上(リモート)にあるリポジトリをリモートリポジトリと呼び、自分のパソコン(ローカル)にあるリポジトリをローカルリポジトリと呼びます。

## clone (クローン)

クローンとは、**リモートリポジトリをローカル環境に複製すること**です。複製してローカル環境にできたリポジトリをローカルリポジトリと呼びます。リモートのmainブランチにあったファイルやディレクトリと、Gitのデータも複製されます。

たぶん、VScode の Git の拡張機能のインストールが終わったと思います。このリポジトリをクローンしてみましょう。

* VScode で clone する手順

ctr + p を押してコマンドパレットを表示。(Mac は多分 Command + p)

コマンドパレットに `> git clone` と入力し、`git クローン`を選択。 github から複製を選ぶ。Github にログインしていない場合はログインする。権限はすべて許可してください。

![gir clone](./markDownResource/clone1.png)

`tuatmcc/mcc-c-git-lec`を選択してください。

![select repository](./markDownResource/selectrepo.png)

クローンする場所は好きな場所にクローンしてください。クローンしたら開いてください。

`README.md` を開いてください。この資料が見れると思います。


## commit (コミット)

コミットとは、ファイルやディレクトリの追加・変更・削除などの**変更履歴をリポジトリに記録すること**です。コミットすると、その時点のファイルやディレクトリの状態が記録されます。コミットするときは、どのような追加・変更・削除を行ったかを示すコミットメッセージを一言程度で書きます。

ここで、このリポジトリのコミット履歴を見てみましょう。下の方の GitGraph のアイコンを押してください。コミット履歴のグラフのタブが開きます。下の画像はちょっと前のやつなので、みなさんが見ているものとは異なると思います。

![commit](./markDownResource/commit1.png)

１つ１つがコミット履歴です。誰が、いつ、何を編集したのかわかると思います。ためにし過去のコミット履歴を１つ選択してみてください。コミットの詳しい内容が書いてあります。

![commit details](./markDownResource/commit2.png)

左に書いてあるファイルを選択してみてください(以下の画像ならREADME.mdがわかりやすい)。すると、そのコミットでのそのファイルの差分が見れます。左側に変更前、右側に変更後があります。ソースコードなどのテキストファイルでは、そのコミットで削除された部分は変更前のところに赤くハイライトされます。追加された部分は変更後のところに緑でハイライトされます。

![commit diff](./markDownResource/commit3.png)

## branch (ブランチ)

ブランチとは、**変更履歴を記録していく系統**です。基本的に１つの機能につき、１つのブランチをつ作ります。以下に MCC のホームページのブランチを示します。ローカルにしかないブランチをローカルブランチ、リモートにしかないブランチをリモートブランチと呼びます。

![sample graph](./markDownResource/sample-graph1.png)

ブランチ名が書いてあるコミットが、ローカルブランチでの最新のコミットです。ブランチ名に origin がついているコミットは、リモートブランチでの最新のコミットです。あとで実際に触れながら詳しく説明します。

## checkout (チェックアウト)

チェックアウトとは、**作業するブランチを切り替えること**です。ブランチを切り替えると、そのブランチの最新のコミットの状態になります。

## merge (マージ)

マージとは、**ブランチの変更履歴を統合すること**です。ブランチを切り替えるときに、そのブランチの変更履歴を現在のブランチに統合することができます。

## pull (プル)

プルとは、**リモートリポジトリの変更履歴を取得すること**です。リモートリポジトリの変更履歴を取得すると、ローカルリポジトリの変更履歴にも反映されます。

## push (プッシュ)

プッシュとは、**ローカルリポジトリの変更履歴をリモートリポジトリに反映すること**です。ローカルリポジトリの変更履歴をリモートリポジトリに反映すると、リモートリポジトリの変更履歴にも反映されます。

## commit, branch, checkout, merge, pull, push を試してみよう

現在のブランチは左下で確認できます。現在は `main` ブランチになっているはずです。確認してください。

![checkout](./markDownResource/checkout2.png)

* `branch-practice` にチェックアウトする

`branch-practice` ブランチにチェックアウト (ブランチの切り替え) をします。 Git Graph から、`branch-practice` をダブルクリックして下さい。それで、`branch-practice` ブランチにチェックアウトできます。

![checkout](./markDownResource/checkout1.png)

チェックアウト後は `branch-practice` になっているはずです。確認してください。

![checkout](./markDownResource/checkout3.png)

* my-branch を作成する

MCC の Discord の自分の名前の Branch を作ります。 `branch-practice origin` を右クリックし、 `Create Branch` を選択してください。

![create branch](./markDownResource/selectbranch.png)

ブランチ名は MCC の Discord の自分の名前にして、 `Create Branch` してください。

![create branch](./markDownResource/createbranch.png)

自分の名前のブランチができたらこのようになります。

![create branch](./markDownResource/createbranch2.png)

自分の名前のブランチをダブルクリックして、チェックアウトしてください。チェックアウトしたら、ちゃんと今開いているブランチが自分の名前のブランチか確認してください。

![create branch](./markDownResource/createbranch3.png)

![create branch](./markDownResource/createbranch4.png)

先程作成した自分の名前のブランチには `origin` がついていません。これは、自分の名前のブランチはまだリモートに存在しないからです。ローカルブランチしか存在しません。

* コミットする

自分の名前のブランチにチェックアウトができていたら、 branch-practice ディレクトリの中に `自分の名前.txt` というファイルを作成してください。中身は何でもいいです。

![create mytext](./markDownResource/createmytext.png)

コミットをする前にステージします。ソースの管理から、 `自分の名前.txt` をカーソルを合わせると現れる + を押してステージしてください。

リポジトリ内のファイルを変更してコミットする際、コミットするファイルを選べます。選んだファイルがステージされ、ステージされたファイルのみコミットされます。特定のファイルだけ別のコミットにしたいときや、コミットしたくないファイルがあるときなどにこの機能は役立ちます。

![stage](./markDownResource/stage.png)

ステージしたらメッセージを入力してください。ここではわかりやすく `commit 自分の名前` と入力してください。メッセージを入力したら Ctrl+Enter 、 (MacはたぶんCommand+Enter) もしくは `✓コミット` をクリックしてコミットできます。

![commit](./markDownResource/commit.png)

コミットしたら Git Graph から自分の名前のブランチにコミットが反映されていることを確認してください。また、メッセージも反映できているか確認してください。

![commited](./markDownResource/commited.png)

* マージする


