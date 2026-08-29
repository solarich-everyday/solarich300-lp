# 1500W GALLERY — 公開・運用ガイド

## 公開URL（ログイン不要・誰でも閲覧可）
**https://solarich-everyday.github.io/solarich300-lp/**

GitHub Pages（`gh-pages` ブランチ）で配信。CTAボタンはLINE友だち追加（LIFF）へ遷移。

## 構成（このブランチ＝公開ルート）
```
index.html        … ギャラリー本体（単一HTML）
img/grid/ (25枚)  … 一覧用（1600px）
img/full/ (25枚)  … 拡大用（2200px）
```

## 更新方法（写真差し替え・並び替え・コピー修正）
1. `main` ブランチの `1500-gallery/` で編集（元写真は `1500-gallery/originals/`）
2. 画像を変える場合はリポジトリ同梱の `build_gallery.py` で最適化
3. 更新した `index.html` と `img/` を **この `gh-pages` ブランチのルート**にコピーしてpush
4. push すると `.github/workflows/deploy-pages.yml` が自動実行され、数分で本番反映

## 独自ドメインに切り替える場合
`1500.solarich.co.jp` を使うには:
- DNSに `CNAME`: ホスト名 `1500` → 値 `solarich-everyday.github.io`
- このブランチ直下に `CNAME`（中身: `1500.solarich.co.jp`）を追加して push
