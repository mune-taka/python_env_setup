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
pipを利用した基本的なインストール方法は以下のコマンド
```
コマンドプロンプトを起動
py -m pip install [package] --proxy="XXXX"
```
社内のネットワークはプロキシサーバを使用しているため、プロキシを指定してインストールする。

とりあえず、pythonの統合開発環境(Integrated Development Environment: IDE)の一つであるjupyterlabをインストール
```
コマンドプロンプトを起動
py -m pip install jupyterlab --proxy="XXXX"
```

jupyterlabの起動テスト
```
コマンドプロンプトを起動
py -m jupyterlab
```

機械学習などではpython本体やライブラリのヴァージョン管理が重要で、ライブラリの依存関係によっては動かない場合が良くあります。
IDEは各自使いやすいものを用意すればおｋですが、今回の実践ではGpyOptというベイズ最適化用のライブラリを使うので、GpyOptが動く環境構築をお願いします。（今後いろんなライブラリを使いたいので、anaconda環境はお勧めしない。）


# pythonのカーネル追加
上述の通り、python本体のヴァージョンによっては環境構築できないライブラリがままあります。
インストールしたなりのpythonのバージョンでは使えなくなった機能があるため、古いバージョンのpythonをjupyterlab上で使えるようにする。






