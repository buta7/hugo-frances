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
```

config.toml

```toml
baseURL = "https://higebobo.github.io/hugo-frances/"
languageCode = "ja"
title = "Hugo Frances"
theme = "hugo-frances-theme"
publishDir = "docs"
```

> github pagesやnetlifyで使う場合はbaseURLのプロトコルはhttpsにすること

Githubレポジトリ作成後

```shell
git remote add origin git@github.com:higebobo/hugo-frances.git
cp somplace/{Makefile,deploy.sh} .
make deploy
```

Github>Settings>Gighub Pages>Source>master branch/docs folder

## 使い方

### 投稿

新規ポートフォリオ

```shell
hugo new blog/hello.md
content/blog/hello.md created
```

編集

```shell
vi content/blog/hello.md
```

## Link

* [Hugo Frances Theme \| Hugo Themes](https://themes.gohugo.io/hugo-frances-theme/)
