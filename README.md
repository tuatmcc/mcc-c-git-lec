# MCC Git-C 言語講座

今回は Git を使って C言語 でリバーシプログラムを作ります。

## Git の環境構築

vscode の拡張昨日から検索欄に`git`と入れ、 Git Graph 、 Git History 、 GitLens の3つをインストールしてください。

git graph はいらない？

![git検索](./markDownResource/git1.png)

インストールしている間に Git の概要を話したいと思います。

## Git とは

Git とは、ソースコードなどの変更履歴を記録・追跡するためのバージョン管理システムです。Git を使うことで、誰が、いつ、どのような変更を行ったかを記録することができます。

覚えてほしい単語

```
repository
- local repository
- remote repository
clone
branch
- local branch
- remote branch
commit
push
pull
marge
Github
```

## repository (リポジトリ)

リポジトリとは、バージョン管理システムで管理したい範囲のファイルやディレクトリと、それらの履歴データなどをまとめたものです。基本的に、1つのアプリケーションを作るときなど、1つのプロジェクトに対して1つのリポジトリを作成します。

リポジトリはローカルリポジトリとリモートリポジトリの2種類があります。サーバー上(リモート)にあるリポジトリをリモートリポジトリと呼び、自分のパソコン(ローカル)にあるリポジトリをローカルリポジトリと呼びます。

## clone (クローン)

クローンとは、リモートリポジトリをローカル環境に複製することです。複製してローカル環境にできたリポジトリをローカルリポジトリと呼びます。リモートのmainブランチにあったファイルやディレクトリと、Gitのデータも複製されます。

たぶん、VScode の Git の拡張機能のインストールが終わったと思います。このリポジトリをクローンしてみましょう。

* VScode で clone する手順

ctr + p を押してコマンドパレットを表示。(Mac は多分 Command + p)

コマンドパレットに`> git clone` と入力し、`git クローン`を選択。 github から複製を選ぶ。Github にログインしていない場合はログインする。権限はすべて許可してください。

![gir clone](./markDownResource/clone1.png)

`tuatmcc/mcc-c-git-lec`を選択してください。

![select repository](./markDownResource/selectrepo.png)

クローンする場所は好きな場所にクローンしてください。クローンしたら開いてください。

`README.md` を開いてください。この資料が見れると思います。
