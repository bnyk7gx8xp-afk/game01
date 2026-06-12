# 深夜の旧病院 〜脱出〜

スマホブラウザ向けのホラー脱出ゲーム。`index.html` 1ファイルだけで動作します(外部アセット・ビルド不要)。

🎧 音が出ます。イヤホン推奨。気になる場所をタップして調べ、アイテムと暗号を見つけて旧病院から脱出してください。エンディングは2種類。

## ローカルで遊ぶ

`index.html` をブラウザで開くだけです。

```sh
npx serve .   # または python3 -m http.server
```

## デモ公開(Cloudflare Pages)

GitHub Actions による自動デプロイを用意しています(`.github/workflows/deploy.yml`)。
リポジトリの **Settings → Secrets and variables → Actions** に以下を追加すると、push のたびに自動でデプロイされます。

| Secret | 内容 |
|---|---|
| `CLOUDFLARE_API_TOKEN` | Cloudflare ダッシュボード → My Profile → API Tokens で「Cloudflare Pages — Edit」権限のトークンを作成 |
| `CLOUDFLARE_ACCOUNT_ID` | Cloudflare ダッシュボード右側に表示される Account ID |

デプロイ先 URL: `https://kyu-byoin-escape.pages.dev`

手動でデプロイする場合:

```sh
npx wrangler login
npx wrangler pages project create kyu-byoin-escape --production-branch=main
npx wrangler pages deploy . --project-name=kyu-byoin-escape --branch=main
```
