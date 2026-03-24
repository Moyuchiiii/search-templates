# Search Templates

AIエージェント（Claude Code）による調査・リサーチを体系化したプロンプトテンプレート集。

## 特徴

- **8フェーズパイプライン**: 要件明確化→ペルソナ生成→検索→データ収集→検証→分析→レポート→トラックレコード
- **ペルソナ駆動調査（STORM方式）**: 仮想専門家を複数立てて調査の死角を構造的に排除
- **コンセンサス検証（gpt-researcher方式）**: 複数ソースの一致度で情報の信頼性を判定
- **適応的クエリ拡張**: 初回結果を見て検索クエリを動的に追加・修正
- **モジュラー設計**: 共通テンプレート + ドメイン固有設定で、新しい調査を簡単に追加

## 構成

```
_template/                    # 共通テンプレート（コア）
├── 00-orchestrator.md       # 全体フロー制御（エントリーポイント）
├── 01-clarify.md            # 要件明確化・サブ質問分解
├── 02-persona.md            # ペルソナ駆動調査（STORM方式）
├── 03-search-strategy.md    # 検索戦略・多言語・鮮度ルール
├── 04-data-collection.md    # データ収集・記録ルール
├── 05-verification.md       # 交差検証・コンセンサス判定
├── 06-analysis.md           # 分析・スコアリング
├── 07-report.md             # レポート生成（HTML）
└── 08-track-record.md       # 予測トラックレコード

CLAUDE.md                    # プロジェクト設定（Claude Code用）
.claude/agents/researcher.md # 調査エージェント定義
```

## 8フェーズパイプライン

```
Phase 0: 初期化
  │  ドメインprompt.md + 関連ファイルを読み込む
  ▼
Phase 1: 要件明確化（01-clarify.md）
  │  調査目的をサブ質問に分解 → スコープ定義
  ▼
Phase 2: ペルソナ生成（02-persona.md）
  │  仮想専門家3〜5人が多角的な質問を追加
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
  │  HTML単一ファイルで出力（OLED Dark + Glassmorphism）
  ▼
Phase 8: トラックレコード（08-track-record.md）
     予測の的中率を蓄積・検証
```

## 使い方

### 1. cloneする

```bash
git clone https://github.com/Moyuchiiii/search-templates.git search
cd search
```

### 2. 調査を実行する

Claude Codeを起動して、やりたい調査を指示するだけ：

```
○○について調査して
```

CLAUDE.mdが自動で読み込まれ、テンプレートに沿って調査が実行される。

### 3. 新しい調査テーマを追加する

`[テーマ名]/prompt.md` を作成する：

```markdown
# [調査名]

> 共通テンプレート: `_template/` の各フェーズファイルを参照

## 基本情報
- 調査名: ○○調査
- 頻度: 週1回 / 月1回 / 単発
- 保存先: `[テーマ名]/YYYY-MM-DD/`

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
1. 📊 サマリー
2. 🔍 詳細分析
3. 💡 アクション提案
```

### 出力ファイル

| ファイル | 内容 |
|---------|------|
| `調査結果_YYYY-MM-DD.md` | 生データ（検索ログ・全文記録・検証結果） |
| `レポート_YYYY-MM-DD.html` | 最終レポート（HTMLで開くだけで読める） |
| `track_record.md` | 予測トラックレコード（毎回追記） |

## カスタマイズ

### 任意セクション

prompt.mdに必要に応じて追加できる：

| セクション | 用途 |
|-----------|------|
| `## 事前読み込み` | 調査前に読むべきファイル |
| `## スコアリング設定` | ランキング用の評価軸と重み |
| `## 鮮度ルール` | デフォルトの鮮度基準を上書き |
| `## 文脈連携` | 他の調査レポートとの連携 |

### マルチモデル戦略

| フェーズ | デフォルト | 切り替え条件 |
|---------|----------|------------|
| 探索（Phase 1-4） | Sonnet | 大量の定型転記 → Haiku |
| 分析（Phase 5-6） | Sonnet | 高度な判断 → Opus |
| 生成（Phase 7-8） | Sonnet | 定型更新 → Haiku |

## 参考にしたリポジトリ

| リポジトリ | スター | 取り入れた要素 |
|-----------|-------|--------------|
| [stanford-oval/storm](https://github.com/stanford-oval/storm) | 28k | ペルソナ駆動調査 → `02-persona.md` |
| [assafelovic/gpt-researcher](https://github.com/assafelovic/gpt-researcher) | 26k | コンセンサス検証 → `05-verification.md` |
| [langchain-ai/open_deep_research](https://github.com/langchain-ai/open_deep_research) | 10.9k | 8フェーズパイプライン → `00-orchestrator.md` |
| [ItzCrazyKns/Perplexica](https://github.com/ItzCrazyKns/Perplexica) | 33.4k | マルチソース検索戦略 → `03-search-strategy.md` |
