# README

## セットアップ

サイト作成

```shell
hugo new site hugo-frances
```

レポジトリ初期化

```shell
cd hugo-frances
git init
echo '*.bak' >> .gitignore
echo '*~' >> .gitignore
echo '*.orig' >> .gitignore
echo 'public' >> .gitignore
```

テーマ設定

```shell
cd themes 
git submodule add git@github.com:mcrwfrd/hugo-frances-theme.git
```

サイト設定

```shell
cd hugo-frances
cp -pr ./themes/hugo-frances-theme/exampleSite/config.toml .
cp -pr ./themes/hugo-frances-theme/{content,data,layouts,static} .
```

layoutsのパスが絶対URLになっている箇所があるので修正

* layouts/_default/baseof.html
* layouts/partials/head.html
* layouts/partials/foot.html

config.toml

```toml
baseURL = "https://higebobo.github.io/hugo-frances/"
languageCode = "ja"
title = "Hugo Frances"
theme = "hugo-frances-theme"
publishDir = "docs"
...

```

> github pagesやnetlifyで使う場合はbaseURLのプロトコルはhttpsにすること

Githubレポジトリ作成後

```shell
git remote add origin git@github.com:higebobo/hugo-frances.git
cp somplace/{Makefile,deploy.sh} .
make deploy
```

Github>Settings>Gighub Pages>Source>master branch/docs folder

## 既存のレポジトリからクローンする場合

```shell
git clone git@github.com:higebobo/hugo-frances.git higebobo-frances
cd higebobo-frances
git submodule update --init --recursive
```

## 使い方

### 投稿

新規投稿

```shell
hugo new posts/hello.md
content/posts/hello.md created
```

編集

```shell
vi content/posts/hello.md
```

### ポートフォリオ

```shell
vi data/artworks.toml
```

## Link

* [Hugo Frances Theme \| Hugo Themes](https://themes.gohugo.io/hugo-frances-theme/)
