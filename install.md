# このメモ帳での作業の流れ
1. python(適当なヴァージョン)のインストール
2. jupyterlab(統合開発環境)のインストール
3. python(任意のヴァージョン)のインストールとjupyterlabへのカーネル追加
4. python(任意のヴァージョン)へのライブラリ追加

最初から任意のヴァージョンのpythonで環境構築すればおｋなのですが、ヴァージョン管理の方法も込みで環境構築方法について紹介する。
とりあえずはこれで動くはず・・。

# pythonをインストール
既にインストール済みの場合不要。環境汚したくない場合は仮想環境で。
日本語情報サイト：https://www.python.jp/ 
本家と.exeファイルのダウンロードはこっち：https://www.python.org/
とりあえず最新版でおｋ。
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
(プロキシのパスを指定するやり方もあるがうまくいかなかった。)

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
IDEは各自使いやすいものを用意すればおｋですが、今回の実践ではGpyOptというベイズ最適化用のライブラリを使うので、GpyOptが動く環境構築をお願いします。（下記は一例）
（ベイズ最適化自体はGpyOptでなくともsklernでもpytourchでもできるらしいが、GpyOptのネット記事が一番分かりやすかった）

# jupyterlabに別ヴァージョンのpythonカーネル追加
上述の通り、python本体のヴァージョンによっては環境構築できないライブラリがままあります。
インストールしたなりのpythonのバージョンでは使えなくなった機能があるため、古いバージョンのpythonをjupyterlab上で使えるようにする。
python3.6.8をダウンロード: https://www.python.org/downloads/release/python-368/
デフォルトのインストール先は：C:\Users\user\AppData\Local\Programs\Python
python3.6.8の実行ファイルを指定してipykernelをpip installする。
```
コマンドプロンプトを起動
C:\Users\user\AppData\Local\Programs\Python\Python36\python.exe -m pip install ipykernel --proxy="XXXX"
```
jupyterにpython3.6.8を追加する。
```
コマンドプロンプトを起動
C:\Users\user\AppData\Local\Programs\Python\Python36\python.exe -m ipykernel install --user --name Python368
```
jupyterlabでカーネルを切り替えられるようになる

# pythonのヴァージョン指定してライブラリを追加
python3.6.8にベイズ最適化に必要なライブラリをインストール
```
コマンドプロンプトを起動
C:\Users\user\AppData\Local\Programs\Python\Python36\python.exe -m pip install Gpy --proxy="XXXX"
C:\Users\user\AppData\Local\Programs\Python\Python36\python.exe -m pip install gpyopt --proxy="XXXX"
C:\Users\user\AppData\Local\Programs\Python\Python36\python.exe -m pip install numpy --proxy="XXXX"
C:\Users\user\AppData\Local\Programs\Python\Python36\python.exe -m pip install scipy --proxy="XXXX"
C:\Users\user\AppData\Local\Programs\Python\Python36\python.exe -m pip install pandas --proxy="XXXX"
C:\Users\user\AppData\Local\Programs\Python\Python36\python.exe -m pip install scikit-learn --proxy="XXXX"
C:\Users\user\AppData\Local\Programs\Python\Python36\python.exe -m pip install Matplotlib --proxy="XXXX"
```
pip listでライブラリの確認
