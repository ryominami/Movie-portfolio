# RYO STUDIO — Movie Portfolio

映像クリエイター Ryo のポートフォリオサイト。
公開URL: https://ryominami.github.io/Movie-portfolio/

## バージョン構成

| 版 | 場所 | 内容 |
|---|---|---|
| **v2 (現行)** | `index.html` | モーション強化版 —「映写機の光」コンセプト (GSAP + ScrollTrigger + Lenis) |
| **v1 (保存)** | `v1.html` / git tag `v1` | film-festival award-winner concept (モーション追加前) |

v1 はそのまま閲覧可能: https://ryominami.github.io/Movie-portfolio/v1.html

## v1 に戻す方法 (どちらか1つ)

```bash
# 方法A: タグから復元
git checkout v1 -- index.html
git commit -m "revert: back to v1"
git push

# 方法B: 保存ファイルから復元
cp v1.html index.html
git commit -am "revert: back to v1"
git push
```

## v2 モーションの構成

- すべての追加コードは `<style id="v2-motion">` と `<script id="v2-engine">` に隔離
- CDN: GSAP 3.12.5 / ScrollTrigger / Lenis 1.1.18 (CDN不達時は静的サイトとして完全動作)
- `prefers-reduced-motion` 完全対応 (アニメーション全停止・全コンテンツ即時表示)
- 単一ファイル構成は維持 (ビルド不要、GitHub Pages 直配信)
