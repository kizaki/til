# Gitとは
- 分散型バージョン管理ツール
- ファイルの状態を好きな時に変更履歴として保存可能
- つまり、一度編集したファイルを過去に戻したり、編集箇所の差分を表示できる

## git configコマンド
git configコマンドでGitの設定を行う<br />
最初にすることは、名前とメールアドレスの設定である

```
$ git config --global user.name "testuser"
$ git config --global user.email "testuser@example.com"
```

## git cloneコマンド
リモートリポジトリをローカルリポジトリに複製する
```
$ git clone {url}
```

## git initコマンド
ディレクトリにローカルリポジトリを作成する
```
$ git init
```

## git addコマンド
ワーキング・ツリーの中でコンテンツ（ファイルなど）を見つけてインデックスに追加する
```
$ git add {ファイル名}
```
ディレクトリ内の全てのファイルをインデックスに追加する場合
```
$ git add .
```

## git commitコマンド
インデックスに追加されたファイルをコミットする
```
$ git commit
```
コミットメッセージを同時に指定する場合（通常はこれ）
```
$ git commit -m "{message}"
```

## git statusコマンド
ワーキング・ツリーの状態を表示する
```
$ git status
```

## git logコマンド
コミット時のログを表示する
```
$ git log
```

リポジトリに履歴を視覚的に確認する
```
$ git log --graph
```

## git log --grep {検索文字列}
```
$ git log --grep "20210507"
```

## git diff {コミットID1} {コミットID2}
差分を比較したいコミットIDを指定する

## git diff {コミットID}
現在のブランチの状態から特定のコミットまでを比較する

## git pushコマンド
リモートリポジトリの履歴を更新する<br />
以下はローカルブランチ「main」を、リモートリポジトリ「main」上の同名のブランチに反映する
```
$ git push origin main
```
git pushを強制するオプション（--force）
```
$ git push --force origin main
```

## git remote add コマンド
リモートリポジトリを追加する<br />
慣習として{shortname}がoriginであるが、{url}の別名で付けてるだけなのでなんでもよい

```
$ git remote add {shortname} {url}
```
例としてkizakiというユーザーのアカウントに紐づくsampleというリモートリポジトリを作成する
```
$ git remote add origin git@github.com:kizaki/sample.git
```
## git remote get-urlコマンド
下記のコマンドで紐づけられているURLを取得できる

```
$ git remote get-url {shortname}
```
## git checkoutコマンド
下記のコマンドで変更を戻せる（addする前）

```
$ git checkout {filename}
```
下記コマンドで全ての変更を戻せる（addする前）

```
$ git checkout .
```

##　git resetコマンド
直前のコミットを取り消す

```
$ git rest --hard HEAD^
```

コミット後の変更を全て消す

```
$ git reset --hard HEAD
```

指定したコミットIDに戻す<br />
※ git logコマンドでコミットIDを検索できる

```
$ git reset --hard {コミットID}
```

トピックブランチの作業が完了し、mainブランチに取り込む
```
$ git merge --no-ff {ブランチ名}
```
手順
```
$ git checkout main
$ git merge --no-ff feature-A
```

## 参考URL
- [[git] 戻したい時よく使っているコマンドまとめ](https://qiita.com/rch1223/items/9377446c3d010d91399b "[git] 戻したい時よく使っているコマンドまとめ")
- [git mergeを使ってブランチをマージする方法](https://techacademy.jp/magazine/10264 "git mergeを使ってブランチをマージする方法")