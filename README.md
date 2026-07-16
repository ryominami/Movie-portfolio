# RYO STUDIO — Movie Portfolio

映像クリエイター Ryo のポートフォリオサイト。
公開URL: https://ryominami.github.io/Movie-portfolio/

## バージョン構成

| 版 | 場所 | 内容 |
|---|---|---|
| **v4 (現行)** | `index.html` | 「CARD DECK」— 黒基調3Dカードデザイン (浮遊カードデッキヒーロー+筆記体透かし+作品フリップカード+スティッキー積層FEATURED+白セクション帯)。Kanit+Zen Kaku Gothic New、GSAP+ScrollTrigger のみ (Lenis廃止) |
| **v3 (保存)** | `v3.html` / git tag `v3` | 「試写室」— WebGLヒーロー(生きた映写)+作品フリップブック+章漢字透かし+高級化リファイン |
| **v2 (保存)** | git tag `v2` | 「映写機の光」モーション層 (GSAP + ScrollTrigger + Lenis) |
| **v1 (保存)** | `v1.html` / git tag `v1` | film-festival award-winner concept (モーション追加前) |

保存版はそのまま閲覧可能:
- v3: https://ryominami.github.io/Movie-portfolio/v3.html
- v1: https://ryominami.github.io/Movie-portfolio/v1.html

## 前の版に戻す方法 (どちらか1つ)

```bash
# 方法A: タグから復元 (v1 / v2 / v3)
git checkout v3 -- index.html   # v3 に戻す例
git commit -m "revert: back to v3"
git push

# 方法B: 保存ファイルから復元
cp v3.html index.html           # v1 なら cp v1.html index.html
git commit -am "revert: back to v3"
git push
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
