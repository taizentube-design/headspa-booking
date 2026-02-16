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

## 3. GitHub Pages を有効にする（Actions を使う場合・推奨）

1. リポジトリの **Settings** → **Pages**
2. **Build and deployment** の **Source** で **「GitHub Actions」** を選ぶ（「Deploy from a branch」ではない）
3. 何も Save ボタンがなくても、Source を選んだ時点で有効になる
4. リポジトリの **Actions** タブを開き、「Deploy to GitHub Pages」ワークフローが実行されるのを待つ（緑のチェックになるまで 1〜2 分）
5. 完了後、次の URL でサイトが表示されます：
   **https://taizentube-design.github.io/headspa-booking/**

※ まだ 404 のときは、**Settings → Pages** で Source が「GitHub Actions」になっているか確認し、**Actions** タブでワークフローが成功（緑✓）か確認してください。
