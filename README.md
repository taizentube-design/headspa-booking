# ヘッドスパ予約・紹介サイト

関東（東京）のヘッドスパを地域から探せる紹介サイトの MVP です。

## ブラウザで見る（GitHub Pages）

このリポジトリを **Public** にし、GitHub Pages を有効にすると、次の URL でサイトが表示されます。

**https://&lt;あなたのユーザー名&gt;.github.io/headspa-booking/mvp/**

### GitHub Pages の有効化手順

1. リポジトリの **Settings** → **Pages**
2. **Source** で **Deploy from a branch** を選択
3. **Branch**: `main`、**Folder**: **/ (root)** → **Save**
4. 1〜2分待つとサイトが公開されます

## 構成

- `mvp/` — トップ・東京一覧・店舗詳細（HTML + JSON 駆動）
- `data/stores.json` — 店舗データ（追加・編集はここだけ）

店舗の変更は `data/stores.json` を編集するだけで反映されます。
