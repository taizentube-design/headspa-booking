# このリポジトリを GitHub に push する手順

## 1. GitHub で新規リポジトリを作る

1. https://github.com/new を開く
2. **Repository name** に `headspa-booking` と入力（ほかの名前でも可。その場合は以下のコマンドのリポジトリ名を合わせる）
3. **Public** を選択
4. **Add a README file** などにはチェックを入れず、**Create repository** をクリック

## 2. このフォルダから push する

ターミナルで以下を実行（`<ユーザー名>` はあなたの GitHub ユーザー名に置き換え）。

```bash
cd /Users/k/Desktop/ai-workspace/headspa-booking
git remote add origin https://github.com/taizentube-design/headspa-booking.git
git branch -M main
git push -u origin main
```

SSH を使う場合：

```bash
git remote add origin git@github.com:taizentube-design/headspa-booking.git
git push -u origin main
```

## 3. GitHub Pages を有効にする

1. リポジトリの **Settings** → **Pages**
2. **Source**: Deploy from a branch
3. **Branch**: main、**Folder**: / (root) → **Save**
4. 1〜2分待つと、次の URL でサイトが表示されます：
   **https://taizentube-design.github.io/headspa-booking/mvp/**
