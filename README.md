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
├── 00-orchestrator.md       # 全体フロー制御
├── 01-clarify.md            # 要件明確化・サブ質問分解
├── 02-persona.md            # ペルソナ駆動調査（STORM方式）
├── 03-search-strategy.md    # 検索戦略・多言語・鮮度ルール
├── 04-data-collection.md    # データ収集・記録ルール
├── 05-verification.md       # 交差検証・コンセンサス判定
├── 06-analysis.md           # 分析・スコアリング
├── 07-report.md             # レポート生成（HTML）
└── 08-track-record.md       # 予測トラックレコード

AI/prompt.md                 # AI先進国 週次動向調査
invest/prompt.md             # 投資・仮想通貨 勝率ランキング
auto-income/prompt.md        # 自動収益モデル調査
ai-money/prompt.md           # AI自動収益化調査
upwork/prompt.md             # Upwork攻略調査
country.md                   # 対象国リスト（共有）
```

## 使い方

### 既存の調査を実行する

各ドメインの `prompt.md` をClaude Codeに読み込ませて実行する。
共通テンプレート（`_template/`）は `prompt.md` 内の参照指示に従って自動的に読み込まれる。

### 新しい調査を追加する

1. `[調査名]/prompt.md` を作成する
2. `_template/00-orchestrator.md` の「ドメインprompt.mdの必須セクション」に従ってセクションを記述する
3. 実行する

## 参考にしたリポジトリ

| リポジトリ | 手法 | 取り入れた要素 |
|-----------|------|--------------|
| [stanford-oval/storm](https://github.com/stanford-oval/storm) (28k⭐) | ペルソナ駆動調査 | 仮想専門家による多視点質問生成 |
| [assafelovic/gpt-researcher](https://github.com/assafelovic/gpt-researcher) (26k⭐) | コンセンサス検証 | 複数ソース頻度ベースの信頼性判定 |
| [langchain-ai/open_deep_research](https://github.com/langchain-ai/open_deep_research) (10.9k⭐) | パイプライン分離 | 7段階プロンプト×モデルロール分業 |
| [ItzCrazyKns/Perplexica](https://github.com/ItzCrazyKns/Perplexica) (33.4k⭐) | 検索エンジン統合 | マルチソース検索戦略 |
