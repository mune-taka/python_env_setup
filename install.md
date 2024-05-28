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
最近のpythonはpip(python package index: pythonの便利機能をお手軽にインストールするためのユーティリティ)が付属されているらしいので不要。入ってなかったらインストールする。

# pipで主要なパッケージをインストール
とりあえずはpythonの統合開発環境の一つであるjupyterlabのインストール

```
コマンドプロンプトを起動
py -m pip install [package] --proxy="XXXX"
```

社内のネットワークはプロキシサーバを使用しているため、プロキシを指定してインストールする。

```
コマンドプロンプトを起動
py -m pip install jupyterlab --proxy="XXXX"
```

jupyterlabの起動テスト
```
コマンドプロンプトを起動
py -m jupyterlab
```

# pythonのカーネル追加

