# Mil Palavras

頻出ポルトガル語5000語 + IT用語300語を対象にした単語クイズアプリ（React + Vite）。[vocabulario-frequente/](../vocabulario-frequente/)の全5300語をもとにしている。

公開URL: [https://portuguese.innospot.net](https://portuguese.innospot.net)

- 意味↔単語の4択クイズ
- Leitner box方式の間隔反復（`localStorage`に進捗を保存）
- Web Speech APIによる発音読み上げ（対応ブラウザのみ）

## 開発

```bash
npm install
npm run dev
```

## ビルド

```bash
npm run build
```

`dist/` に静的ファイルが出力される。

## デプロイ（Cloudflare Workers、Git連携）

Cloudflare Dashboard → Workers & Pages → Create application → Connect to Git でこのリポジトリを接続し、以下を設定する。

- Build command: `npm run build`
- Deploy command: `npx wrangler deploy`
- Root directory: `/mil-palavras`
- Production branch: `main`

`main`ブランチへのpushで自動的に再ビルド・再デプロイされる。`wrangler.toml`の`name`はCloudflare側のプロジェクト名（現在は`portuguese`）と一致させる必要がある。
