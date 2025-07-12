---
title: Gatsby 入門ガイド：高速でモダンな Web サイトを構築しよう
description: Gatsbyで作ろうというものです。
pubDate: 2025/07/12
image:
  url: "https://docs.astro.build/default-og-image.png"
  alt: "惑星と星のイラストの中に「astro」という単語があります。"
category:
  name: Gatsby
  slug: gatsby
tags: [{ name: Gatsby, slug: gatsby }, { name: Javascript, slug: javascript }]
---

## はじめに

Gatsby（ギャツビー）は、React をベースにした静的サイトジェネレーターです。  
静的サイトとはいえ、Gatsby を使えば SPA（Single Page Application）と同等の体験を提供することができます。

この記事では、Gatsby の基本的な特徴からセットアップ方法、そして応用的な使い方まで幅広く解説します。

---

## Gatsby とは？

Gatsby は、React で構築された静的サイトジェネレーターです。以下のような特徴を持っています：

- **高速な表示速度**  
  ビルド時にすべての HTML を生成するため、表示が非常に速い。

- **React ベース**  
  コンポーネント思考で UI を構築できる。

- **GraphQL によるデータ取得**  
  CMS や Markdown など、さまざまなソースからデータを取得できる。

- **PWA 対応**  
  オフラインでも動作可能な Web アプリケーションを構築できる。

---

## Gatsby の主な用途

Gatsby は以下のようなプロジェクトに最適です：

- ブログサイト
- ポートフォリオ
- 企業サイト
- ドキュメントサイト
- Headless CMS と連携したメディアサイト

---

## セットアップ手順

### 1. Node.js をインストール

Gatsby は Node.js で動作します。まずは Node.js をインストールしてください（すでにインストール済みならスキップして OK です）。

```bash
node -v
npm -v
```

---

### 2. Gatsby CLI のインストール

Gatsby 専用の CLI ツールをインストールします。

```bash
npm install -g gatsby-cli
```

---

### 3. プロジェクトの作成

```bash
gatsby new my-gatsby-site
cd my-gatsby-site
gatsby develop
```

これで、`http://localhost:8000` にアクセスすればローカル開発環境が立ち上がります。

---

## フォルダ構成の基本

```
my-gatsby-site/
├── src/
│   ├── pages/       ← ページコンポーネント
│   ├── components/  ← 再利用可能な部品
│   └── images/      ← 画像ファイル
├── gatsby-config.js ← 設定ファイル
├── gatsby-node.js   ← 動的ページ生成用
└── package.json
```

---

## ページの作り方

`src/pages`ディレクトリにファイルを置くだけで、自動的にページとして認識されます。

例：`src/pages/about.js`

```jsx
import React from "react";

const AboutPage = () => (
  <main>
    <h1>このサイトについて</h1>
    <p>これはGatsbyで作られた静的サイトです。</p>
  </main>
);

export default AboutPage;
```

---

## GraphQL の利用

Gatsby では GraphQL を使ってデータを取得します。Markdown、CMS（Contentful, MicroCMS など）、画像など、さまざまなソースにアクセス可能です。

例：Markdown のデータを取得

```graphql
query {
  allMarkdownRemark {
    nodes {
      frontmatter {
        title
      }
      excerpt
    }
  }
}
```

---

## プラグインの活用

Gatsby には豊富なプラグインがあります。たとえば、以下のようなプラグインが人気です：

- `gatsby-plugin-image`: 画像最適化1
- `gatsby-plugin-mdx`: MDX サポート
- `gatsby-plugin-sharp`: 画像処理
- `gatsby-source-filesystem`: ローカルファイルを GraphQL に取り込む
- `gatsby-plugin-sitemap`: サイトマップ生成

---

## デプロイ：Netlify への公開

Netlify を使えば、Gatsby サイトを簡単にデプロイできます。

1. GitHub にリポジトリをプッシュ
2. [Netlify](https://www.netlify.com/) にログイン
3. 新しいサイトを GitHub からインポート
4. ビルドコマンドを設定：`gatsby build`
5. 公開！

---

## Gatsby のメリットと注意点

### メリット

- 表示が超高速
- SEO に強い
- ビルド時にコンテンツをすべて生成できるため、セキュリティリスクが低い

### 注意点

- サイト規模が大きいとビルド時間が長くなる
- サーバー側でリアルタイムにデータを更新するのには不向き（必要なら SSR 機能を検討）

---

## まとめ

Gatsby は、React の知識があればすぐに始められる強力なツールです。静的サイトとは思えないほど高機能で、モダンな Web 開発に最適です。

ブログ、ポートフォリオ、企業サイトなど、さまざまな用途に対応できるため、ぜひ一度 Gatsby を試してみてください！

---

## 参考リンク

- [Gatsby 公式サイト](https://www.gatsbyjs.com/)
- [Gatsby のスターター一覧](https://www.gatsbyjs.com/starters/)
- [Gatsby Plugin Library](https://www.gatsbyjs.com/plugins/)
