# Mil Palavras

頻出ポルトガル語1〜1000位を対象にした単語クイズアプリ（React + Vite）。[vocabulario-frequente/](../vocabulario-frequente/)の上位1000語をもとにしている。

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

## Cloudflare Pagesへのデプロイ

### 方法A: ダッシュボードでGit連携（推奨）

1. Cloudflare Pagesのダッシュボードで「Create a project」→「Connect to Git」
2. このリポジトリを選択
3. ビルド設定:
   - Build command: `npm run build`
   - Build output directory: `mil-palavras/dist`
   - Root directory: `mil-palavras`
4. デプロイ後、`main`ブランチへのpushで自動的に再デプロイされる

### 方法B: Wrangler CLIで手動デプロイ

```bash
npm run build
npx wrangler login
npx wrangler pages deploy dist --project-name=mil-palavras
```
