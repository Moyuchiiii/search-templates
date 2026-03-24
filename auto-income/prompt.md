# 自動収益モデル調査

> 共通テンプレート: `search/_template/` の各フェーズファイルを参照

## 基本情報

- 調査名: 自動収益モデル調査
- 頻度: 随時
- 保存先: `search/auto-income/YYYY-MM-DD/`

## 事前読み込み

- 前回の `track_record.md`（差分追跡用）

## ペルソナ設定

以下の視点を持つ専門家ペルソナを生成すること:

- **AIエージェント開発者**: Claude API・Playwright等を使った自動化の技術的実現性を評価する
- **フリーランサー**: プラットフォーム規約・現場の競合状況を熟知している
- **インディーハッカー**: マイクロSaaS・副業収益モデルの実例に詳しい
- **クリプト/DeFiエンジニア**: 自動取引・アービトラージの技術と法規制を把握している
- **コンテンツマーケター**: SEO・AdSense・アフィリエイト収益の実態を知っている

## 調査カテゴリ

以下の7カテゴリをすべて漏れなく調査すること。

### 1. フリーランスプラットフォーム自動受注

- Upwork, Fiverr, Freelancer, Toptal等での自動提案・自動納品
- 日本: クラウドワークス、ランサーズ、ココナラでの自動化可能性
- どの案件タイプが自動化しやすいか（ライティング、コード生成、データ処理等）
- プラットフォームの規約上、AI自動化は許容されるか
- 実際にやっている人・ボットの事例
- 月間収益の実績・見込み

### 2. バグバウンティ・セキュリティ報酬

- HackerOne, Bugcrowd, Immunefi（Web3）等のバグバウンティ
- GitHub Bounty以外のコード報酬プラットフォーム
- AIエージェントによる脆弱性発見の自動化事例
- 競合状況（他のAIボットの参入度合い）
- 報酬レンジと成功率

### 3. コンテンツ生成・メディア収益

- ブログ/SEO記事の自動生成 → AdSense/アフィリエイト収益
- YouTube台本・サムネイル自動生成 → チャンネル運営
- SNS自動運用 → スポンサー/アフィリエイト
- 電子書籍（Kindle等）の自動執筆・出版
- ストック素材（写真/イラスト/音楽）のAI生成・販売
- 各プラットフォームのAIコンテンツに対するポリシー（BANリスク）

### 4. SaaS/ツール構築・販売

- AIを使ったマイクロSaaSの自動構築
- Chrome拡張機能、Slack Bot等のツール開発・販売
- API-as-a-Service（特定のAI機能をAPI化して課金）
- プロンプトマーケットプレイス（PromptBase等）でのプロンプト販売
- テンプレート・ボイラープレート販売

### 5. トレーディング・アービトラージ

- 仮想通貨の自動取引ボット（DEX/CEXアービトラージ）
- NFT自動フリップ
- ドメイン・デジタル資産の自動売買
- スポーツベッティングのアービトラージ
- リスクと法規制も必ず調査すること

### 6. データ収集・リサーチ代行

- 企業向けリード生成サービス（自動スクレイピング→クレンジング→納品）
- 市場調査レポートの自動作成・販売
- 特定業界のデータ分析サービス
- 競合分析レポートの自動生成
- 不動産・求人等のアグリゲーションサービス

### 7. 新興・ニッチ領域

- AI Agent Marketplace（AgentGPT, CrewAI等のエージェント販売）
- AIチューター/教育コンテンツの自動生成
- 翻訳・ローカライゼーションの自動化
- 法務・契約書レビューの自動化サービス
- AIカスタマーサポートの代行サービス
- その他、2026年に新しく出てきた自動収益モデル

## 検索クエリ

### 英語クエリ

- `"AI agent passive income 2026"`
- `"automated freelancing AI bot 2026"`
- `"make money with AI agents automatically"`
- `"AI bot freelance Upwork Fiverr automated"`
- `"bug bounty automation AI 2026"`
- `"AI content monetization passive income"`
- `"micro SaaS AI automated revenue"`
- `"crypto arbitrage bot AI 2026"`
- `"AI agent marketplace sell agents"`
- `"automated lead generation AI service"`
- `"AI side hustle passive income 2026 reddit"`
- `"Claude API make money automated"`
- `"autonomous AI agent revenue model"`
- `"AI ghostwriting automated publishing"`
- `"automated data collection service AI"`
- `"AI coding agent bounty automated"`
- `"Immunefi bug bounty AI automation"`
- `"sell AI tools Chrome extension revenue"`
- `"AI translation service automated income"`
- `"AI agent that earns money autonomously 2026"`

### 日本語クエリ

- `"AI 自動 不労所得 2026"`
- `"AIエージェント 自動収益 仕組み"`
- `"AI副業 自動化 稼ぐ"`
- `"クラウドワークス AI 自動応募"`
- `"ココナラ AI 自動化"`
- `"AIボット 自動収益 事例"`
- `"マイクロSaaS AI 個人開発 収益"`
- `"AI ブログ 自動 アフィリエイト 収益"`

## スコアリング設定

### 評価軸（8軸）

| 評価軸 | 重み | 評価基準 |
|--------|------|----------|
| 実現性 | 25% | 今の技術スタック（Claude + Python + Playwright）で実装可能か |
| 収益性 | 20% | 月間でどれくらい稼げるか |
| 自動化率 | 15% | 人間の介入がどれくらい不要か（100%=完全自律） |
| 競合度（逆） | 15% | 同じことやってるボットが少ないほど高評価 |
| 持続性 | 10% | 規約変更・BAN・市場飽和で潰れにくいか |
| 初期コスト | 5% | 立ち上げに必要な費用が低いほど高評価 |
| スケーラビリティ | 5% | 横展開・規模拡大が容易か |
| 実例の有無 | 5% | 実際に稼いでいる事例があるか |

### 実現性ランク定義

| ランク | 定義 |
|--------|------|
| S | 今すぐ実装可能。類似の仕組みが既に動いている |
| A | 1-2週間で実装可能。技術的なハードルは低い |
| B | 1ヶ月程度で実装可能。一部検証が必要 |
| C | 実装可能だが課題多い。規約・法的リスクあり |
| D | 理論上は可能だが現実的でない |

## レポートセクション

HTMLレポート（`レポート_YYYY-MM-DD.html`）のセクション構成:

1. **調査サマリー (Executive Summary)**
   - 調査目的と範囲を2-3行で要約
   - 7カテゴリ中で最も有望なカテゴリを明示
   - 「結局どれをやるべきか」を3行以内で結論

2. **自動収益モデル ランキング (Automated Income Model Ranking)**
   - ランキングテーブル（順位・モデル名・カテゴリ・実現性・月間収益見込み・競合度・自動化率・初期コスト・総合スコア・信頼度）
   - 各モデルの詳細（概要・なぜ有望か・リスク・実装イメージ・実例・収益シミュレーション・スコア内訳）

3. **カテゴリ別 詳細分析 (Category Deep Dive)**
   - 7カテゴリそれぞれについて: 市場概況・主要プラットフォーム・技術的実現性・規約/法的リスク・競合状況・実例（ソースURL付き）

4. **実装ロードマップ (Implementation Roadmap)**
   - 上位3モデルの具体的な実装計画（Phase 1〜3）
   - 必要なAPI・サービス一覧・コスト試算

5. **リスクマトリクス (Risk Matrix)**
   - 規約BANリスク・法的リスク・技術的リスク・市場飽和リスク・総合リスクの一覧表
   - 各リスクの詳細説明とソースURL

6. **組み合わせ戦略 (Portfolio Strategy)**
   - 複数モデルのポートフォリオ運用提案
   - 月1万円/5万円/10万円コース別の最適な組み合わせパターン

7. **今後の注目領域 (What to Watch)**
   - 2026年後半に登場しそうな新しい自動収益モデル
   - 技術進化（Claude 5等）で可能になりそうなこと
   - 各国AI規制の動向が自動収益に与える影響
