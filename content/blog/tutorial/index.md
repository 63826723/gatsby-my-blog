---
title: Gatsbyを使ったブログ作成
date: "2020-09-17T01:00:00.000Z"
description: 実際にGatsbyを使ってブログのベースを作る流れについて。GitHubやNetlifyを使って実際に世の中に公開するところまで説明します。
---
### 事前準備

- GitHubのアカウントを作成 https://github.com
  ※GitHub: ソースコード保存、公開できるウェブサービス
- NetlifyとGitHubのアカウントを連携 https://www.netlify.com
  ※Netlify: 静的ホスティングサービス



### Gatsby環境構築

Gatsbyをローカルで動かすためにインストールするもの

- Node.js(2020-09-16現在、最新版は14.11.0) https://nodejs.org/en/
- yarn https://classic.yarnpkg.com/ja/
  ※Gatsbyプラグインをインストールするのにnpmも使用できるが今回はyarnを使う
- Git
- gatsby-cli

```bash
npm install --global gatsby-cli
```



### Gatsbyサイトベース作成

1. 任意の場所で以下のコマンドを実行(gatsby-siteは任意のプロジェクト名)
   ※https://www.gatsbyjs.com/starters/?v=2 から初期デザインを選ぶことができる。その場合は4番目の引数にデザインソースを指定する

   ```bash
   gatsby new <gatsby-site>
   ```

2. プロジェクトフォルダに移って、開発サーバーを実行

   ```bash
   cd gatsby-site
   gatsby develop
   ```

3. ブラウザでlocalhost:8000にアクセス



### GitHubとNetlifyを連携してGatsbyアプリをデプロイする

サンプルプログラム(今見ているサイト)をGitHubで公開しているのでそれを使って説明する。

プログラム: https://github.com/63826723/gatsby-my-blog.git

1. 任意の場所にプログラムをcloneする

   ```bash
   git clone https://github.com/63826723/gatsby-my-blog.git
   ```

2. ローカルでcloneしたプログラムが動くことを確認する

   ```bash
   cd <任意の場所>
   yarn install
   gatsby develop
   ```

3. ソースコードを適宜変更してGitHubへpushする

   ```bash
   git push
   ```

4. Netlifyが既にGitHubと連携していれば、gitへの着信があったタイミングでNetlifyが自動的にビルドを開始してデプロイされる



##### サンプルプログラムの構成

- content/blog配下に任意のフォルダを作成
  ※フォルダ名がサイトの記事のURLになる
- そのフォルダの配下にindex.mdファイルを作成
  ※ファイルの内容がブログの記事になる
- YAML Front-matter(このマークダウンの先頭にある記述)で、ブログのタイトルや概要、作成日時を記述



#### 神田君の昼ご飯

- 卵焼き
- 魚の塩焼き
- 肉の炒め物
- 