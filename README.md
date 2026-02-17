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

---

## コミットとプッシュの手順（サイトを更新するとき）

このリポジトリは **ai-workspace の外で独立した Git リポジトリ** になっています。変更を GitHub に反映してサイトを更新する手順です。

### 1. ターミナルで headspa-booking フォルダへ移動

```bash
cd /Users/k/Desktop/ai-workspace/headspa-booking
```

### 2. 変更状況を確認

```bash
git status
```

（変更したファイルの一覧が表示されます）

### 3. 変更をすべてステージする

```bash
git add .
```

### 4. コミット（変更に名前をつけて記録する）

```bash
git commit -m "渋谷の店舗を追加"
```

※ `"渋谷の店舗を追加"` の部分は、今回の変更内容に合わせて自由に変えてOKです（例：`"店舗データ更新"`）。

### 5. プッシュ（GitHub に送る）

```bash
git push origin main
```

- 初めてプッシュする場合や、GitHub の認証を求められた場合は、**ユーザー名** と **パスワード** を入力します。  
  パスワードには **Personal Access Token（PAT）** を使います（通常のログイン用パスワードでは不可）。  
  → [GitHub: 個人用アクセストークン](https://github.com/settings/tokens) で「Generate new token」から発行できます。
- 成功すると `main -> main` のような表示が出て、数分後に GitHub Actions が動き、サイトが更新されます。

### まとめ（コピペ用）

```bash
cd /Users/k/Desktop/ai-workspace/headspa-booking
git add .
git commit -m "渋谷の店舗を追加"
git push origin main
```

※ **1行ずつ実行しても、上記4行をまとめて貼り付けて一気に実行してもOK** です。ターミナルは貼り付けた行を上から順に実行します。

---

## プッシュしたのにサイトに反映されないとき

**プッシュは成功している場合**（`main -> main` と表示されていればOK）、以下を順に確認してください。

### 1. GitHub Actions が成功しているか

1. ブラウザで **https://github.com/taizentube-design/headspa-booking** を開く  
2. 上部の **「Actions」** タブをクリック  
3. 一番上にある「Deploy to GitHub Pages」の実行が **緑の✓（成功）** になっているか確認  

- **失敗（赤い×）になっている場合**  
  → その実行を開き、どのステップで失敗したか確認する。よくあるのは「Settings → Pages → Source」が **GitHub Actions** になっていないことです。  
- **成功している場合**  
  → デプロイは完了しているので、次の 2 に進む。

### 2. Pages の公開元が「GitHub Actions」か

1. リポジトリの **Settings** → 左の **Pages**  
2. **Build and deployment** の **Source** が **「GitHub Actions」** になっているか確認  

- 「Deploy from a branch」のままになっていると、`main` へのプッシュではサイトが更新されません。**Source を「GitHub Actions」に変更**して保存する。

### 3. ブラウザのキャッシュ

- **強制再読み込み**：Mac は **Cmd + Shift + R**、Windows は **Ctrl + Shift + R**  
- または **シークレット（プライベート）ウィンドウ**で開き直す  
- **別のブラウザ**で開いてみる  

### 4. 見ているURL

- 正しいURL：**https://taizentube-design.github.io/headspa-booking/**  
- トップは自動で `mvp/` に飛びます。東京一覧は「東京」を押した先のページです。
