# 吉祥寺レディースクリニック 乳腺外来 LP プロジェクトノート

## プロジェクト概要

| 項目 | 内容 |
|------|------|
| クライアント | 吉祥寺レディースクリニック |
| 制作物 | 乳腺外来 LP（ランディングページ） |
| レビューURL | https://kichijyoji-breast-clinic.vercel.app/lp-review/_G-standalone_v2.html |
| リポジトリ | `/Users/asako/Documents/kichijyoji-breast-clinic/` |
| 状態 | **制作中**（2026-05-20〜） |

---

## 採用デザイン：Variant G2

複数案（A〜G）を比較検討し、**Variant G2** が採用。

### デザイン特徴
- ピンク系（`#DC7A95`）のブランドカラー
- うねうね曲線のSVGウェーブで各セクションを仕切る
- 大きなblobデコレーション（半透明の円形）を背景に重ねる
- 固定フロートバッジ（右下・電話番号）
- フォント：`Zen Maru Gothic` × `Quicksand`

---

## ファイル構成

```
kichijyoji-breast-clinic/
├── docs/
│   └── lp-nyusen.md          # このファイル
├── lp-review/
│   ├── _G-standalone_v2.html # 【レビュー用】バンドル済み（19MB・全アセット埋め込み）
│   ├── variant-g2.html       # 【ソース】編集はここを行う（React/JSX・CDN参照）
│   ├── index.html            # レビュー一覧（パスワードゲート付き）
│   └── variant-a〜g.html     # 比較用の他案
├── musashino_nyugan_v2.html  # 武蔵野市乳がん検診LP
└── index.html / index-v2.html
```

### 編集ルール
- **日常の編集**: `variant-g2.html` を直接編集
- **レビュー用更新**: 編集後、standaloneを再ビルドして `_G-standalone_vN.html` として保存
- **バージョン命名**: `_G-standalone_v2.html` → `_G-standalone_v3.html` → `_G-standalone_v3_1.html` ...

---

## セクション構成

| # | セクション | 内容 | 写真状態 |
|---|------------|------|---------|
| 1 | HERO | キャッチコピー＋CTAボタン | **プレースホルダー**（右カラム） |
| 2 | ABOUT | 乳腺外来の説明 | **プレースホルダー**（右カラム） |
| 3 | STRENGTHS | 選ばれる4つの理由（カード） | 写真なし（テキストカード） |
| 4 | DOCTOR | 担当医師紹介・伊藤真由子先生 | **プレースホルダー**（左カラム） |
| 5 | EXAMS | 検査タブ（マンモ/エコー/細胞診/組織診）| 写真なし |
| 6 | PRICE | 費用・検診内容 | 写真なし |
| 7 | FLOW | 検診の流れ（ステップ） | 写真なし |
| 8 | FAQ | よくある質問（アコーディオン） | 写真なし |
| 9 | CTA | 予約・お問い合わせ | 写真なし |
| 10 | FOOTER | 住所・リンク | — |

---

## 写真素材

### 利用可能な素材

| ファイル | サイズ | 内容 | 用途案 |
|---------|--------|------|--------|
| `~/Downloads/乳腺科.jpg` | 246×420px | 胸に手を当てる女性（実写） | Hero または About |
| `~/Downloads/ChatGPT Image 2026年5月15日 16_30_35.png` | 1254×1254px | 「女性検診」ピンクイラスト（丸型） | Hero または About のアクセント |
| `~/Downloads/ChatGPT Image 2026年5月15日 17_10_26.png` | 1254×1254px | 上と同内容（別バージョン） | 同上 |
| `/cf-kichijoji/public/assets/img/doctor/mishina.png` | 丸型 | 三品先生（白衣・丸抜き） | Doctor（要確認：伊藤先生の写真と差し替え） |

### 写真の配置方針（未定）
- **Hero右**: 院内写真 or 医師ポートレート → 要確認・要素材
- **About右**: 院内の雰囲気写真 → `乳腺科.jpg` で代替可
- **Doctor左**: 伊藤真由子先生の写真 → 素材未入手（要クライアント確認）

---

## テキスト確認事項

- [ ] 医師名「伊藤真由子先生」は確定か（実在する先生の名前か）
- [ ] 診療時間 `9:15-12:15 / 14:15-18:15` は乳腺外来の専用枠か
- [ ] 乳腺外来の受付開始時期・告知タイミング
- [ ] ネット予約リンク（CTAボタンのhref）

---

## TODO（仕上げ作業）

### 写真追加
- [ ] Hero右カラムに写真配置（`vg-hero-img` の `repeating-linear-gradient` を `<img>` に置き換え）
- [ ] About右カラムに写真配置（`vg-about-img`）
- [ ] Doctor左カラムに医師写真配置（`vg-doc-photo`）

### テキスト・コンテンツ
- [ ] FAQ追加（現在4件 → もっと増やすか確認）
- [ ] CTAボタンのネット予約リンクを本物のURLに
- [ ] ヘッダーナビのリンク（href を各セクションIDに）
- [ ] フッターのリンク先を本番URLに

### 仕上げ
- [ ] SPでの表示確認
- [ ] `_G-standalone_v3.html` としてビルドしVercelにデプロイ
- [ ] git commit & push

---

## デザイン変数（参照用）

```css
--pink-pale:   #FCE9EE   /* 薄ピンク背景 */
--pink-soft:   #F8D2DD
--pink:        #F5B6C5
--pink-mid:    #ED9DB1
--pink-deep:   #DC7A95   /* メインカラー・CTA */
--pink-darker: #B83969
--text:        #3D1F2A
--text-soft:   rgba(61,31,42,0.7)
--jp:          'Zen Maru Gothic', 'Noto Sans JP', sans-serif
--en:          'Quicksand', sans-serif
```

---

## 更新履歴

| 日付 | バージョン | 内容 |
|------|-----------|------|
| 2026-05-13 | v2 | Variant G2 採用・レビューURL公開 |
| 2026-05-20 | — | 仕上げ作業開始・プロジェクトノート作成 |
