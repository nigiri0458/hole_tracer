# Hole Tracer

インドアゴルフの飛距離・左右ずれから、実際のホール画像上にボール位置を表示するPWAです。

## Pixel 9a に入れる手順（GitHub Pages）

PWAとしてホーム画面に追加・オフライン動作させるには、HTTPSで配信する必要があります。

1. GitHubで新しいリポジトリ（例：holetracer）を作り、このフォルダの5ファイル
   （index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png）をアップロードする
2. リポジトリの Settings → Pages で、Branch を main / (root) にして保存する
3. 数分後に表示される https://<ユーザー名>.github.io/holetracer/ をPixelのChromeで開く
4. Chromeのメニュー →「ホーム画面に追加」（または「アプリをインストール」）
5. 一度起動すれば、以降は通信なしでも動く

データは端末内にだけ保存されます。Chromeの「サイトデータを削除」を行うと消えます。

## 修正を反映するとき

index.html などを更新したら、sw.js 1行目の `holetracer-v1` を v2, v3… と上げてからアップロードしてください。
アプリを2回起動し直すと新しい版に切り替わります。

## ファイル構成

- index.html … 画面・処理のすべて（保存は IndexedDB）
- sw.js … オフライン用キャッシュ
- manifest.webmanifest, icon-*.png … ホーム画面追加用
