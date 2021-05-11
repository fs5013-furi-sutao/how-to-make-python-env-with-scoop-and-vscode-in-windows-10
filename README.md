# VWindows 10 で Scoop と VSCode を使って Python のコーディング環境を作る方法

## 実行環境

Windows 10 Home 20H2

## 手順

1. Scoop のインストール
2. 最新 Python のインストール
3. VSCode ポータブル版のインストール
4. Python 拡張のインストール
5. venv の作成
6. サンプルプログラムの作成
7. サンプルプログラムの実行

## 1. Scoop のインストール

Scoop.sh のページに従って、Scoop をインストールする。

## 2. 最新 Python のインストール

次のコマンドで最新の Python をインストールする。

``` console
scoop install python
```

Python がインストールできたか、確認する。

``` console
python --version
```

実行結果例：
```
Python 3.9.5
```

```  console
python --version
```

実行結果例：
```
Python 3.9.5
```

## 3. VSCode ポータブル版のインストール

まずは最新 Python のマニフェストがある extras バケットを追加する。

``` console 
scoop bucket add extras
```

次に VSCode のポータブル版をインストールする。

``` console
scoop install vscode-portable
```

## 4. Python 拡張のインストール

VSCode を開いて、拡張機能のサイドバーを開いて、python と検索する。

検索結果の一番目に拡張機能 `ms-python.python` が表示されるので、この拡張機能をインストールする。

## 5. venv の作成

任意の場所にプロジェクトフォルダを作る。

``` console 
mkdir test_project
```

``` console
cd ./test_project
```

venv 仮想環境を作る。

``` console
python -m venv project_env
```

## 6. サンプルプログラムの作成

以下のサンプルプログラムを作成する。

sample.py:
``` python
from mypackage import aaa

print(aaa.bbb)
```

mypackage/aaa.py:
``` python
bbb = 234
```

## 7. サンプルプログラムの実行

VSCode で Terminal を開く。

そして、Python の仮想環境をアクティベートさせる。

``` console
./project_env/Scripts/Activate.ps1
```

実行結果例：
```
(project_env) PS C:\Users\N_hashimoto\Desktop\test_project>
```

サンプルプログラムを実行させる。

``` console
python ./sample.py
```

実行結果例：
``` 
234
```

ディアクティベートさせる。

``` console
deactivate
```

実行結果例：
``` 
PS C:\Users\N_hashimoto\Desktop\test_project>
```
