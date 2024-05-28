# pythonをインストール
日本語情報サイト：https://www.python.jp/ 
本家と.exeファイルのダウンロードはこっち：https://www.python.org/
インストール完了後、バージョンを確認する。

```
コマンドプロンプトを起動
py -V
Python X.X.X
```

# pipのインストール
最近のpythonはpip(python package index: pythonの便利機能をお手軽にインストールするためのユーティリティ)が付属されているらしい。

# pipで主要なパッケージをインストール
py -m pip install --proxy="XXXX" [package]
社内のネットワークはプロキシサーバを使用しているため、プロキシを指定してインストールする。

# pythonのカーネル追加
