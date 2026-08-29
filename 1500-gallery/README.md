# 1500W GALLERY — solarich 1500 キャンペーン用ギャラリー

公開URL（予定）: **https://1500.solarich.co.jp/**

## フォルダ構成

```
1500-gallery/
├── index.html        … ギャラリーサイト本体（単一HTML・CSS/JSインライン）
├── CNAME             … カスタムドメイン設定（1500.solarich.co.jp）
├── img/
│   ├── grid/  (25枚) … 一覧表示用（長辺1600px・q86）
│   └── full/  (25枚) … 拡大表示用（長辺2200px・q88）
└── originals/ (25枚) … 撮影オリジナル（Dropbox納品データ）
```

- CTAボタン: LINE友だち追加（LIFF）へ遷移
- 画像は相対パス参照のため、このフォルダをそのまま公開ルートに置けば動作します

## 公開手順（GitHub Pages ＋ 独自サブドメイン）

1. **DNS設定**（solarich.co.jp のDNS管理画面）
   - レコード種別: `CNAME`
   - ホスト名: `1500`
   - 値: `solarich-everyday.github.io`
2. **GitHub Pages有効化**（リポジトリ Settings → Pages）
   - Source: この `1500-gallery/` の内容が公開ルートになるよう設定
     （最も簡単なのは、このフォルダの中身だけを `gh-pages` ブランチの直下に置く運用）
   - Custom domain: `1500.solarich.co.jp`（CNAMEファイルで自動入力されます）
   - 「Enforce HTTPS」にチェック
3. DNS反映後、**https://1500.solarich.co.jp/** でギャラリーが表示されます

## 画像の差し替え・追加

`originals/` に元写真を置き、リポジトリ同梱の `build_gallery.py` を実行すると
`img/grid` `img/full` の最適化画像と `index.html` の写真リストが再生成されます。
