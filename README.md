# solo-siege

1人用ソリティア「ソロ・シージ」。完全にクライアントサイド（vanilla JS + localStorage）で動く静的HTMLゲームです。サーバーやビルド処理は不要です。

## 中身

- `index.html` … ゲーム本体（このファイル1つで完結）
- `vercel.json` … Vercel用の設定（無くても動きますが、URLを綺麗にするために同梱）

## GitHubにアップロードする手順

1. GitHubで新しいリポジトリを作成（Public/Privateどちらでも可）
2. このZIPを展開し、中身（`index.html` と `vercel.json`）をリポジトリのルート直下に置く
3. コミットしてpush

```
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin <あなたのリポジトリのURL>
git push -u origin main
```

## Vercelで公開する手順

1. https://vercel.com にログイン（GitHubアカウントで連携可能）
2. 「Add New... > Project」から、上記でpushしたリポジトリをImport
3. Framework Presetは自動検出されない場合「Other」のままでOK（ビルドコマンドは不要）
4. 「Deploy」を押すだけで、`https://<プロジェクト名>.vercel.app` のようなURLが発行される

以降、`main` ブランチにpushするたびに自動で再デプロイされます。

## 注意点

- セーブデータ（ベストスコアなど）は各プレイヤーの端末のブラウザ内（localStorage）に保存されます。サーバー側には何も保存されないので、知り合いに配る分にはこのままで問題ありません。
- 今後、広告や課金を組み込む場合はこの構成だけでは足りず、別途バックエンドの追加が必要です（この点は会話内で相談済みの通り）。
