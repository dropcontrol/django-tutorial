# TL;DR

Laerning Django with Official Tutorial

# Day 1

## 前提

* pyenv, venv, あたりで環境構築する。venvを使う理由は https://qiita.com/toast-uz/items/f2df428f75b049b1d172 この辺りを読んで納得したところがある。

## 環境構築

の前にDjangoがRequirementしてるpythonのバージョンなどを確認 > https://docs.djangoproject.com/ja/3.1/faq/install/

* pythonのインストール
```
$ pyenv local 3.9.0
$ pyenv versions
  system
  3.6.8
  3.7.2
  3.8.2
* 3.9.0 (set by /Users/yamato/Src/django-tutorial/.python-version)
```

* venvで環境作り
```
$ python -V
Python 3.9.0
$ python -m venv django-tutorial
```

* アクティベーションを`source django-tutorial/bin/activate`で行う（抜けるには`deactivate`だけで良い）以下はアクティベーションした環境ないで行う。

* Djangoのインストール
```
$ python -m pip install Django
```

* pipのバージョンが古いぞ。というワーニングが出たので、それにも対応
```
$ python -m pip install --upgrade pip
```

* pythonの対話シェルを使ってDjangoの確認
```
$ python
Python 3.9.0 (default, Mar 11 2021, 16:15:44) 
[Clang 12.0.0 (clang-1200.0.32.29)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import django
>>> print(django.get_version())
3.1.7
```

* settings.pyのSECRET_KEYの外部ファイル化はここを参考にした > https://qiita.com/haessal/items/abaef7ee4fdbd3b218f5


## Day1：雑感（チュートリアル3まで終了）

* 理解しやすく大変シンプルに出来てる印象。VSCodeでKite使って書いてると保管機能がヤバイ。
* TIME_ZONEの設定でなぜか’Asia/Tokyo'ではmigrateがうまくいかず、'Japan'とするとうまくいく。後でもう一度確認。
* 管理画面を作ってくれるのだがMT3時代を思い出す感じのデザインでほっこりした。というのはともかく、これを自動で用意してくれるのは大変便利だと思う。ここにデザインやUIの機能を足していく、となると大変そうなのでそういうのが必要になったらそれは別途必要なものだけを作った方がいいのか、この管理画面を拡張した方がいいのかは要検討。Django使いの先人たちの事例を知りたいところ。
* プロジェクトとアプリ、という分け方は便利そう。機能を拡張していくときにアプリケーションを分けて作っていくことができるなら拡張しやすいのではないか。

と言った感じ。Day2に続く。