# Gitとは
- 分散型バージョン管理ツール
- ファイルの状態を好きな時に変更履歴として保存可能
- つまり、一度編集したファイルを過去に戻したり、編集箇所の差分を表示できる
```
$ git remote add [shortname] [url]
```
慣習として<shortname>がoriginであるが、<url>の別名で付けてるだけなのでなんでもよい

```
$ git remote get-url [shortname]
```
上記のコマンドで紐づけられているURLを取得できる

