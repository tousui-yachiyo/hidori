# 緋酉 -HIDORI- LP

純米大吟醸「緋酉 -HIDORI-」のランディングページ。GitHub Pagesでホスティングする静的サイトです。

---

## 概要

| 項目 | 内容 |
|---|---|
| 商品名 | 緋酉 -HIDORI- 純米大吟醸 |
| 製造元 | 八千代酒造合名会社（山口県萩市・1887年創業） |
| 価格 | ¥9,800（税込・720ml） |
| 発売日 | 2026年5月10日（出荷は6月上旬から順次） |
| 原料米 | 山田錦100%（山口県萩地域産） |
| 精米歩合 | 40% |
| アルコール度数 | 15度 |
| 産地認定 | GI萩（地理的表示） |

技術スタック：HTML / CSS / JavaScript（外部フレームワーク・ビルドツール不要）。Google Fontsのみ外部CDNを利用。

---

## ファイル構成

```
/
├── index.html           # 日本語版 LP（HTML / CSS / JS を1ファイルに内包）
├── README.md            # このファイル
├── en/
│   └── index.html       # 英語版 LP（画像は ../images/ を共有）
└── images/
    ├── hero.jpg         # ファーストビュー / 最終CTA背景（再使用）
    ├── ogp.jpg          # SNSシェア用 OGP画像（5120×2688）
    ├── favicon.png      # ファビコン（八千代マーク）
    ├── image-01.jpg     # 利用シーン①「記念日に」
    ├── image-02.jpg     # 利用シーン②「贈りものに」
    ├── image-03.jpg     # 利用シーン③「週末のひと息に」
    ├── image-04.jpg     # ブランドストーリー（ラベル寄り）
    ├── image-05.jpg     # テイスティング（ボトル正面）
    ├── image-06.jpg     # 蔵元 スライダー Slide 1（萩の町並み）
    ├── image-07.jpg     # 蔵元 引用ブロック（米麹）
    ├── image-08.jpg     # 商品セクション（メイン写真）
    ├── image-09.jpg     # 十粋セクション（ボトル＋桐箱）
    ├── image-10.jpg     # 蔵元 スライダー Slide 2（仕込みの風景）
    ├── image-11.jpg     # 蔵元 スライダー Slide 3（醸造のディテール）
    └── image-12.jpg     # 蔵元 スライダー Slide 4（完成した一献）
```

---

## 多言語対応（日本語 / English）

本LPは日本語版と英語版の2ページ構成です。

| 言語 | ファイル | 公開URL |
|---|---|---|
| 日本語（デフォルト） | `index.html` | `https://hidori.puresake-tousui.com/` |
| English | `en/index.html` | `https://hidori.puresake-tousui.com/en/` |

- **言語切替ボタン**：両ページのヘッダー右上に `JA / EN` を設置。現在の言語がワインカラーで強調されます。日本語版の `EN` は `en/` へ、英語版の `JA` は `../`（日本語トップ）へリンクします。
- **画像は共有**：英語版は独自の画像を持たず、`../images/` で日本語版と同じ画像を参照します。画像を差し替えれば**両言語に同時反映**されます。
- **hreflang**：両ページの `<head>` に `ja` / `en` / `x-default` の相互参照を設定済み（検索エンジンが言語別に正しいページを表示します）。
- **英語版のメタ情報**：`lang="en"`、`og:locale=en_US`、`canonical`/`og:url` は `/en/`、JSON-LD も英語化済み。

### 更新時の同期ルール（重要）

**日本語版（`index.html`）と英語版（`en/index.html`）は別ファイルです。** 一方を直すと、もう一方は自動では変わりません。以下を編集したら必ず両方を更新してください。

- 価格・スペック・発売日の変更（→ 本文・メタ・JSON-LD・Sticky CTA すべて）
- CTAリンクURLの変更
- セクションの追加・削除
- 文言の修正

CTAリンクや外部リンク（EC・十粋・Instagram・問い合わせ）は**両ページで共通**です。発売後に「予約する → 購入する」へ変える場合も両ページで対応してください。

---

## 公開方法（GitHub Pages）

### 1. リポジトリを作成してファイルをアップロード

```bash
git init
git add index.html README.md en/ images/
git commit -m "Initial commit: 緋酉 LP"
git branch -M main
git remote add origin https://github.com/USERNAME/REPONAME.git
git push -u origin main
```

### 2. GitHub Pagesを有効化

1. リポジトリの **Settings** → **Pages** を開く
2. **Source** で `Deploy from a branch` を選択
3. **Branch** を `main` / `(root)` に設定 → Save
4. 数分後、`https://USERNAME.github.io/REPONAME/` で公開されます

### 3. 公開後の確認

- [ ] スマートフォン表示の確認
- [ ] CTAリンクの動作確認（ECサイトへの遷移）
- [ ] Sticky CTA（モバイル下部固定）の動作確認
- [ ] FAQアコーディオンの開閉
- [ ] [Twitter Card Validator](https://cards-dev.twitter.com/validator) でOGP表示確認
- [ ] [Google Rich Results Test](https://search.google.com/test/rich-results) で構造化データ検証

---

## 画像差し替え箇所

すべて `images/` ディレクトリ内のファイルを上書きすれば反映されます。**ファイル名は変えずに同じ名前で保存**してください。

| ファイル | 用途 | 推奨サイズ・形式 |
|---|---|---|
| `images/hero.jpg` | ファーストビュー & 最終CTA背景 | 横長 1980×1115（16:9）以上 / JPG |
| `images/ogp.jpg` | SNSシェア画像（OGP・Twitter Card） | 1200×630（1.91:1）以上 / JPG |
| `images/favicon.png` | ブラウザタブ・iOSホームアイコン | 正方形 512×512 / **PNG（透過推奨）** |
| `images/image-01.jpg` | 利用シーン①「記念日に」 | 横長 1200×900（4:3） / JPG |
| `images/image-02.jpg` | 利用シーン②「贈りものに」 | 横長 1200×900（4:3） / JPG |
| `images/image-03.jpg` | 利用シーン③「週末のひと息に」 | 横長 1200×900（4:3） / JPG |
| `images/image-04.jpg` | ブランドストーリー（ラベル寄り） | 縦長 1200×1500（4:5）推奨 / JPG |
| `images/image-05.jpg` | テイスティング（ボトル正面） | 縦長 1200×1500（4:5）推奨 / JPG |
| `images/image-06.jpg` | 蔵元 スライダー Slide 1（萩の風景） | 横長 1920×1080（16:9） / JPG |
| `images/image-07.jpg` | 蔵元 引用ブロック（米麹） | 横長 1200×900（4:3） / JPG |
| `images/image-08.jpg` | 商品メイン写真 | 正方形 1200×1200（1:1）推奨 / JPG |
| `images/image-09.jpg` | 十粋セクション | 横長 1600×1000 / JPG |
| `images/image-10.jpg` | 蔵元 スライダー Slide 2（仕込みの風景） | 横長 1920×1080（16:9） / JPG |
| `images/image-11.jpg` | 蔵元 スライダー Slide 3（醸造のディテール） | 横長 1920×1080（16:9） / JPG |
| `images/image-12.jpg` | 蔵元 スライダー Slide 4（完成した一献） | 横長 1920×1080（16:9） / JPG |

### 蔵元スライダーについて

蔵元セクションのメイン画像は **4枚の写真を切り替えるスライダー** になっています。

- **自動切替**：5秒ごとに自動でスライド（ホバー時は停止／ビューポート外でも停止）
- **手動切替**：左右の矢印ボタン、下部のドット、スワイプ（モバイル）に対応
- **キャプション**：各スライドの左下に表示。`<span class="brewery-slide-caption">` のテキストを編集
- **アスペクト比**：16:9（PC・モバイル共通）

スライダーの**枚数を増減したい**場合は `index.html` の `.brewery-slide` の数と `.brewery-slider-dots .dot` の数を一致させてください。

**注意点：** `image-07.jpg`（米麹画像）は4.8MBと大きめのため、本番デプロイ前に2MB以下へ圧縮することを推奨します（[TinyPNG](https://tinypng.com/) など）。

---

## CTAリンク差し替え箇所

`index.html`（日本語）と `en/index.html`（英語）にそれぞれ同じCTA / 外部リンクがあります。リンクURLを変えるときは**両ファイル**を検索置換してください。

| # | 場所 | 現在のリンク先 | 用途 |
|---|---|---|---|
| 1 | ヘッダー右上「予約する」 | `https://ec.yachiyo-sake.com/items/142632636` | EC予約 |
| 2 | ヒーロー「緋酉を、予約する」 | 同上 | EC予約（メインCTA） |
| 3 | 商品セクション「ECで予約する」 | 同上 | EC予約 |
| 4 | 商品セクション「特定商取引法」 | `https://ec.yachiyo-sake.com/law` | 法務情報 |
| 5 | FAQ「表記を見る」 | `https://ec.yachiyo-sake.com/law` | 法務情報 |
| 6 | FAQ「お問い合わせ」 | `mailto:info@puresake-tousui.com` | メール問い合わせ |
| 7 | 十粋セクション「十粋を見る」 | `https://puresake-tousui.com/` | 十粋公式サイト |
| 8 | 最終CTA「緋酉を、予約する」 | `https://ec.yachiyo-sake.com/items/142632636` | EC予約 |
| 9 | Sticky CTA（モバイル） | 同上 | EC予約 |
| 10 | フッター 各種リンク | 上記の組み合わせ | 各種ページ |

### 一括置換のサンプル

エディタで以下を一括置換すれば、全EC予約リンクを更新できます。

```
変更前: https://ec.yachiyo-sake.com/items/142632636
変更後: （新しい予約URL）
```

その他のリンクは `index.html` 内の `<!-- CTA:` コメントを目印に探してください。

---

## SEO・OGP の差し替え箇所

`index.html` の `<head>` 内、以下の項目は **公開ドメインに合わせて変更を推奨** します。

```html
<!-- 公開URLが決まったら以下を絶対URLに変更 -->
<link rel="canonical" href="https://ec.yachiyo-sake.com/items/142632636" />
<meta property="og:url" content="https://ec.yachiyo-sake.com/items/142632636" />
<meta property="og:image" content="images/ogp.jpg" />
<meta name="twitter:image" content="images/ogp.jpg" />
```

**推奨：** 一部のSNSクローラー（Slack等）は相対パスを正しく処理しないため、本番では絶対URLへ変更してください。

```html
<!-- 例: https://username.github.io/repo/ で公開する場合 -->
<meta property="og:image" content="https://username.github.io/repo/images/ogp.jpg" />
<meta name="twitter:image" content="https://username.github.io/repo/images/ogp.jpg" />
```

---

## 更新時の注意点

### コンテンツ変更時

- **価格・スペックを変更する場合は4箇所を要更新**
  - ヒーロー直下の `¥8,800 (税込) ／ 720ml`
  - 商品セクションの `purchase-price-value` と `purchase-spec`
  - 最終CTAの `final-cta-price-line`
  - Sticky CTAの `sticky-cta-price`
  - JSON-LDの `"price": "8800"`
- **発売日を変更する場合**
  - ヒーローバッジ `予約受付中／2026.05.10 発売`
  - 購入ノート `2026年5月10日 発売（出荷は6月上旬から順次）`
  - JSON-LD `"availabilityStarts": "2026-05-10T00:00:00+09:00"`
  - FAQ「いつから購入できますか？」の回答
- **発売後はCTA文言を「予約する」→「購入する」に変更**

### 画像差し替え時

- **ファイル名は固定**（HTML側は `images/image-XX.jpg` を参照しているため）
- 画像サイズは「画像差し替え箇所」の推奨に合わせる（CLS対策）
- ファイルサイズは1枚あたり **500KB以下** が理想（hero/ogpは例外的に2MBまで許容）
- カラートーンは **ローズ系・暖色系** を維持するとデザインと馴染む

### コード編集時

- インデントは半角スペース2つ
- CSSはすべて `<style>` タグ内、JSはすべて `<script>` タグ内に統一
- 外部ライブラリの追加は推奨しない（パフォーマンス維持のため）
- メタタグ・JSON-LDの編集後は [Google Rich Results Test](https://search.google.com/test/rich-results) で検証

### 動作要件

| 項目 | 対応 |
|---|---|
| 推奨ブラウザ | Chrome / Safari / Edge / Firefox の最新版 |
| モバイル対応 | iOS Safari 14+ / Android Chrome 90+ |
| JavaScript | 必須（FAQ・Sticky CTA・スクロール検知に使用） |
| 外部依存 | Google Fonts（オフラインでは表示が代替フォントになる） |

---

## ライセンス・クレジット

- **製造元**：八千代酒造合名会社（山口県萩市）
- **企画**：株式会社 AND.io
- **アートワーク**：Satoshi Tamura
- &copy; AND.io 2026

商品写真・ブランドアセットの権利は八千代酒造合名会社・AND.io に帰属します。LPコード自体は管理者の指定するライセンスに従ってください。

---

## お問い合わせ

LP・商品に関するお問い合わせは以下までお願いします。

**十粋事務局**
Email: [info@puresake-tousui.com](mailto:info@puresake-tousui.com)
