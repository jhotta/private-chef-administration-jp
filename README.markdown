# Private Chef Administration Guide

<!-- This repository has the source material for the Private Chef Administration guide. -->
このリポジとリーには、「Private Chef 管理ガイド」関するコードが記述されています。

<!-- ## Prerequisites -->
事前準備
<!--
To use this documentation, you'll need to have [Sphinx](http://sphinx.pocoo.org) installed,
along with [Pygments](http://pygments.org) for syntax highlighting. If you want to generate
PDF documentation, you'll also need to have a version of [LaTeX](http://www.latex-project.org/)
installed (specifically latex2pdf).
-->

このドキュメントを使うには、[Sphinx](http://sphinx.pocoo.org)とシンタックスのハイライトの為の[Pygments](http://pygments.org)のインストールが必要です。
更に、PDFを生成するなら[LaTeX](http://www.latex-project.org/)(特にlatex2pdf)のインストールが必要です。  

<!-- ## Installation -->
##インストール

```bash
    easy_install Pygments
    easy_install sphinx
```

<!-- ## Build -->
##ビルド

<!-- To build the documentation: -->
このドキュメントをビルドするには:

```bash
    export LC_ALL=en_US.UTF
    export LANG=en_US.UTF-8
    make html
```

<!-- Will generate HTML output in build/html/index.html. -->
HTMLのファイルを/build/html/のディレクトリ以下に作成します。

<!-- ##Run: -->
##実行

```bash
    make help
```

<!-- For alternative formats. -->
詳細の表示に関しては上記コマンドを実行してください。   

## Publish

Use 'make upload' to upload to s3. Requires that you have Opscode internal credentials configured for s3cmd.

<!-- ## OSX Instructions -->
##OSXへのインストル

<!-- ### Using Homebrew Python and avoiding permission issues -->
### HomebrewでPythonをインストール

```bash
    brew install python
```
<!--
Now add the following to your PATH using the shell initialization
script that makes sense for your environment:
-->

shellの初期化の部分で次のPATHを追加します。
環境に合わせてbashのexprotの部分を書き換えます:

```bash
   export PATH=/usr/local/share/pythno:$PATH
```
<!--
You can now call `easy_install` directly with no sudo and then follow
the make instructions.
-->

この場合sudoを使わずに`easy_install`を実行することができます。
そしてmake時の指示に従って下さい。

<!-- ### Using Python shipped with OSX -->
###OSX純正のPythonを使い場合の補足

<!-- A few minor nits for installing on OSX.　-->
OSXにインストールするための作業。

```bash
    sudo easy_install Pygments
    sudo easy_install sphinx
```

You may have issues with ownership of `/Library/Python/2.7/site-packages/` after you build Pygments and sphinx. You can either change the ownership with:

```bash
    sudo chown YOURUSER -R /Library/Python/2.7/site-packages
```

or make them world-executable with

```bash
    sudo chmod -R 755 /Library/Python/2.7/site-packages
```

You can then use the `make` commands as previously documented.

iPad
----

If you want iPad-readable docs, take the output of

```bash
    make epub
```

and copy the `build/epub/PrivateChefGuide.epub` to iTunes and sync it into the iBooks app.
