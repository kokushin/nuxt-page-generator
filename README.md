# nuxt-page-generator

> jsonファイルからページを量産できるnuxtjsテンプレート

## 環境

- Node.js 12.14.0

## 依存モジュール

- dayjs
- node-sass
- sass-loader

## 実行

``` bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).

## Netlifyとの連携

1. https://www.netlify.com/ へアクセス
2. Repositoryを連携
3. Build command に `npm run generate` を指定
4. Publish directory に `dist` を指定
5. 変更をプッシュすると自動ビルド
6. netlifyで設定したドメインでホスティングされる

GitHub上から `db/blog.json` を変更すればノーコーディングで記事を量産できるよ！

## Todo

- ページャー機能
- 検索機能
- サイトマップ機能

## Licence

MIT Licence

(c) 2020 makery, inc.  
https://makery.co.jp
