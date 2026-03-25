# Phase 7: レポートCSS実装

レポート生成時、このCSSをHTMLの `<style>` タグにそのままコピーして使う。

```css
/* ============================================
   CSS変数定義（:root）
   テーマ切り替えはここだけ変えればOK
   ============================================ */
:root {
  /* カラー */
  --color-bg: #ffffff;
  --color-bg-alt: #f8f9fa;
  --color-bg-card: #f1f3f5;
  --color-text-heading: #1a1a2e;
  --color-text-body: #374151;
  --color-text-sub: #6b7280;
  --color-accent: #4f46e5;
  --color-accent-hover: #3730a3;
  --color-border: #e5e7eb;
  --color-border-table: #d1d5db;
  --color-success: #059669;
  --color-warning: #d97706;
  --color-error: #dc2626;

  /* チャートカラー */
  --chart-1: #4f46e5;
  --chart-2: #06b6d4;
  --chart-3: #8b5cf6;
  --chart-4: #f59e0b;
  --chart-5: #10b981;

  /* タイポグラフィ */
  --font-family: "Inter", "Noto Sans JP", -apple-system, BlinkMacSystemFont, sans-serif;
  --font-size-base: 16px;
  --font-size-sm: 14px;
  --font-size-xs: 12px;
  --font-size-h1: 2rem;
  --font-size-h2: 1.5rem;
  --font-size-h3: 1.125rem;
  --line-height-body: 1.8;

  /* レイアウト */
  --max-width: 1280px;
  --padding-x: 32px;
  --section-gap: 64px;
  --card-radius: 12px;
  --shadow-sm: 0 1px 3px rgba(0,0,0,0.08), 0 1px 2px rgba(0,0,0,0.06);
  --shadow-md: 0 4px 6px rgba(0,0,0,0.07), 0 2px 4px rgba(0,0,0,0.06);
  --shadow-lg: 0 10px 15px rgba(0,0,0,0.07), 0 4px 6px rgba(0,0,0,0.05);
  --card-shadow: var(--shadow-sm);
  --card-shadow-hover: var(--shadow-md);

  /* ナビバー */
  --nav-height: 60px;
}

/* ============================================
   ダークテーマ（prefers-color-scheme）
   デフォルトは白。ダークはオプション
   ============================================ */
@media (prefers-color-scheme: dark) {
  :root {
    --color-bg: #0f0f0f;
    --color-bg-alt: #1a1a1a;
    --color-bg-card: #242424;
    --color-text-heading: #f0f0f0;
    --color-text-body: #d1d5db;
    --color-text-sub: #9ca3af;
    --color-accent: #6366f1;
    --color-accent-hover: #818cf8;
    --color-border: #2d2d2d;
    --color-border-table: #374151;
  }
}

/* ============================================
   リセット・ベーススタイル
   ============================================ */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
  font-size: var(--font-size-base);
}

body {
  font-family: var(--font-family);
  background-color: var(--color-bg);
  color: var(--color-text-body);
  line-height: var(--line-height-body);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* ============================================
   ナビバー（固定、白背景、backdrop blur）
   ============================================ */
.report__nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: var(--nav-height);
  background-color: rgba(255, 255, 255, 0.85);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--color-border);
  z-index: 100;
  display: flex;
  align-items: center;
}

.report__nav-inner {
  max-width: var(--max-width);
  width: 100%;
  margin: 0 auto;
  padding: 0 var(--padding-x);
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
}

.report__nav-title {
  font-size: 14px;
  font-weight: 600;
  color: var(--color-text-heading);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.report__nav-links {
  display: flex;
  align-items: center;
  gap: 4px;
  list-style: none;
  flex-shrink: 0;
}

.report__nav-links a {
  display: block;
  padding: 6px 12px;
  font-size: 13px;
  color: var(--color-text-sub);
  text-decoration: none;
  border-radius: 6px;
  transition: background-color 0.15s, color 0.15s;
}

.report__nav-links a:hover {
  background-color: var(--color-bg-card);
  color: var(--color-text-heading);
}

/* ============================================
   メインコンテンツ（ナビバー分のオフセット）
   ============================================ */
.report__main {
  padding-top: var(--nav-height);
}

.report__container {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 var(--padding-x);
}

/* ============================================
   ヒーローセクション（タイトル・日付・サマリー）
   ============================================ */
.report__hero {
  padding: 80px 0 72px;
  background: linear-gradient(135deg, var(--color-bg) 0%, var(--color-bg-alt) 50%, rgba(79, 70, 229, 0.04) 100%);
  border-bottom: 1px solid var(--color-border);
}

.report__hero-label {
  display: inline-block;
  padding: 4px 12px;
  background-color: rgba(79, 70, 229, 0.08);
  color: var(--color-accent);
  font-size: var(--font-size-sm);
  font-weight: 600;
  border-radius: 100px;
  margin-bottom: 16px;
}

.report__hero-title {
  font-size: clamp(1.75rem, 4vw, 2.5rem);
  font-weight: 700;
  color: var(--color-text-heading);
  letter-spacing: -0.02em;
  line-height: 1.2;
  margin-bottom: 16px;
}

.report__hero-meta {
  display: flex;
  align-items: center;
  gap: 16px;
  font-size: var(--font-size-sm);
  color: var(--color-text-sub);
  margin-bottom: 24px;
  flex-wrap: wrap;
}

.report__hero-meta-item {
  display: flex;
  align-items: center;
  gap: 6px;
}

.report__hero-summary {
  font-size: 1.0625rem;
  line-height: 1.7;
  color: var(--color-text-body);
  max-width: 720px;
  padding: 20px 24px;
  background-color: var(--color-bg-alt);
  border-left: 3px solid var(--color-accent);
  border-radius: 0 8px 8px 0;
}

/* ============================================
   目次（インライン、ヒーロー直下）
   ============================================ */
.report__toc {
  padding: 32px 0;
  border-bottom: 1px solid var(--color-border);
}

.report__toc-title {
  font-size: var(--font-size-sm);
  font-weight: 600;
  color: var(--color-text-sub);
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-bottom: 12px;
}

.report__toc-list {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  list-style: none;
}

.report__toc-list a {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 6px 14px;
  background-color: var(--color-bg-alt);
  border: 1px solid var(--color-border);
  border-radius: 100px;
  font-size: var(--font-size-sm);
  color: var(--color-text-body);
  text-decoration: none;
  transition: border-color 0.15s, color 0.15s, background-color 0.15s;
}

.report__toc-list a:hover {
  border-color: var(--color-accent);
  color: var(--color-accent);
  background-color: rgba(79, 70, 229, 0.04);
}

/* ============================================
   セクション（交互背景）
   ============================================ */
.report__section {
  padding: 80px 0;
}

.report__section:nth-child(even) {
  background-color: var(--color-bg-alt);
}

.report__section-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 var(--padding-x);
}

.report__section-label {
  font-size: var(--font-size-xs);
  font-weight: 700;
  color: var(--color-accent);
  text-transform: uppercase;
  letter-spacing: 0.1em;
  margin-bottom: 8px;
}

.report__section-title {
  font-size: var(--font-size-h2);
  font-weight: 700;
  color: var(--color-text-heading);
  letter-spacing: -0.02em;
  line-height: 1.3;
  margin-bottom: 24px;
  padding-bottom: 16px;
  border-bottom: 1px solid var(--color-border);
}

.report__section-body {
  font-size: var(--font-size-base);
  line-height: var(--line-height-body);
  color: var(--color-text-body);
}

.report__section-body p {
  margin-bottom: 16px;
}

.report__section-body h3 {
  font-size: var(--font-size-h3);
  font-weight: 700;
  color: var(--color-text-heading);
  margin: 32px 0 12px;
}

.report__section-body ul,
.report__section-body ol {
  padding-left: 24px;
  margin-bottom: 16px;
}

.report__section-body li {
  margin-bottom: 8px;
}

/* ============================================
   カード（影、角丸、ホバー効果）
   ============================================ */
.report__card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  margin-top: 24px;
}

.report__card {
  background-color: var(--color-bg);
  border: 1px solid var(--color-border);
  border-radius: var(--card-radius);
  padding: 24px;
  box-shadow: var(--card-shadow);
  transition: box-shadow 0.2s, transform 0.2s;
}

.report__card:hover {
  box-shadow: var(--card-shadow-hover);
  transform: translateY(-2px);
}

.report__card-label {
  font-size: var(--font-size-xs);
  font-weight: 700;
  color: var(--color-text-sub);
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-bottom: 8px;
}

.report__card-value {
  font-size: 2rem;
  font-weight: 700;
  color: var(--color-text-heading);
  letter-spacing: -0.02em;
  line-height: 1;
  margin-bottom: 8px;
}

.report__card-desc {
  font-size: var(--font-size-sm);
  color: var(--color-text-sub);
  line-height: 1.5;
}

/* ============================================
   テーブル（ヘッダー、ホバー、横スクロール）
   ============================================ */
.report__table-wrapper {
  overflow-x: auto;
  margin-top: 24px;
  border: 1px solid var(--color-border);
  border-radius: var(--card-radius);
}

.report__table {
  width: 100%;
  border-collapse: collapse;
  font-size: var(--font-size-sm);
}

.report__table thead {
  background-color: var(--color-bg-alt);
  position: sticky;
  top: 0;
}

.report__table th {
  padding: 12px 16px;
  text-align: left;
  font-size: var(--font-size-xs);
  font-weight: 700;
  color: var(--color-text-sub);
  text-transform: uppercase;
  letter-spacing: 0.06em;
  border-bottom: 1px solid var(--color-border-table);
  white-space: nowrap;
}

.report__table td {
  padding: 12px 16px;
  color: var(--color-text-body);
  border-bottom: 1px solid var(--color-border);
  vertical-align: top;
}

.report__table tbody tr:last-child td {
  border-bottom: none;
}

.report__table tbody tr:hover td {
  background-color: var(--color-bg-alt);
}

/* ============================================
   横棒グラフ（flexbox + CSS変数で値制御）
   使い方: style="--bar-value: 75%"
   ============================================ */
.report__chart-bar {
  display: flex;
  flex-direction: column;
  gap: 12px;
  margin-top: 24px;
}

.report__chart-bar-item {
  display: grid;
  grid-template-columns: 140px 1fr 60px;
  align-items: center;
  gap: 12px;
}

.report__chart-bar-label {
  font-size: var(--font-size-sm);
  color: var(--color-text-body);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.report__chart-bar-track {
  height: 10px;
  background-color: var(--color-bg-card);
  border-radius: 100px;
  overflow: hidden;
}

.report__chart-bar-fill {
  height: 100%;
  width: var(--bar-value, 0%);
  background: linear-gradient(90deg, var(--chart-1), #6366f1);
  border-radius: 100px;
  transition: width 0.6s cubic-bezier(0.4, 0, 0.2, 1);
}

/* チャートカラーバリエーション */
.report__chart-bar-fill--2 { background: linear-gradient(90deg, var(--chart-2), #22d3ee); }
.report__chart-bar-fill--3 { background: linear-gradient(90deg, var(--chart-3), #a78bfa); }
.report__chart-bar-fill--4 { background: linear-gradient(90deg, var(--chart-4), #fbbf24); }
.report__chart-bar-fill--5 { background: linear-gradient(90deg, var(--chart-5), #34d399); }

.report__chart-bar-value {
  font-size: var(--font-size-sm);
  font-weight: 600;
  color: var(--color-text-heading);
  text-align: right;
}

/* ============================================
   引用ブロック（左ボーダー、背景）
   ============================================ */
.report__blockquote {
  margin: 24px 0;
  padding: 16px 20px;
  background-color: rgba(79, 70, 229, 0.04);
  border-left: 3px solid var(--color-accent);
  border-radius: 0 8px 8px 0;
}

.report__blockquote p {
  font-style: italic;
  color: var(--color-text-body);
  margin-bottom: 8px;
}

.report__blockquote p:last-child {
  margin-bottom: 0;
}

.report__blockquote cite {
  font-size: var(--font-size-sm);
  color: var(--color-text-sub);
  font-style: normal;
}

/* ============================================
   ステータスバッジ（緑/赤/黄のラベル）
   ============================================ */
.report__badge {
  display: inline-flex;
  align-items: center;
  padding: 2px 10px;
  border-radius: 100px;
  font-size: var(--font-size-xs);
  font-weight: 700;
  white-space: nowrap;
}

.report__badge--success {
  background-color: rgba(5, 150, 105, 0.1);
  color: var(--color-success);
}

.report__badge--warning {
  background-color: rgba(217, 119, 6, 0.1);
  color: var(--color-warning);
}

.report__badge--error {
  background-color: rgba(220, 38, 38, 0.1);
  color: var(--color-error);
}

.report__badge--neutral {
  background-color: var(--color-bg-card);
  color: var(--color-text-sub);
}

/* ============================================
   差分表示（週次レポートの前回比較用）
   ============================================ */

/* 新規項目: 緑背景 */
.report__badge--new {
  background-color: rgba(5, 150, 105, 0.12);
  color: #059669;
  border: 1px solid rgba(5, 150, 105, 0.25);
}

/* 変化あり: 青背景 */
.report__badge--changed {
  background-color: rgba(79, 70, 229, 0.1);
  color: var(--color-accent);
  border: 1px solid rgba(79, 70, 229, 0.2);
}

/* 継続（変化なし）: グレー背景 */
.report__badge--unchanged {
  background-color: var(--color-bg-card);
  color: var(--color-text-sub);
  border: 1px solid var(--color-border);
}

/* 消失: 赤背景 + 取り消し線 */
.report__badge--gone {
  background-color: rgba(220, 38, 38, 0.08);
  color: var(--color-error);
  border: 1px solid rgba(220, 38, 38, 0.2);
  text-decoration: line-through;
  text-decoration-color: rgba(220, 38, 38, 0.6);
}

/* 変化した数値の強調表示 */
.report__diff-highlight {
  font-weight: 700;
  color: var(--color-text-heading);
}

/* 上昇矢印（緑） */
.report__diff-arrow--up {
  font-size: var(--font-size-xs);
  font-weight: 700;
  color: #059669;
  margin-left: 4px;
  white-space: nowrap;
}

/* 下降矢印（赤） */
.report__diff-arrow--down {
  font-size: var(--font-size-xs);
  font-weight: 700;
  color: var(--color-error);
  margin-left: 4px;
  white-space: nowrap;
}

/* ============================================
   折れ線グラフ（SVG、スコア推移用）
   ============================================ */
.report__chart-line {
  margin-top: 24px;
  background-color: var(--color-bg);
  border: 1px solid var(--color-border);
  border-radius: var(--card-radius);
  padding: 24px;
  overflow: hidden;
}

.report__chart-line svg {
  width: 100%;
  height: auto;
  display: block;
  overflow: visible;
}

/* グリッド線 */
.report__chart-line .chart-grid-line {
  stroke: var(--color-border);
  stroke-width: 1;
  stroke-dasharray: 4 4;
}

/* 軸ラベル */
.report__chart-line .chart-axis-label {
  font-family: var(--font-family);
  font-size: 11px;
  fill: var(--color-text-sub);
}

/* 折れ線本体 */
.report__chart-line .chart-line {
  fill: none;
  stroke: var(--color-accent);
  stroke-width: 2.5;
  stroke-linecap: round;
  stroke-linejoin: round;
}

/* 塗りつぶしエリア（線の下） */
.report__chart-line .chart-area {
  fill: url(#chart-gradient);
  opacity: 0.15;
}

/* データポイント（丸） */
.report__chart-line .chart-dot {
  fill: var(--color-accent);
  stroke: var(--color-bg);
  stroke-width: 2.5;
  r: 4;
  cursor: pointer;
  transition: r 0.15s;
}

.report__chart-line .chart-dot:hover {
  r: 6;
}

/* ポイントラベル */
.report__chart-line .chart-point-label {
  font-family: var(--font-family);
  font-size: 11px;
  font-weight: 700;
  fill: var(--color-text-heading);
  text-anchor: middle;
}

/* グラフタイトル */
.report__chart-line-title {
  font-size: var(--font-size-sm);
  font-weight: 700;
  color: var(--color-text-heading);
  margin-bottom: 12px;
}

/* 凡例 */
.report__chart-legend {
  display: flex;
  gap: 20px;
  margin-top: 16px;
  flex-wrap: wrap;
}

.report__chart-legend-item {
  display: flex;
  align-items: center;
  gap: 6px;
  font-size: var(--font-size-xs);
  color: var(--color-text-sub);
}

.report__chart-legend-dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background-color: var(--color-accent);
  flex-shrink: 0;
}

.report__chart-legend-dot--2 { background-color: var(--chart-2); }
.report__chart-legend-dot--3 { background-color: var(--chart-3); }

/* レスポンシブ対応（折れ線グラフ） */
@media (max-width: 480px) {
  .report__chart-line {
    padding: 16px;
  }

  .report__chart-line .chart-point-label {
    display: none; /* 狭い画面ではラベル非表示 */
  }
}

/* ============================================
   ソース表記
   ============================================ */
/* インラインリンク */
.report__section-body a {
  color: var(--color-accent);
  text-decoration: underline;
  text-underline-offset: 2px;
  transition: color 0.15s;
}

.report__section-body a:hover {
  color: var(--color-accent-hover);
}

/* 末尾参照（出典ブロック） */
.report__sources {
  margin-top: 32px;
  padding-top: 24px;
  border-top: 1px solid var(--color-border);
}

.report__sources-title {
  font-size: var(--font-size-sm);
  font-weight: 700;
  color: var(--color-text-sub);
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-bottom: 12px;
}

.report__sources-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.report__sources-list li {
  font-size: var(--font-size-sm);
  color: var(--color-text-sub);
  display: flex;
  gap: 8px;
  align-items: baseline;
}

.report__sources-list li::before {
  content: counter(source-counter);
  counter-increment: source-counter;
  font-size: var(--font-size-xs);
  font-weight: 700;
  color: var(--color-accent);
  min-width: 16px;
}

.report__sources-list {
  counter-reset: source-counter;
}

.report__sources-list a {
  color: var(--color-accent);
  text-decoration: underline;
  text-underline-offset: 2px;
  word-break: break-all;
}

/* ============================================
   フッター
   ============================================ */
.report__footer {
  background-color: var(--color-bg-alt);
  border-top: 1px solid var(--color-border);
  padding: 32px 0;
  margin-top: var(--section-gap);
}

.report__footer-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 var(--padding-x);
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  flex-wrap: wrap;
}

.report__footer-text {
  font-size: var(--font-size-sm);
  color: var(--color-text-sub);
}

.report__footer-note {
  font-size: var(--font-size-xs);
  color: var(--color-text-sub);
  font-style: italic;
}

/* ============================================
   レスポンシブ（768px以下）
   ============================================ */
@media (max-width: 768px) {
  :root {
    --padding-x: 16px;
    --font-size-h1: 1.5rem;
    --font-size-h2: 1.25rem;
  }

  .report__nav-links {
    display: none; /* モバイルではナビリンクを非表示 */
  }

  .report__hero {
    padding: 40px 0 32px;
  }

  .report__card-grid {
    grid-template-columns: 1fr;
  }

  .report__chart-bar-item {
    grid-template-columns: 100px 1fr 50px;
    gap: 8px;
  }

  .report__footer-inner {
    flex-direction: column;
    align-items: flex-start;
  }
}

/* ============================================
   レスポンシブ（480px以下）
   ============================================ */
@media (max-width: 480px) {
  :root {
    --padding-x: 12px;
  }

  .report__section {
    padding: 40px 0;
  }
}

/* ============================================
   印刷スタイル
   ============================================ */
@media print {
  .report__nav {
    position: static;
    backdrop-filter: none;
    border-bottom: 1px solid #e5e7eb;
  }

  .report__main {
    padding-top: 0;
  }

  .report__section:nth-child(even) {
    background-color: transparent;
  }

  .report__card {
    box-shadow: none;
    border: 1px solid #e5e7eb;
  }

  /* 印刷時にURLを表示 */
  a[href]::after {
    content: " (" attr(href) ")";
    font-size: 11px;
    color: #6b7280;
  }

  /* ナビリンクは印刷不要 */
  .report__nav-links,
  .report__toc {
    display: none;
  }

  /* ページブレーク */
  .report__section {
    page-break-inside: avoid;
  }
}
```
