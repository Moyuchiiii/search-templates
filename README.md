# 🔍 Search Templates

**AIエージェントによる深い調査を、テーマを伝えるだけで。**

ChatGPTやPerplexityでは得られない深さ — 30以上の検索クエリ、5人の仮想専門家ペルソナ、交差検証、スコアリング付きランキング、WebサイトにそのままON可能なHTMLレポートを自動生成。

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

---

## 特徴

- **テーマ名だけで調査開始** — prompt.md が存在しない新規テーマは自動生成される。ファイルを手動で作る必要はない
- **8フェーズの体系的な調査パイプライン** — STORM方式のペルソナ駆動調査、コンセンサス検証、適応的クエリ拡張を順次実行
- **白ベースのモダンHTMLレポート** — Apple / Linear / Notion 風のクリーンデザイン。ダークモード自動対応。Webサイトにそのまま組み込める
- **週次調査の差分追跡・スコア推移** — 前回比較バッジ、予測トラックレコードを自動更新
- **Claude Code + MCP で動作** — Exa / Firecrawl があるとより深い検索が可能。なくても通常Web検索で動作する

---

## クイックスタート

```bash
# 1. リポジトリをクローン
git clone https://github.com/Moyuchiiii/search-templates.git
cd search-templates

# 2. Claude Code で開く
claude

# 3. 調査を指示する（prompt.md は自動生成される）
```

Claude Code を起動したら、調査したいテーマをそのまま伝えるだけ：

```
> 「AI自動化エージェンシーについて調査して」
```

### 前提条件

| 項目 | 必須 | 備考 |
|------|------|------|
| Claude Code | ✅ 必須 | 最新版推奨 |
| Exa MCP | オプション | より深いWeb検索が可能 |
| Firecrawl MCP | オプション | Webページの全文取得に対応 |

---

## サンプル出力

出力レポートのイメージは [examples/sample-report.html](examples/sample-report.html) を参照。

> スクリーンショットは後で追加予定。

---

## テンプレート構成

```
_template/                    # 共通テンプレート（コア）
├── 00-orchestrator.md       # 全体フロー制御（エントリーポイント）
├── 00a-generate-prompt.md   # prompt.md 自動生成（新規テーマ用）
├── 01-clarify.md            # 要件明確化・サブ質問分解
├── 02-persona.md            # ペルソナ駆動調査（STORM方式）
├── 03-search-strategy.md    # 検索戦略・多言語・鮮度ルール
├── 04-data-collection.md    # データ収集・記録ルール
├── 05-verification.md       # 交差検証・コンセンサス判定
├── 06-analysis.md           # 分析・スコアリング
├── 07-report.md             # レポート生成（HTML）
└── 08-track-record.md       # 予測トラックレコード

CLAUDE.md                    # プロジェクト設定（Claude Code用）
```

### フェーズ詳細

| フェーズ | ファイル | 内容 |
|---------|---------|------|
| 0 | `00-orchestrator.md` | 全体フロー制御・並列実行ルール |
| 0.5 | `00a-generate-prompt.md` | prompt.md 自動生成（新規テーマ用） |
| 1 | `01-clarify.md` | 要件明確化・サブ質問分解 |
| 2 | `02-persona.md` | ペルソナ駆動調査（STORM方式） |
| 3 | `03-search-strategy.md` | 検索戦略・多言語・鮮度・MCP連携 |
| 4 | `04-data-collection.md` | データ収集・記録ルール |
| 5 | `05-verification.md` | 交差検証・コンセンサス判定 |
| 6 | `06-analysis.md` | 分析・スコアリング・市場分析 |
| 7 | `07-report.md` | レポート生成（HTML・テーマ・品質ルール） |
| 8 | `08-track-record.md` | 予測トラックレコード |

### 8フェーズパイプライン

```
Phase 0: 初期化
  │  ドメイン prompt.md + 関連ファイルを読み込む
  ▼
Phase 1: 要件明確化（01-clarify.md）
  │  調査目的をサブ質問に分解 → スコープ定義
  ▼
Phase 2: ペルソナ生成（02-persona.md）
  │  仮想専門家 3〜5人が多角的な質問を追加
  ▼
Phase 3: 検索実行（03-search-strategy.md）
  │  多言語検索 + 適応的クエリ拡張 ← 並列実行可
  ▼
Phase 4: データ収集（04-data-collection.md）
  │  生データを構造化して記録（全文・省略禁止）
  ▼
Phase 5: 検証（05-verification.md）
  │  交差検証 + コンセンサス判定 + 反証チェック
  ▼
Phase 6: 分析（06-analysis.md）
  │  情報圧縮 → スコアリング → トレンド分析
  ▼
Phase 7: レポート生成（07-report.md）
  │  HTML 単一ファイルで出力（白ベース、ダークモード自動対応）
  ▼
Phase 8: トラックレコード（08-track-record.md）
     予測の的中率を蓄積・検証
```

---

## カスタマイズ

### prompt.md を手動で作る

`[ドメイン名]/prompt.md` を作成して以下の形式で記述する。
サンプルは `_template/example-prompt.md` を参照。

```markdown
# [調査名]

> 共通テンプレート: `_template/` の各フェーズファイルを参照

## 基本情報
- 調査名: ○○調査
- 頻度: 週1回 / 月1回 / 単発
- 保存先: `[ドメイン名]/YYYY-MM-DD/`

## ペルソナ設定
1. **専門家A** — ○○の視点
2. **専門家B** — △△の視点
3. **懐疑派** — リスク・反証を指摘

## 調査カテゴリ
1. カテゴリ1: ○○
2. カテゴリ2: △△

## 検索クエリ
- `"検索クエリ1"`
- `"検索クエリ2"`

## レポートセクション
1. エグゼクティブサマリー
2. ランキング・比較
3. 詳細分析
4. アクション提案
```

### CSS変数でレポートデザインを変更する

`07-report.md` の CSS ブロック内 `:root` の変数を変更するだけでテーマを変更できる。

```css
:root {
  --color-accent: #4f46e5;   /* インディゴ → 好きな色に変更可 */
  --max-width: 960px;        /* 読み幅 */
  --card-radius: 12px;       /* カード角丸 */
}
```

---

## 取り込み元

### 公開リポジトリ

| リポジトリ | スター | 取り入れた要素 |
|-----------|-------|--------------|
| [stanford-oval/storm](https://github.com/stanford-oval/storm) | 28k | ペルソナ駆動調査 → `02-persona.md`, `00-orchestrator.md` |
| [assafelovic/gpt-researcher](https://github.com/assafelovic/gpt-researcher) | 26k | 適応的クエリ拡張 → `03-search-strategy.md`, コンセンサス検証 → `05-verification.md` |
| [langchain-ai/open_deep_research](https://github.com/langchain-ai/open_deep_research) | 10.9k | 情報圧縮・構造化 → `06-analysis.md` |
| [ItzCrazyKns/Perplexica](https://github.com/ItzCrazyKns/Perplexica) | 33.4k | マルチソース検索戦略 → `03-search-strategy.md` |

### Claude Code スキル

| スキル | 取り入れた要素 |
|--------|--------------|
| deep-research（firecrawl + exa MCP） | MCP連携による検索強化 → `03-search-strategy.md` |
| market-research | 市場分析フレームワーク（トップダウン+ボトムアップ）→ `06-analysis.md` |
| ui-ux-pro-max | デザインシステム生成・チャート選定 → `07-report.md` |
| article-writing | 文章構造ルール（逆ピラミッド等）→ `07-report.md` |
| dispatching-parallel-agents | 並列エージェントディスパッチ → `00-orchestrator.md` |
| theme-factory | プリセットテーマ・カスタムテーマ → `07-report.md` |

---

## ライセンス

MIT — 詳細は [LICENSE](./LICENSE) を参照。
