# ヘッドスパ予約・紹介サイト

関東（東京）のヘッドスパを地域から探せる紹介サイトの MVP です。

## ブラウザで見る（GitHub Pages）

このリポジトリを **Public** にし、GitHub Pages を有効にすると、次の URL でサイトが表示されます。

**https://&lt;あなたのユーザー名&gt;.github.io/headspa-booking/mvp/**

### GitHub Pages の有効化手順

1. リポジトリの **Settings** → **Pages**
2. **Source** で **「GitHub Actions」** を選択（Deploy from a branch ではない）
3. このリポジトリには `.github/workflows/deploy-pages.yml` が入っており、push のたびに自動でデプロイされます
4. **Actions** タブで「Deploy to GitHub Pages」が成功（緑✓）になったら、1〜2分後にサイトが表示されます

## 構成

- `mvp/` — トップ・東京一覧・店舗詳細（HTML + JSON 駆動）
- `data/stores.json` — 店舗データ（追加・編集はここだけ）

店舗の変更は `data/stores.json` を編集するだけで反映されます。
