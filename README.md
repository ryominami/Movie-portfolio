# RYO STUDIO — Movie Portfolio

映像クリエイター Ryo のポートフォリオサイト。
公開URL: https://ryominami.github.io/Movie-portfolio/

## バージョン構成

| 版 | 場所 | 内容 |
|---|---|---|
| **v7 (現行)** | `index.html` / git tag `v7` | 「深度と遊び心」— 4ペルソナ監査を反映した v6 強化版。本物の遠近カメラ (hero perspective+translateZ)・カーソル連動光源/グレア・見出しの奥行き登場・フィルムスプロケット付きマーキー・フクをつつくと「にゃ」・スクロール映写リール・紙グレイン+金箔スイープ・focus-visible・FAQ 2列。lightbox不可視バグ修正済 |
| **v6 (保存)** | git tag `v6` | 「クリームの上映サロン」— v5 の生成りクリーム転調。--paper #F5F1E8 基調・墨インク・濃ゴールド、contact のみエスプレッソ暗転+lightbox はダーク維持 (上映=暗転の演出)。構造/キャラ/機能は v5 と同一 |
| **v5 (保存)** | git tag `v5` | 「案内猫の試写室」— v3の情緒 × v4の3Dカード × 対話ヒーローの融合 (黒×ゴールドのダーク版)。オリジナル3Dキャラ「案内猫フク」(GPT Image 2生成・images/usher-cat*.png) がカードデッキ上で迎え、ブラー導入+タイプライター挨拶+ピルボタン。章漢字透かし復活、Shippori Mincho追加 |
| **v4 (保存)** | `v4.html` / git tag `v4` | 「CARD DECK」— 黒基調3Dカードデザイン (浮遊カードデッキヒーロー+筆記体透かし+作品フリップカード+スティッキー積層FEATURED+白セクション帯)。Kanit+Zen Kaku Gothic New、GSAP+ScrollTrigger のみ (Lenis廃止) |
| **v3 (保存)** | `v3.html` / git tag `v3` | 「試写室」— WebGLヒーロー(生きた映写)+作品フリップブック+章漢字透かし+高級化リファイン |
| **v2 (保存)** | git tag `v2` | 「映写機の光」モーション層 (GSAP + ScrollTrigger + Lenis) |
| **v1 (保存)** | `v1.html` / git tag `v1` | film-festival award-winner concept (モーション追加前) |

保存版はそのまま閲覧可能:
- v4: https://ryominami.github.io/Movie-portfolio/v4.html
- v3: https://ryominami.github.io/Movie-portfolio/v3.html
- v1: https://ryominami.github.io/Movie-portfolio/v1.html

## 別の版に切り替える方法 (どちらか1つ)

```bash
# 方法A: タグから復元 (v1 / v2 / v3 / v4 / v5)
git checkout v4 -- index.html   # v4 に切り替える例
git commit -m "switch: to v4"
git push

# 方法B: 保存ファイルから復元
cp v4.html index.html           # v3 なら cp v3.html index.html
git commit -am "switch: to v4"
git push
# ※ v5 に戻すときは images/usher-cat*.png が必要 (リポジトリに同梱済み)
```

## v4 の構成

- 単一ファイル構成 (ビルド不要、GitHub Pages 直配信)。CSS は `<style id="v4-style">`、JS は `<script id="v4-engine">` に隔離
- CDN: GSAP 3.12.5 + ScrollTrigger のみ。**CDN不達時は静的サイトとして完全動作** (`html.motion-ok` ゲート)
- フリップカード: 自動公開レールのカードマークアップ (`.work-card` = thumbnail+info の2子構造) をそのまま表/裏として再解釈 — レール (`portfolio_publish.py`) 側の変更ゼロ
- 自動公開アンカーは維持: `PORTFOLIO:WORKS:INSERT` (works-grid 末尾) / `PORTFOLIO:MORE:INSERT` (more-works-grid 末尾)。**消すと自動挿入が停止する**
- 日英バイリンガル (translations 辞書 + `#langToggle` + localStorage) は v3 から完全引き継ぎ
- `prefers-reduced-motion` 完全対応 (アニメ停止・全コンテンツ即時表示)、モバイル 320px〜4K レスポンシブ

## 検収 (v4 デプロイ前に実施済)

- 機械: INSERT アンカー各1・data-video 一意・受賞11/料金3/FAQ6 全文一致・メール掲載0
- ブラウザ4パス: desktop 1440 / mobile 390 / prefers-reduced-motion / CDN断 — 20項目 PASS
