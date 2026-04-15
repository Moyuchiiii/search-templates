# awesome-claude-code-toolkit サマリー

> リポジトリ: https://github.com/rohitg00/awesome-claude-code-toolkit
> ⭐ 1,097 | フォーク: 300 | 最終更新: 2026-04-02
> 確認日: 2026-04-06

## 概要

Claude Code 向けの包括的なツールキット集。135のエージェント、35のキュレーション済みスキル（SkillKit経由で400,000以上）、42のコマンド、150+のプラグイン、19のフック、15のルール、7つのテンプレート、8つのMCP設定などを収録している。Claude Codeを使った開発ワークフローをプロダクションレベルに引き上げるためのリソースをワンストップで提供するリポジトリ。

## 主なカテゴリ

### Plugins（150+）

プラグインマーケットプレイス形式で配布。コマンド `/plugin marketplace add <repo>` で導入可能。

- **pro-workflow**（⭐1,400+）: 自己修正メモリ・並列worktree・8種フック・5エージェントを含む実戦的ワークフロー集
- **everything-claude-code**（⭐78,600+）: スキル・instinct・メモリ・セキュリティ・research-first開発を統合したエージェントハーネス最適化システム
- **gstack**（⭐15,000+）: Garry Tanのスタック
- **skills-janitor**: スキルの監査・重複除去・修正・使用状況追跡（コマンド9本、依存関係ゼロ）
- **aws-cost-saver**: 173パターンのAWSコスト最適化スキャナー

### Agents（135体・10カテゴリ）

| カテゴリ | 数 | 代表エージェント |
|---|---|---|
| Core Development | 13 | code-reviewer, architect, debugger |
| Language Experts | 25 | python, typescript, go, rust 等各言語専門 |
| Infrastructure | 11 | kubernetes, terraform, docker |
| Quality Assurance | 10 | tester, security-auditor |
| Data & AI | 15 | data-scientist, ml-engineer, prompt-engineer |
| Developer Experience | 15 | docs-writer, onboarding, dx-optimizer |
| Specialized Domains | 15 | blockchain, mobile, embedded |
| Business & Product | 12 | product-manager, ux-researcher, business-analyst, growth-hacker, sales-engineer |
| Orchestration | 8 | multi-agent-coordinator, workflow-designer |
| Research & Analysis | 11 | market-researcher, competitive-analyst |

### Skills（35 curated + 400,000 via SkillKit）

- TDD、API設計、DBチューニング、Reactパターン、Kubernetes操作など
- SkillKit Marketplace（15,000+スキル）を通じて大量追加可能

### Commands（42本・8カテゴリ）

- Git（7）: コミット・PR・ブランチ管理
- Testing（6）: テスト実行・カバレッジ
- Architecture（6）: 設計レビュー・ADR
- Documentation（5）: ドキュメント生成
- Security（5）: 脆弱性スキャン
- Refactoring（5）: コード整理
- DevOps（5）: デプロイ・CI/CD
- Workflow（3）: 作業フロー管理

### Hooks（19本）

`cc-safe-setup` による一括セットアップ対応。危険コマンドのブロック・通知系フックなど。

### その他

- **Rules（15）**: コーディングルール・セキュリティルール
- **Templates（7）**: CLAUDE.md テンプレート各種
- **MCP Configs（8）**: MCP サーバー設定
- **Contexts（5）**: コンテキストモード切り替え
- **Companion Apps & GUIs（26）**: 可視化・セッション管理ツール

### Ecosystem（51+エントリ）

| 名前 | Stars | 概要 |
|---|---|---|
| claude-mem | ⭐35,900+ | Claude の行動を自動キャプチャ・AI圧縮してコンテキスト注入（2026年2月 GitHub トレンド1位） |
| wshobson/agents | ⭐31,300+ | 112エージェント・16オーケストレーター・146スキル・79ツール（72プラグイン） |
| oh-my-claudecode | ⭐9,900+ | チーム向けマルチエージェントオーケストレーション（19エージェント・28スキル） |
| ccusage | ⭐11,500+ | ローカルJSONLからClaudeの使用量をオフライン分析するCLI |
| ccpm | ⭐7,600+ | GitHub Issues + Git worktreeで並列エージェント実行するプロジェクト管理 |

## factory での活用方法

factoryで `monetization project` を量産する際の各ステップへの対応:

| ステップ | 活用できるリソース |
|---|---|
| `/research`（市場調査） | Research & Analysis エージェント（market-researcher, competitive-analyst）+ exa-search連携 |
| `/select-repos`（技術選定） | Ecosystem一覧・pluginのスター数・メンテ状況を参照して既存実装を再利用 |
| `/plan`（設計） | Orchestration エージェント（multi-agent-coordinator, workflow-designer）、Architecture コマンド6本 |
| `/transform`（実装） | Language Experts・Core Development エージェント、pro-workflow プラグイン（自己修正メモリ付き） |
| `/optimize`（品質・収益化） | Business & Product エージェント（growth-hacker, pricing-strategist, sales-engineer）、QA エージェント |

特に **Business & Product（12エージェント）** は収益化・案件獲得に直結するため、factoryのビジネス判断フェーズで積極活用できる。

## 注目アイテム

- **pro-workflow**: self-correcting memory（自己修正メモリ）が実装されており、長期プロジェクトの文脈保持に有効。factoryの `/transform` フェーズで導入すると品質が上がる
- **everything-claude-code**: research-first 開発フローを強制する仕組み。「自作前に既存調査」というfactoryの原則と完全一致
- **claude-mem**: セッション跨ぎのコンテキスト保持。複数案件を並列で走らせるfactory運用に刺さる
- **ccpm**: GitHub Issues + worktree による並列エージェント管理。大型案件で有効
- **SkillKit Marketplace**: 400,000+スキルのマーケットプレイス。自作スキルの外販・収益化チャネルとしても検討可
- **oh-my-claudecode**: チーム向け19エージェント構成。外注・チームスケールアップ時の参考アーキテクチャになる
- **Business & Product エージェント群**: product-manager / growth-hacker / pricing-strategist / sales-engineer が揃っており、受注判断・提案書作成に転用できる

## 注意点

- **スター数の誇張リスク**: `everything-claude-code`（78,600+）など一部のスター数が突出して大きい。fork starやbot inflationの可能性を疑って実際のコード品質を確認すること
- **XVARY Stock Research セクション**: README中盤に唐突に「XVARY Stock Research」セクションが存在する。本題と無関係なプロモーションコンテンツの可能性があり、参照しないこと
- **SkillKit 400,000+は外部サービス**: 本リポジトリに含まれるわけではなくマーケットプレイス経由。品質はピンキリ
- **メンテ状況**: 最終更新 2026-04-02 と比較的新しい。ただし各プラグイン・エージェントの個別リポジトリのメンテ状況は別途確認が必要
- **Apache-2.0 ライセンス**: 商用利用・改変・再配布は可能だが、ライセンス表記は必要
