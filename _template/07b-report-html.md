# Phase 7: レポートHTMLテンプレート

レポート生成時、このHTMLを骨格として使う。
CSSは `07a-report-css.md` のコードブロックを `<style>` タグにコピーすること。

## テーマプリセット

ドメインprompt.mdで `## テーマ` が指定されている場合はそちらを使用する。
未指定の場合は **light（デフォルト）** を適用する。

### プリセット一覧

| テーマ名 | 説明 | 変更するCSS変数 |
|---------|------|----------------|
| **light**（デフォルト） | 白ベース。汎用レポート | `:root` そのまま |
| **dark** | ダークテーマ。tech系・夜間閲覧向け | `--color-bg: #0f0f0f` 等、`prefers-color-scheme` ブロックを参照 |
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

## HTMLテンプレート

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>レポートタイトル</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500;700;900&display=swap" rel="stylesheet">
  <style>
    /* 07a-report-css.md のCSSをここに貼る */
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

    <!-- ヒーロー（フルワイド背景） -->
    <div class="report__hero">
      <div class="report__container">
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
    </div>

    <!-- 目次 -->
    <div class="report__container">
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

          <!-- 差分バッジ例（週次レポートで使用） -->
          <span class="report__badge report__badge--new">新規</span>
          <span class="report__badge report__badge--changed">変化</span>
          <span class="report__badge report__badge--unchanged">継続</span>
          <span class="report__badge report__badge--gone">消失</span>
        </div>
      </div>
    </section>

    <!-- 差分表示テーブル例（週次レポート用） -->
    <section class="report__section" id="diff">
      <div class="report__section-inner">
        <p class="report__section-label">前回比</p>
        <h2 class="report__section-title">スコア変動サマリー</h2>
        <div class="report__table-wrapper">
          <table class="report__table">
            <thead>
              <tr>
                <th>項目</th>
                <th>今回スコア</th>
                <th>前回比</th>
                <th>状態</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>サンプルA</td>
                <td><span class="report__diff-highlight">82</span> <span class="report__diff-arrow--up">↑12</span></td>
                <td>+12</td>
                <td><span class="report__badge report__badge--changed">変化</span></td>
              </tr>
              <tr>
                <td>サンプルB（新規）</td>
                <td><span class="report__diff-highlight">70</span></td>
                <td>—</td>
                <td><span class="report__badge report__badge--new">新規</span></td>
              </tr>
              <tr>
                <td>サンプルC</td>
                <td><span class="report__diff-highlight">58</span> <span class="report__diff-arrow--down">↓5</span></td>
                <td>-5</td>
                <td><span class="report__badge report__badge--unchanged">継続</span></td>
              </tr>
              <tr>
                <td>サンプルD（消失）</td>
                <td>—</td>
                <td>—</td>
                <td><span class="report__badge report__badge--gone">消失</span></td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- スコア推移グラフ例（SVG折れ線） -->
    <section class="report__section" id="trend-chart">
      <div class="report__section-inner">
        <p class="report__section-label">スコア推移</p>
        <h2 class="report__section-title">週次スコア推移グラフ</h2>
        <div class="report__chart-line">
          <p class="report__chart-line-title">過去6週間のスコア推移</p>
          <!--
            グラフの座標系: viewBox="0 0 500 220"
            プロット領域: x: 50〜470、y: 20〜170
            X軸: 週ラベル（等間隔）
            Y軸: スコア（0〜100）
            グリッド線: Y=20,70,120,170（スコア100,75,50,25に相当）
            データ例: week1=55, week2=62, week3=70, week4=65, week5=78, week6=82
            座標変換: x = 50 + (week_index / 5) * 420, y = 170 - (score / 100) * 150
          -->
          <svg viewBox="0 0 500 220" aria-label="週次スコア推移グラフ" role="img">
            <defs>
              <!-- グラデーション（塗りつぶしエリア用） -->
              <linearGradient id="chart-gradient" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#4f46e5" stop-opacity="0.4"/>
                <stop offset="100%" stop-color="#4f46e5" stop-opacity="0"/>
              </linearGradient>
            </defs>

            <!-- グリッド線 -->
            <line class="chart-grid-line" x1="50" y1="20" x2="470" y2="20"/>
            <line class="chart-grid-line" x1="50" y1="57" x2="470" y2="57"/>
            <line class="chart-grid-line" x1="50" y1="95" x2="470" y2="95"/>
            <line class="chart-grid-line" x1="50" y1="132" x2="470" y2="132"/>
            <line class="chart-grid-line" x1="50" y1="170" x2="470" y2="170"/>

            <!-- Y軸ラベル -->
            <text class="chart-axis-label" x="42" y="23" text-anchor="end">100</text>
            <text class="chart-axis-label" x="42" y="60" text-anchor="end">75</text>
            <text class="chart-axis-label" x="42" y="98" text-anchor="end">50</text>
            <text class="chart-axis-label" x="42" y="135" text-anchor="end">25</text>
            <text class="chart-axis-label" x="42" y="173" text-anchor="end">0</text>

            <!-- X軸ラベル（6週分） -->
            <text class="chart-axis-label" x="50"  y="192" text-anchor="middle">W1</text>
            <text class="chart-axis-label" x="134" y="192" text-anchor="middle">W2</text>
            <text class="chart-axis-label" x="218" y="192" text-anchor="middle">W3</text>
            <text class="chart-axis-label" x="302" y="192" text-anchor="middle">W4</text>
            <text class="chart-axis-label" x="386" y="192" text-anchor="middle">W5</text>
            <text class="chart-axis-label" x="470" y="192" text-anchor="middle">W6</text>

            <!-- 塗りつぶしエリア -->
            <polygon class="chart-area"
              points="50,87 134,77 218,65 302,72 386,53 470,47 470,170 50,170"/>

            <!-- 折れ線 -->
            <polyline class="chart-line"
              points="50,87 134,77 218,65 302,72 386,53 470,47"/>

            <!-- データポイント + ラベル（値: 55,62,70,65,78,82） -->
            <circle class="chart-dot" cx="50"  cy="87"/>
            <text class="chart-point-label" x="50"  y="78">55</text>

            <circle class="chart-dot" cx="134" cy="77"/>
            <text class="chart-point-label" x="134" y="68">62</text>

            <circle class="chart-dot" cx="218" cy="65"/>
            <text class="chart-point-label" x="218" y="56">70</text>

            <circle class="chart-dot" cx="302" cy="72"/>
            <text class="chart-point-label" x="302" y="63">65</text>

            <circle class="chart-dot" cx="386" cy="53"/>
            <text class="chart-point-label" x="386" y="44">78</text>

            <!-- 最新ポイントは強調（最新週） -->
            <circle cx="470" cy="47" r="6" fill="#4f46e5" stroke="white" stroke-width="2.5"/>
            <text class="chart-point-label" x="470" y="38" style="fill:#4f46e5;">82</text>
          </svg>

          <!-- 凡例 -->
          <div class="report__chart-legend">
            <div class="report__chart-legend-item">
              <span class="report__chart-legend-dot"></span>
              スコア推移
            </div>
          </div>
        </div>

        <!-- アクセシビリティ用データテーブル（スクリーンリーダー対応） -->
        <details style="margin-top: 16px;">
          <summary style="font-size: 13px; color: var(--color-text-sub); cursor: pointer;">データテーブルで見る</summary>
          <div class="report__table-wrapper" style="margin-top: 8px;">
            <table class="report__table">
              <thead>
                <tr><th>週</th><th>スコア</th><th>前週比</th></tr>
              </thead>
              <tbody>
                <tr><td>W1</td><td>55</td><td>—</td></tr>
                <tr><td>W2</td><td>62</td><td><span class="report__diff-arrow--up">↑7</span></td></tr>
                <tr><td>W3</td><td>70</td><td><span class="report__diff-arrow--up">↑8</span></td></tr>
                <tr><td>W4</td><td>65</td><td><span class="report__diff-arrow--down">↓5</span></td></tr>
                <tr><td>W5</td><td>78</td><td><span class="report__diff-arrow--up">↑13</span></td></tr>
                <tr><td>W6</td><td>82</td><td><span class="report__diff-arrow--up">↑4</span></td></tr>
              </tbody>
            </table>
          </div>
        </details>
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
