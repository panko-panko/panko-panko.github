# panko-panko.github

簡単な静的ページのサンプルです。ローカルでの確認方法、編集手順、Git 操作、そして簡易的な公開（GitHub Pages）までの流れをまとめています。

## ローカルで確認する（初心者向け）

1. リポジトリのルートフォルダに移動します（例: `c:\Users\kaise\panko-panko.github`）。
2. `index.html` をダブルクリックしてブラウザで開くか、PowerShell で次を実行します：

```powershell
Start-Process .\index.html
```

3. ブラウザでページが開き、見出しやボタン、画像が表示されることを確認します。

> 補足: 外部スクリプトや fetch を使う場合はファイルプロトコル（file://）だと動作しないことがあるので、その場合はローカルサーバー（次節）を使ってください。

## ローカルサーバー（オプション）

簡単な HTTP サーバーを立てると、より本番に近い挙動を確認できます。Python がインストールされていれば：

```powershell
python -m http.server 8000
# ブラウザで http://localhost:8000 を開く
```

または VS Code の拡張「Live Server」を使うと自動リロードが効いて便利です。

## 編集して確認する手順

1. VS Code 等のエディタで `index.html`, `index.css`, `index.js` を開く。
2. 変更を保存してブラウザをリロード（F5）すると反映されます。
3. ブラウザの DevTools（F12）を使って Console / Network / Elements を確認するとトラブルシュートが楽になります。

## Git の基本（変更を記録して共有する）

よく使うコマンドの例：

```powershell
git status
git add .
git commit -m "Update: 説明的なメッセージ"
git push
```

初めて push する場合は、リモートの設定（`git remote add origin <repo-url>`）や認証が必要です。必要なら手順を追って案内します。

## GitHub Pages で公開する（数分でできる簡易手順）

1. GitHub のリポジトリページを開く。
2. `Settings` → `Pages`（または `Pages` セクション）を開く。
3. `Branch` に `main`（または `gh-pages`）を選び、`/ (root)` を指定して `Save`。
4. 数分で `https://<username>.github.io/<repo>/` のような URL が発行されます。

注意: 公開したくないファイルや秘密情報はリポジトリに入れないでください。

## トラブルシュートよくある問題
- 画像が表示されない → `src` のパスが正しいか、Network タブで 404 を確認
- JS が動かない → Console にエラーが出ていないか確認
- 相対パスの問題 → ローカルサーバーで動作を確認

---

必要ならこの README にさらに「コマンドのスクリーンショット」や「よくあるエラーの例」を追加します。README を更新したら Git のコミットも行いますか？
