---
title: SPA? SSR? JAMstack?
date: "2020-09-16T23:30:00.000Z"
description: Webアプリケーションをブラウザで表示するための仕組みをまとめました。Gatsbyで使われているJAMstackというアーキテクチャについても少し。

---

### ウェブサイトが表示される仕組み

https://qiita.com/amakawa_/items/e7d0720e1ab8632769bf

↑このサイトが図解で分かりやすい。以下、抜粋。

#### 一般的なウェブサイト

クライアントからのリクエストごとに、サーバーでHTMLを生成してレスポンスを返す。更新が不要な部分も都度レスポンスに含まれるので処理に時間がかかる。

#### SPA(Single Page Application)

ページ遷移なしにコンテンツを切り替えるアプリケーション。初回の読み込みに時間がかかるが、以降は更新が必要なデータのみ処理されるので早い。

サイト例: https://bnature-hawaii.com/

#### SSR(Server Side Rendering)

※ここではJavaScriptでHTML生成するものを指すこととする。

SPAはHTMLの生成をクライアントで行うが、SSRではサーバー側で生成するのでページ表示が早い。

サイト例: https://studio.design/ja



### SSGとは?

静的サイトジェネレーター(Static Site Generator)のこと。

https://dyno.design/articles/what-is-static-site-generator/

GatsbyはReact向けのSSG。Reactベースでページを実装し、ウェブサーバーにデプロイする前にビルドを行い、事前にHTMLファイルを作成してサーバーに配置する。ビルドに時間はかかるが、サイト表示時にプログラムの実行がないので表示が早い。



### JAMstackとは?

JAMstackのJAMは、JavaScript, APIs, Markupの頭文字。JavaScriptでAPIをたたいてMarkupを配信することを意味する。

https://microcms.io/blog/what-is-jamstack/

https://qiita.com/ozaki25/items/4075d03278d1fb51cc37

https://4rchiv3s.solit4ry.io/tech/marmalade/

https://employment.en-japan.com/engineerhub/entry/2019/12/10/103000

https://dyno.design/articles/what-is-jamstack/



### SSGのメリット/デメリット/使いどころ

WordPressなどのCMSと比べたメリット・デメリットについて。

https://dyno.design/articles/what-is-static-site-generator/

https://dyno.design/articles/jamstack-cms-pros-cons-comparison/

#### メリット

- セキュリティ
- パフォーマンス
- メンテナンス
- 本番サーバー
- コンテンツソース
- Markdown
- バックアップ
- SPA

#### デメリット

- プログラミング知識
- 動的・インタラクティブ機能
- ビルド時間
- 後方互換性

#### 使いどころ

- プログラマの個人ブログ
- 技術チームのブログ
- 更新頻度の低いサイト
- 高いパフォーマンスが求められるサイト