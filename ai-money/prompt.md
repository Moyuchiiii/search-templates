# AIマネタイズ調査

> 共通テンプレート: `search/_template/` の各フェーズファイルを参照

## 基本情報

- 調査名: AIを活用した自動収益化の調査
- 頻度: 週1回（AI調査・投資調査と同期）
- 保存先: `search/ai-money/YYYY-MM-DD/`
- 調査対象期間: 直近1週間を基本。情報がない場合は「特になし」と記載

## 事前読み込み

調査開始前に以下を全て読み込むこと。

1. `search/country.md` — 対象国リスト（AI規制・市場環境が収益モデルの実現性に影響）
2. `search/AI/` 内の直近レポート — AI先進国の最新動向（新ツール・新サービス・政策変更 → 新しい収益機会のヒント）
3. `search/ai-money/track_record.md` — 過去の予測トラックレコード（前回の予測検証に使用）

## 2軸マトリクス（自動度 × 収益タイプ）

調査した方法は以下の2軸で必ず分類する。

- **自動度**: 🤖 完全自動（放置で稼げる）→ 🔄 半自動（定期的な人間介入）→ 🙋 手動（AIがアシスト）
- **収益タイプ**: 💰 ストック型（資産・仕組みから継続収益）vs ⚡ フロー型（労働対価・都度収益）

## ペルソナ設定

Phase 2（ペルソナ生成）での方向性ヒント。

- AIマネタイズ実践者（個人で月$500〜$5,000稼いでいるエンジニア・フリーランサー）
- プラットフォームリスク評価の専門家（規約・BANリスクに詳しい）
- 自動化ビジネス構築者（AIエージェント・RPAで収益化している起業家）
- 投資・副業コンサルタント（実績ベースで費用対効果を評価できる人物）

## 調査カテゴリ（9カテゴリ）

### カテゴリ1: フリーランスプラットフォーム自動受注（フロー型・半自動〜自動）

AIエージェントがプラットフォーム上の案件を自動検索→提案→納品する仕組み。

**調査項目:**
- Upwork, Fiverr, Freelancer, Toptal等での自動提案・自動納品の事例
- 日本: クラウドワークス、ランサーズ、ココナラでの自動化可能性
- どの案件タイプが自動化しやすいか（ライティング、コード生成、データ処理、デザイン等）
- プラットフォームの規約上、AI自動化は許容されるか（BANリスク）
- 実際にやっている人・ボットの事例と月間収益
- AI活用による単価の変化（AI前 vs AI後の比較データ）

### カテゴリ2: AIプロダクト・SaaS（ストック型・半自動）

AIを組み込んだプロダクトを作って販売する。一度構築すれば継続収益。

**調査項目:**
- 個人〜少人数で作れるAI SaaSの成功事例（MRR、成長率）
- AI Wrapper（既存AIのラッパー）ビジネスの現状と将来性
- マイクロSaaS（ニッチ市場向け小規模SaaS）の事例
- NoCode/LowCodeでAIアプリを作って売る方法
- AIテンプレート・プロンプト販売の市場（PromptBase等）
- Chrome拡張機能、Slack Bot等のツール開発・販売
- API-as-a-Service（特定のAI機能をAPI化して課金）

### カテゴリ3: AIコンテンツ生成・メディア収益（ストック型・半自動〜自動）

AIでコンテンツを生成し、広告・アフィリエイト・販売で収益化する。

**調査項目:**
- AIブログ・SEOサイトの収益事例（Google AI content policyの最新動向含む）
- AI YouTube（台本・ナレーション・動画生成）の収益事例
- AI電子書籍・Kindle出版の現状と収益データ
- AIニュースレター・有料メディアの事例
- SNS運用のAI自動化と収益化（X, Instagram, TikTok等）
- ストック素材（写真/イラスト/音楽）のAI生成・販売
- 各プラットフォームのAIコンテンツに対するポリシー変更（BANリスク）

### カテゴリ4: AIエージェント・自動化ビジネス（ストック型・自動）

AIエージェントを構築して、人間の介入なしに稼ぐ仕組みを作る。

**調査項目:**
- AIエージェントで自動的に収益を生む事例（バウンティハンター、自動トレーディング等）
- Claude Code / Cursor / Devin 等のコーディングAIを使った自動開発の事例
- AIエージェントフレームワーク（LangChain、CrewAI、AutoGen、Claude Agent SDK等）の活用事例
- RPA × AI の組み合わせによる業務自動化ビジネス
- AIエージェントの構築・販売ビジネス（Agent Marketplace）
- 企業向けAI自動化代行サービス

### カテゴリ5: AIトレーディング・アービトラージ（ストック型・自動）

AIを使って投資・トレーディング・アービトラージを自動化する。

**調査項目:**
- AI/LLMを使った自動売買の事例と実績成績
- 仮想通貨の自動取引ボット（DEX/CEXアービトラージ）
- AIによる銘柄分析・スクリーニングの手法
- LLMを使ったセンチメント分析トレーディング
- NFT自動フリップ、ドメイン自動売買
- 個人が使えるAIトレーディングツール・プラットフォーム
- リスクと損失事例（必ず調査すること）
- 法規制（金商法、暗号資産交換業等）

### カテゴリ6: バグバウンティ・OSSバウンティ（フロー型・半自動）

AIを使ってバウンティプラットフォームで報酬を得る。

**調査項目:**
- HackerOne, Bugcrowd, Immunefi（Web3）等のバグバウンティでのAI活用
- GitHub Bounty以外のコード報酬プラットフォーム（Algora等）
- AIエージェントによる脆弱性発見の自動化事例
- 競合状況（他のAIボットの参入度合い、anti-AIゲートの増加）
- 報酬レンジと成功率
- AI PRの受け入れ状況

### カテゴリ7: AI教育・コンサルティング（フロー型・手動〜半自動）

AI活用のノウハウ自体を売る。

**調査項目:**
- AI講座・オンラインコース販売の市場規模と事例
- AI導入コンサルティングの需要と単価
- 企業向けAI研修・ワークショップの事例
- AIコミュニティ・メンバーシップビジネス
- YouTube / ブログでのAI教育コンテンツの収益化

### カテゴリ8: データ収集・リサーチ代行（フロー型〜ストック型・半自動〜自動）

AIエージェントが自動でデータ収集・分析・レポート作成を行い、販売する。

**調査項目:**
- 企業向けリード生成サービス（自動スクレイピング→クレンジング→納品）
- 市場調査レポートの自動作成・販売
- 特定業界のデータ分析サービス
- 競合分析レポートの自動生成
- 不動産・求人等のアグリゲーションサービス
- AIリサーチアシスタントの販売

### カテゴリ9: 新興・ニッチなAIマネタイズ（その他）

上記カテゴリに収まらない新しい稼ぎ方。

**調査項目:**
- AIモデルのファインチューニング受託
- AI × 特定業界（不動産、法律、医療等）のニッチサービス
- 翻訳・ローカライゼーションの自動化サービス
- 法務・契約書レビューの自動化サービス
- AIカスタマーサポートの代行サービス
- AI生成アート・音楽のライセンス販売
- 日本独自のAIマネタイズ機会
- 2026年に新しく出てきた自動収益モデル

## 検索クエリ

各カテゴリの固定クエリ。毎回すべて実行すること。追加クエリは各カテゴリ2〜3本自分で考えて補足する。

### カテゴリ1: フリーランス自動受注
- `"automated freelancing AI bot 2026"` / `"AI bot freelance Upwork Fiverr automated"`
- `"make money with AI freelancing 2026"` / `"AI freelance income proof"`
- `"upwork AI jobs trending 2026"` / `"fiverr AI gigs revenue"`
- `"クラウドワークス AI 案件 2026"` / `"ココナラ AI サービス 自動化"`
- `"Claude API freelance automation"` / `"AI coding assistant freelance productivity"`
- `"AI side hustle income proof 2026"` / `"AI freelance case study revenue"`
- `"freelance platform AI bot ban policy"` / `"upwork AI policy terms of service"`

### カテゴリ2: AIプロダクト・SaaS
- `"AI SaaS indie hacker 2026"` / `"solo founder AI product revenue"`
- `"AI wrapper business viable 2026"` / `"AI wrapper startup revenue"`
- `"micro SaaS AI idea 2026"` / `"AI micro SaaS examples MRR"`
- `"sell AI prompts templates 2026"` / `"prompt marketplace revenue"`
- `"build AI app no code monetize"` / `"AI tool ProductHunt launch revenue"`
- `"Claude API SaaS business"` / `"Anthropic API startup"`
- `"sell AI tools Chrome extension revenue"` / `"AI Slack bot monetize"`
- `"マイクロSaaS AI 個人開発 収益"` / `"AIツール 販売 個人開発"`

### カテゴリ3: AIコンテンツ・メディア
- `"AI generated content monetization 2026"` / `"AI blog income proof"`
- `"AI YouTube channel revenue 2026"` / `"faceless YouTube AI income"`
- `"AI Kindle publishing income 2026"` / `"AI ebook business revenue"`
- `"AI newsletter business model revenue"` / `"AI content farm 2026"`
- `"Google AI content policy 2026"` / `"AI content SEO penalty update"`
- `"AI副業 コンテンツ 収益"` / `"AI ブログ 稼ぐ 2026"`
- `"AI ghostwriting automated publishing"` / `"AI stock photo sell income"`

### カテゴリ4: AIエージェント・自動化
- `"AI agent make money automatically 2026"` / `"AI agent business revenue"`
- `"AI bounty hunter automated income"` / `"AI bug bounty automation success"`
- `"Claude Code autonomous coding income"` / `"AI coding agent revenue"`
- `"AI agent framework business use case 2026"` / `"CrewAI AutoGen business"`
- `"sell AI automation service small business"` / `"AI agent marketplace sell"`
- `"AIエージェント 自動化 収益"` / `"AI自動化 ビジネス 事例"`
- `"autonomous AI agent revenue model 2026"` / `"AI agent that earns money autonomously"`
- `"Claude agent SDK business application"` / `"AI RPA business automation service"`

### カテゴリ5: AIトレーディング
- `"AI trading bot performance 2026"` / `"LLM stock trading results proof"`
- `"AI automated trading individual investor 2026"`
- `"Claude GPT sentiment analysis trading results"` / `"AI crypto trading bot profit"`
- `"crypto arbitrage bot AI 2026 profit"` / `"DEX arbitrage AI automated"`
- `"AI投資 自動売買 成績 2026"` / `"AI株 自動化 利益"`
- `"AI trading risks losses 2026"` / `"AI trading scam warning"`
- `"AI domain flipping automated"` / `"NFT flip bot AI 2026"`

### カテゴリ6: バグバウンティ・OSSバウンティ
- `"AI bug bounty hunting 2026"` / `"automated bug bounty AI success"`
- `"AI open source bounty income"` / `"Algora bounty AI automated"`
- `"Claude Code bounty hunting results"` / `"AI pull request automation"`
- `"anti AI PR GitHub 2026"` / `"AI generated PR acceptance rate"`
- `"Immunefi bug bounty AI automation"` / `"AI coding agent bounty automated"`
- `"bug bounty AI tools 2026"` / `"AIバウンティ 稼ぐ 実績"`

### カテゴリ7: AI教育・コンサルティング
- `"AI consulting business income 2026"` / `"AI consultant freelance revenue"`
- `"sell AI course online income 2026"` / `"AI training business revenue"`
- `"AI workshop corporate training pricing 2026"`
- `"AI community membership revenue"` / `"AI教育 ビジネス 収益 2026"`
- `"teach AI skills monetize"` / `"AI coaching business income"`

### カテゴリ8: データ収集・リサーチ代行
- `"automated lead generation AI service revenue"` / `"AI data collection service business"`
- `"AI market research report sell"` / `"automated data collection service AI 2026"`
- `"AI competitive analysis service business"` / `"AI research assistant monetize"`
- `"AI scraping service legal business"` / `"データ収集 AI サービス ビジネス"`

### カテゴリ9: 新興・ニッチ
- `"unusual ways to make money with AI 2026"` / `"AI money niche"`
- `"AI fine tuning service business revenue"` / `"custom AI model business"`
- `"AI translation service automated income"` / `"AI legal review service"`
- `"AI niche service industry specific 2026"` / `"AI × 業界特化 ビジネス"`
- `"new AI monetization methods 2026"` / `"AI稼ぎ方 最新 2026"`
- `"AI customer support as a service"` / `"AI art music license sell"`

## スコアリング設定

評価軸（8軸）で1〜5点採点し、加重平均 × 20 = 総合スコア（20〜100点）。

| 評価軸 | 重み | 5点 | 1点 |
|--------|------|-----|-----|
| 実現性 | 25% | 今すぐClaude+Python+Playwrightで実装可能。類似の仕組みが稼働中 | 理論上可能だが現実的でない |
| 収益性 | 20% | 月10万円以上が見込める | 月1万円未満、または赤字リスク |
| 自動化率 | 15% | 完全自動（セットアップ後は放置） | 完全手動（AIはただのツール） |
| 競合度（逆） | 10% | 同じことをやっているボット/人が少ない | レッドオーシャン、飽和状態 |
| 持続性 | 10% | 規約変更・BAN・飽和で潰れにくい | いつBANされてもおかしくない |
| スケーラビリティ | 8% | 横展開・規模拡大が容易 | スケールしない |
| 初期コスト（逆） | 7% | 無料〜月数千円で開始可能 | 初期投資が数十万円以上 |
| 実例の有無 | 5% | 収益データ付きの実績事例が複数ある | 事例ゼロ、理論のみ |

**実現性ランク:**

| ランク | 総合スコア | 定義 |
|--------|-----------|------|
| S | 85〜100 | 今すぐ実装可能。類似の仕組みが既に動いている |
| A | 70〜84 | 1-2週間で実装可能。技術的なハードルは低い |
| B | 55〜69 | 1ヶ月程度で実装可能。一部検証が必要 |
| C | 40〜54 | 実装可能だが課題多い。規約・法的リスクあり |
| D | 20〜39 | 理論上は可能だが現実的でない |

## 鮮度ルール（重み倍率付き）

各評価軸のスコアは、根拠となる情報の鮮度倍率を適用して調整する。最終スコアは5点を上限とする。

| 鮮度 | 重み倍率 | 扱い |
|------|---------|------|
| 1ヶ月以内 | ×1.5 | 最優先。レポートの中心に据える |
| 3ヶ月以内 | ×1.3 | 主要な情報として扱う |
| 6ヶ月以内 | ×1.0 | 標準。有用なら記載。日付を明記 |
| 1年以内 | ×0.7 | 背景情報としてのみ。「⚠️ 古い情報」と明記 |
| 1年超 | ×0.3 | 原則使用しない。使う場合は「⚠️ 非常に古い情報」と明記 |

## 信頼度評価基準

情報ソースの信頼度（3段階）:

| ランク | 表示 | 基準 |
|--------|------|------|
| 最高信頼 | ✅ 実績あり | 具体的な収益数字・スクリーンショット・検証済み事例がある |
| 高信頼 | 🔶 有望 | 論理的に成立し、類似事例はあるが直接の実績データが少ない |
| 低信頼 | ⚠️ 未検証 | 煽り系・理論のみ・再現性不明。レポート採用は慎重に |

データ信頼度スコア（スコアリングとは別に各モデルの情報充実度を評価）:

| 信頼度 | 表示 | 基準 |
|--------|------|------|
| ★★★★★ | 最高 | 複数の独立した実績事例あり。収益データも検証済み |
| ★★★★☆ | 高 | 実績事例あり。主要な判断材料は揃っている |
| ★★★☆☆ | 中 | 類似事例はあるが直接の実績データが不足 |
| ★★☆☆☆ | 低 | 情報が限定的。スコアの精度に疑問 |
| ★☆☆☆☆ | 最低 | ほぼ情報なし。評価保留を推奨 |

**検索言語ルール:**
- 英語 + 日本語の2言語で検索。英語を主軸とする
- 日本語では日本市場特有の機会（クラウドワークス、ココナラ等）を調査
- 特定国に関連する場合は現地語も使用（country.md参照）

## レポートセクション

HTML形式で以下の12セクションを出力する。

1. **エグゼクティブサマリー** — 調査ハイライト、「今すぐ始めるべき TOP3」、2軸マトリクス図、前週との差分
2. **AIマネタイズ ランキング TOP20** — ランキングテーブル + 全20方法の根拠詳細（概要・なぜ今有効か・リスク・始め方・コスト・実例・収益シミュレーション・実装イメージ・スコア内訳）
3. **完全自動モデル 詳細分析** — 🤖完全自動〜ほぼ自動の方法に絞って深掘り（実現可能性検証・セットアップ手順・収益データ・落とし穴・コードアーキテクチャ）
4. **カテゴリ別 詳細分析** — 9カテゴリそれぞれの市場概況・主要プラットフォーム・技術的実現性・規約リスク・競合状況・事例・「最もやるべき方法」1つ
5. **国別チャンス分析** — country.md Tier 1国ごとの市場規模・日本からのアクセス可否・特有のブルーオーシャン
6. **実装ロードマップ** — TOP3についてPhase 1（1週目）→ Phase 2（2-3週目）→ Phase 3（4週目〜）の具体的タスク・API一覧・コスト試算・目標収益
7. **リスクマトリクス & 法規制** — 規約BANリスク・法的リスク・技術的リスク・市場飽和リスク（日本の法規制 + プラットフォーム規約ポリシー）
8. **組み合わせ戦略** — 月1万円/5万円/10万円コースの複数モデルポートフォリオ案（配分比率・リスク分散・期待収益レンジ）
9. **優太向けアクションプラン** — 今すぐ（今週中）・短期（1ヶ月）・中期（3ヶ月）に分けた具体的ステップ・ツール・コスト
10. **予測トラックレコード** — 前週の予測レビュー（的中/部分的中/外れ）+ 累積的中率テーブル
11. **今後の注目領域** — 1〜2週間以内に注目すべき動き・新リリース・規制動向・技術進化（各予測にソースURL）
12. **おすすめリソース TOP5** — 今回の調査で特に有益だったソース5つ（URL・おすすめ理由・種別・継続ウォッチ推奨メディア）

**HTMLデザイン要件:**
- 単一ファイル（CSS・JSはすべてインライン埋め込み）、UTF-8
- `search/AI/` 内の直近HTMLレポートのデザインを参考にする（ウェブページ風レイアウト）
- フルワイド背景 + 1280pxコンテンツ幅、固定ナビバー、ヒーローセクション
- 2-3カラムグリッド、OLED Dark + Glassmorphism、SVGアイコン
- 実現性ランクの色分け: S=金, A=緑, B=青, C=黄, D=赤
- 自動度バッジ（🤖/🔄/🙋）、ランキングテーブルはソート可能（JS実装）
- レスポンシブ対応、`@media print` でリンクURL表示

## 文脈連携（AI調査との連携）

- AI週次レポートに含まれる情報を新しい収益機会の発見に活用する
  - 「新しいAIツールXがリリース → Xを使ったサービスの需要が発生」
  - 「EU AI Act施行 → コンプライアンス支援サービスの需要増」
  - 「インドにAI投資集中 → インド向けAIサービスの市場拡大」
- 各国のAI規制動向はプラットフォームBANリスクの評価に組み込む
- country.md Tier 1の国について、AIフリーランス市場規模・規制影響・日本からのアクセス可否・特有の機会を調査する
- 既に検証済み: GitHubバウンティ自動化（競合飽和で収益化困難 — 2026-03時点）
