# Phase 7: レポート生成

## 目的

Phase 6の分析結果を、読みやすいHTMLレポートとして出力する。
白ベースのクリーンなデザインをデフォルトとし、Webサイトにそのまま組み込めるクオリティを目指す。

---

## HTML出力ルール

### 基本仕様

- **単一HTMLファイル**として出力する（CSS・JSはすべてインライン埋め込み）
- 外部ファイルへの依存なし（オフラインで開いても完全に表示できること）
- **文字コード**: UTF-8
- クラス名はBEM風（`.report__section`、`.report__card`、`.report__table` 等）
- `<section>` タグで区切り、iframe埋め込みしやすい構造にする

---

## デザイン仕様

### デフォルトテーマ: Light（白ベース）

Apple / Linear / Notion 風のクリーンなスタイル。

### カラーパレット

| 用途 | 値 |
|------|-----|
| メイン背景 | `#ffffff` |
| セクション交互背景 | `#f8f9fa` |
| カード背景 | `#f1f3f5` |
| 見出しテキスト | `#1a1a2e` |
| 本文テキスト | `#374151` |
| サブテキスト | `#6b7280` |
| アクセント（インディゴ） | `#4f46e5` |
| ボーダー | `#e5e7eb` |
| テーブルボーダー | `#d1d5db` |
| ステータス: 成功 | `#059669` |
| ステータス: 警告 | `#d97706` |
| ステータス: エラー | `#dc2626` |

### タイポグラフィ

- フォント: `"Inter", "Noto Sans JP", -apple-system, BlinkMacSystemFont, sans-serif`
- 見出し: `font-weight: 700`、`letter-spacing: -0.02em`
- 本文: `16px`、`line-height: 1.8`
- 注釈: `14px`

### レイアウト

- `max-width: 960px`（読みやすさ重視の記事幅）
- 左右padding: `24px`（モバイルは `16px`）
- セクション間: `64px` margin
- カード: `border-radius: 12px`、subtle shadow（`0 1px 3px rgba(0,0,0,0.08)`）
- テーブル: ヘッダー背景 `#f8f9fa`、ホバー `#f1f3f5`、`border-collapse: collapse`

---

## 完全なCSSブロック実装

以下をそのまま `<style>` タグに貼り付けて使う。

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
  --max-width: 960px;
  --padding-x: 24px;
  --section-gap: 64px;
  --card-radius: 12px;
  --card-shadow: 0 1px 3px rgba(0, 0, 0, 0.08), 0 1px 2px rgba(0, 0, 0, 0.04);
  --card-shadow-hover: 0 4px 12px rgba(0, 0, 0, 0.12);

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
  padding: 64px 0 48px;
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
  font-size: var(--font-size-h1);
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
  padding: 56px 0;
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
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
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

---

## テーマプリセット

ドメインprompt.mdで `## テーマ` が指定されている場合はそちらを使用する。
未指定の場合は **light（デフォルト）** を適用する。

### プリセット一覧

| テーマ名 | 説明 | 変更するCSS変数 |
|---------|------|----------------|
| **light**（デフォルト） | 白ベース。汎用レポート | 上記の`:root`そのまま |
| **dark** | ダークテーマ。tech系・夜間閲覧向け | `--color-bg: #0f0f0f` 等、`prefers-color-scheme`ブロックを参照 |
| **corporate** | グレー系。ビジネス向け・印刷想定 | `--color-accent: #1e40af`、`--color-bg-alt: #f0f4f8` |

### テーマのカスタマイズ方法

ドメインprompt.mdに以下を追加するだけ。

```markdown
## テーマ
- ベース: light
- アクセント: #16a34a（緑系）
- フォント: "Noto Sans JP", sans-serif
```

---

## HTMLテンプレート構造

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>レポートタイトル</title>
  <style>
    /* 上記のCSSをここに貼る */
  </style>
</head>
<body>

  <!-- ナビバー -->
  <nav class="report__nav">
    <div class="report__nav-inner">
      <span class="report__nav-title">レポートタイトル</span>
      <ul class="report__nav-links">
        <li><a href="#summary">サマリー</a></li>
        <li><a href="#analysis">詳細分析</a></li>
        <li><a href="#trend">トレンド</a></li>
        <li><a href="#action">アクション</a></li>
      </ul>
    </div>
  </nav>

  <main class="report__main">

    <!-- ヒーロー -->
    <div class="report__container">
      <div class="report__hero">
        <span class="report__hero-label">リサーチレポート</span>
        <h1 class="report__hero-title">レポートタイトル</h1>
        <div class="report__hero-meta">
          <span class="report__hero-meta-item">📅 2026-03-25</span>
          <span class="report__hero-meta-item">🔍 調査対象: ○○</span>
        </div>
        <div class="report__hero-summary">
          エグゼクティブサマリーをここに3〜5行で書く。結論から書くこと。
        </div>
      </div>

      <!-- 目次 -->
      <nav class="report__toc">
        <p class="report__toc-title">目次</p>
        <ul class="report__toc-list">
          <li><a href="#summary">📊 エグゼクティブサマリー</a></li>
          <li><a href="#analysis">🔍 詳細分析</a></li>
          <li><a href="#trend">📈 トレンド</a></li>
          <li><a href="#action">💡 アクション</a></li>
          <li><a href="#risk">⚠️ リスク</a></li>
          <li><a href="#outlook">🔮 今後の展望</a></li>
          <li><a href="#sources">📚 参考ソース</a></li>
        </ul>
      </nav>
    </div>

    <!-- セクション例 -->
    <section class="report__section" id="analysis">
      <div class="report__section-inner">
        <p class="report__section-label">詳細分析</p>
        <h2 class="report__section-title">○○の動向分析</h2>
        <div class="report__section-body">
          <p>本文テキスト。</p>

          <!-- カードグリッド例 -->
          <div class="report__card-grid">
            <div class="report__card">
              <p class="report__card-label">指標名</p>
              <p class="report__card-value">3.5兆円</p>
              <p class="report__card-desc">前年比 +12%。説明テキスト。</p>
            </div>
          </div>

          <!-- 横棒グラフ例 -->
          <div class="report__chart-bar">
            <div class="report__chart-bar-item">
              <span class="report__chart-bar-label">項目A</span>
              <div class="report__chart-bar-track">
                <div class="report__chart-bar-fill" style="--bar-value: 82%"></div>
              </div>
              <span class="report__chart-bar-value">82%</span>
            </div>
            <div class="report__chart-bar-item">
              <span class="report__chart-bar-label">項目B</span>
              <div class="report__chart-bar-track">
                <div class="report__chart-bar-fill report__chart-bar-fill--2" style="--bar-value: 65%"></div>
              </div>
              <span class="report__chart-bar-value">65%</span>
            </div>
          </div>

          <!-- 引用ブロック例 -->
          <blockquote class="report__blockquote">
            <p>「引用テキストをここに入れる」</p>
            <cite>— 発言者名、出典</cite>
          </blockquote>

          <!-- バッジ例 -->
          <span class="report__badge report__badge--success">成長</span>
          <span class="report__badge report__badge--warning">要注意</span>
          <span class="report__badge report__badge--error">リスク</span>
        </div>
      </div>
    </section>

    <!-- テーブル例 -->
    <section class="report__section" id="comparison">
      <div class="report__section-inner">
        <h2 class="report__section-title">比較テーブル</h2>
        <div class="report__table-wrapper">
          <table class="report__table">
            <thead>
              <tr>
                <th>項目</th>
                <th>値</th>
                <th>状態</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>サンプルA</td>
                <td>1,234</td>
                <td><span class="report__badge report__badge--success">良好</span></td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- 参考ソース -->
    <section class="report__section" id="sources">
      <div class="report__section-inner">
        <h2 class="report__section-title">参考ソース</h2>
        <div class="report__sources">
          <ol class="report__sources-list">
            <li><a href="https://example.com" target="_blank">記事タイトル — メディア名</a>（2026-03-25）</li>
          </ol>
        </div>
      </div>
    </section>

  </main>

  <!-- フッター -->
  <footer class="report__footer">
    <div class="report__footer-inner">
      <p class="report__footer-text">© 2026 Research Report</p>
      <p class="report__footer-note">本レポートは自動収集データと筆者分析に基づく。投資助言ではない。</p>
    </div>
  </footer>

</body>
</html>
```

---

## チャート選定ガイド

| データの性質 | 推奨チャート | CSS/SVG実装 |
|------------|-----------|------------|
| 順位・ランキング | 横棒グラフ | `--bar-value: %` + flexbox |
| 時系列推移 | 折れ線グラフ | SVG `<polyline>` |
| 構成比 | 円グラフ / ドーナツ | SVG `<circle>` + `stroke-dasharray` |
| 比較（2-5項目） | レーダーチャート | SVG `<polygon>` |
| 分布・相関 | 散布図 | SVG `<circle>` 配置 |
| Yes/No・進捗 | プログレスバー | `width: %` + gradient |
| 国別データ | ヒートマップ風テーブル | `background-color` の濃淡 |

⚠️ チャートは外部ライブラリ不使用。CSS/SVGのみで実装すること。

---

## デフォルトセクション構成

ドメインprompt.mdの `## レポートセクション` が未定義の場合、以下を使う。

1. **📊 エグゼクティブサマリー** — 全体の要約。結論から書く。3-5行
2. **🔍 詳細分析** — カテゴリ別/国別の詳細情報
3. **📈 トレンド分析** — 前回比・変化点・方向性
4. **💡 アクションアイデア** — 読者が取るべきアクション
5. **⚠️ リスク・注意点** — リスク要因・不確実性
6. **🔮 今後の注目ポイント** — 1-2週間の展望・予測
7. **📚 参考ソース** — 主要ソースのリスト

---

## 文章品質ルール

### 禁止パターン（使ったら即書き直し）

- **冒頭定型表現**: 「急速に進化する○○において」「目まぐるしく変化する○○」
- **ハイプ表現**: 「ゲームチェンジャー」「革命的」「画期的」「パラダイムシフト」
- **フィラー**: 「さらに」「加えて」の連続使用、「注目すべきは」の乱用
- **根拠なき主張**: ソースなしで「〜と言われている」「〜の見方が広がっている」

### 文体ルール

- **事実を先に、分析を後に。結論から書く**
- 具体的な数字・固有名詞を使う。「多くの企業が」ではなく「Google, Meta, Amazonが」
- 1段落1トピック。詰め込まない
- 読者は「で、結局どうなの？」を知りたい。**So What?を常に意識する**
- レポートの長さに上限なし。**正確さ・網羅性を優先する**（読みやすさは維持すること）

### 構造ルール（article-writing方式）

- **逆ピラミッド構造**: 最も重要な情報を冒頭に。詳細は後半に
- **1段落 = 1トピック = 3-5文**: 短く刻む。壁のような長文ブロックは禁止
- **見出しだけで内容が伝わる**: 見出しだけ読んでもレポートの骨子がわかるようにする
- **箇条書き vs 文章の使い分け**:
  - ファクトの列挙 → 箇条書き
  - 因果関係・分析 → 文章
  - 比較 → テーブル
- **数字の書き方**: 1万未満は数字（例: 5,000）、1万以上は漢字混在OK（例: 3.5兆円）
- **引用の挿入**: 重要な発言・データは `.report__blockquote` で強調する

---

## ソース記載ルール

- **レポート内のすべての事実情報にソースURLを付記すること（例外なし）**
- 形式: 情報の末尾に `より [タイトル](URL)` と記載する
- 1つの情報に複数ソースがある場合は全て記載する
- ソースのない情報はレポートに含めない
- 推測や一般論は「（筆者分析）」と明記する
- ソースの鮮度: 03-search-strategy.mdの鮮度ルールに従う

### ソースの見せ方

- **インラインリンク**: 文中に自然に組み込む（例: 「OpenAIが[GPT-5を発表](URL)した」）
- **末尾参照**: 段落の最後にまとめて記載（例: 「（出典: [記事名](URL)）」）
- **どちらでもよいが、1レポート内では統一する**

---

## アクセシビリティ必須ルール

- テキストのコントラスト比: 最低 **4.5:1**（WCAG AA）
- テーブルの行ホバー: 視認性向上のためハイライト必須
- リンク: 色だけでなく下線でも区別可能にする
- チャート: データテーブルを併記する（スクリーンリーダー対応）
- フォントサイズ: 本文最低 **16px**、注釈最低 **14px**
