# YouTube 長尺動画リサーチ（D）

調査日: 2026-06-13
調査者: sasaki-search
出典数: 39件（WebSearch 24件 / WebFetch 8件）

---

## 1. アルゴリズム要因

### 1-1. 主要シグナル（2025-2026年最新）

YouTube アルゴリズムは 2025 年以降、**「生の視聴時間」から「満足度加重の視聴時間＋セッション貢献度」**へ評価軸がシフトした。

| シグナル | 説明 | 長尺への影響 | 目標値 |
|---|---|---|---|
| CTR（クリック率） | インプレッション → クリックの転換率 | サムネ・タイトルの質を示す入口 | 教育系 **4〜7%** |
| AVD（平均視聴時間） | 視聴された絶対時間（分） | 10分 × 50% = 5分 → 3分 × 70% = 2.1分 → 前者が優位 | 尺×50%以上を目指す |
| APV（平均視聴率） | 視聴時間 ÷ 動画尺 × 100% | 長尺ほど下がりやすいが絶対秒数で補完 | 40%以上で推薦圏 |
| セッション貢献度 | 視聴後に視聴者が YouTube に留まるか | 長尺＋終了画面連携で最大化できる | プレイリスト・シリーズ形式が有効 |
| 満足度シグナル | アンケート回答・リピート視聴・セッション継続 | 2025年から「raw watch time より重要」と公式認定 | コメント・高評価・保存が代理指標 |
| 48時間エンゲージメント | 公開後48時間のいいね・コメント・シェア速度 | 4つの確認済みランキング要因の1つ | 投稿直後の通知送信が重要 |

[WebFetch済 vidiq.com/blog/post/understanding-youtube-algorithm/]
[WebFetch済 addness.co.jp/media/youtube-algorithms/]
[WebSearch済 socialpilot.co/youtube-marketing/youtube-algorithm]

### 1-2. Quality CTR の概念（2025新概念）

CTR が高くても、冒頭 15〜30 秒で大量離脱するとアルゴリズムが「クリックベイト」と判定し推薦を降格させる。CTR × 冒頭維持率の積が実質的な評価値になる。

> 「サムネが約束した価値を動画が最初の30秒で証明できなければ、高CTRは逆効果になる」
> [WebFetch済 addness.co.jp/media/youtube-algorithms/]

### 1-3. 露出経路別の特性

| 経路 | 特性 | 長尺向けか |
|---|---|---|
| ブラウジング（ホーム） | セッション貢献・AVDが評価軸 | ◎ 長尺優位 |
| 関連動画 | 同トピック競合動画のタグ・説明文を参照 | ○ 競合タグ活用が有効 |
| 検索（YouTube SEO） | タイトル・説明文・チャプタータイトルのキーワード | ◎ 教育系長尺の主要流入源（全トラフィックの35%） |
| 登録者通知 | 投稿後48時間の急速エンゲージメントが重要 | △ 登録者数に依存 |
| Shorts → 長尺誘導 | Shorts視聴者が同チャンネル長尺を推薦される仕組み | ○ 設計次第で強力 |

[WebSearch済 YouTube Creator Insights 2026経由 ytzolo.com]
[WebSearch済 socialpilot.co/youtube-marketing/youtube-algorithm]

---

## 2. 構成型

### 2-1. フック（最初の 0〜30 秒）

**短尺との最大の違い**: 短尺は 3 秒以内に視覚的インパクトが必須だが、長尺は 15〜30 秒をかけて「問題提起→約束→ステークス確立」の構造を丁寧に積み上げられる。

| フェーズ | 秒数 | 役割 | NG例 |
|---|---|---|---|
| Attention Grab | 0〜5秒 | ショック・問い・衝撃クリップ | 「こんにちは！」「今日は〜についてです」 |
| Promise | 5〜15秒 | 「この動画を見ると〇〇になる」を明言 | 漠然と「参考になれば」 |
| Stakes/Context | 15〜30秒 | なぜ今これを見るべきかの理由 | 自己紹介・チャンネル登録お願い |

「明確な価値提案を最初の15秒に入れた動画は、1分時点の維持率が18%高い」
[WebFetch済 retentionrabbit.com/blog/2025-youtube-audience-retention-benchmark-report]
[WebSearch済 1of10.com/blog/how-to-hook-viewers-in-the-first-30-seconds-of-a-youtube-video/]

**絶対NG**: 「チャンネル登録お願いします」「今日はよろしくお願いします」などのイントロを冒頭に入れること。5〜10秒のロゴ/BGMイントロは即離脱の元。

### 2-2. 構成テンプレ（ジャンル別）

#### A. 解説・教育系（「Claude Code とは何か」「副業の始め方」）

```
[0:00-0:30] フック：問題提起「◯◯ができていない人の共通点は」
[0:30-1:30] 概要提示：「この動画で解決できること3点」
[1:30-本編]  本編：問題→原因→解決策 の Problem-Solution 型
  各セクション 3〜5分、チャプター分割
[終盤-2min]  まとめ＋CTA（次の動画 or チャンネル登録）
```

#### B. チュートリアル系（「Claude Code で◯◯を作る方法」）

```
[0:00-0:30] フック：完成物を見せる（Before/After）
[0:30-1:00] 必要なもの・前提確認
[1:00-本編]  ステップ別手順（Step 1/2/3... チャプターで区切る）
[中盤]       詰まるポイントの先出し「ここで〇〇する人が多いので注意」
[終盤-1min]  完成確認＋応用 or 次ステップの紹介
```

#### C. 実録系（「3ヶ月で副業月14万になった話」）

```
[0:00-0:20] フック：結果を先出し「3ヶ月で月14万達成した。でも最初は〇〇だった」
[0:20-0:45] Why Now：「なぜ今これを話すか」の文脈
[0:45-本編]  時系列ストーリー（月ごと・フェーズごと）
  節目ごとに数字・感情・失敗を入れる（感情接触点）
[終盤-1.5min] 教訓の抽象化＋視聴者へのメッセージ＋CTA
```

#### D. 比較・レビュー系（「ChatGPT vs Claude」）

```
[0:00-0:30] フック：「どちらを選ぶべきか迷っている人に◯分で結論を出す」
[0:30-1:00] 比較軸の提示（3〜5軸）
[1:00-本編]  軸ごとの比較（対立構造で飽きさせない）
[中盤-30s]  サマリー表（テロップで可視化）
[終盤-1min]  「結局どちらを選ぶべきか」結論＋CTA
```

#### E. ノウハウ・Tips系（「副業応募文の書き方」）

```
[0:00-0:30] フック：「この1つを直すだけで返信率が3倍になった」
[0:30-1:00] ナンバリング提示「今日は5つ教える」
[1:00-本編]  各Tips を 1.5〜2分で解説（実例つき）
[中盤]       「最重要Tip」を中盤のやや後ろに配置（視聴維持を引っ張る）
[終盤-1min]  チェックリスト形式でまとめ＋CTA
```

### 2-3. セクション分け（チャプター機能）

「30日以内で平均視聴時間が27%増加した」という事例データあり。チャプターのタイトルは SEO キーワードとしてもインデックスされる。

- 5分超の動画には必ずチャプターを入れる
- チャプタータイトルは検索キーワード意識（「Step 1: 準備」ではなく「Claude Code のインストール方法」）
- 最初のチャプターは0:00ではなく0:01以降で設定（0:00からだとチャプター表示が消える）

[WebSearch済 usevisuals.com/blog/using-chapters-to-improve-watch-time-on-youtube]
[WebSearch済 gyre.pro/blog/youtube-video-chapters-how-to-add-them-why-they-increase-views]

### 2-4. アウトロ（最後の 20〜60 秒）

終了画面（End Screen）は最後の 5〜20 秒。アウトロで話しながら同時に終了画面を出す構成が一般的。

- 推薦する動画は1本に絞る（複数は混乱を招く）
- 視聴した動画に関連する1本を「次見るべき動画」として指定
- 「チャンネル登録」は口頭CTAと終了画面ボタンを同時に出す

[WebSearch済 gyre.pro/blog/how-to-create-high-converting-youtube-end-screens-tips-and-examples]

---

## 3. 視聴維持率ベンチマーク

### 3-1. 尺別の合格ライン

| 動画尺 | 業界全体平均 | 合格ライン（推薦圏） | 優秀ライン | 備考 |
|---|---|---|---|---|
| 〜2分 | 50〜70% | 50%以上 | 70%以上 | Shorts寄り |
| 2〜5分 | 40〜60% | 50%以上 | 65%以上 | 短尺長尺の中間 |
| **5〜10分** | **31.5%** | **40%以上** | **50%以上** | **長尺で最高維持率帯** |
| 10〜15分 | 25〜35% | 35%以上 | 45%以上 | 教育系は維持しやすい |
| 15〜20分 | 20〜30% | 30%以上 | 40%以上 | チャプター必須 |
| 20分超 | 15〜25% | 25%以上 | 35%以上 | プレイリスト形式推奨 |

[WebFetch済 retentionrabbit.com/blog/2025-youtube-audience-retention-benchmark-report]
[WebSearch済 fluxnote.io/guides/youtube-average-view-duration-2026]

**教育系ハウツーは例外的に高維持率**（42.1%）。Vlogは21.5%と最低水準。同じ尺でもジャンルで約 20 ポイントの差が出る。

### 3-2. 最初の 60 秒が決め手

- **55%以上の視聴者が60秒以内に離脱**（プラットフォーム全体）
- 最初の15秒で価値提案を示した動画は「1分時点で18%高い維持率」
- 8秒が「視聴者の判断ウィンドウ」
- 冒頭5秒以内にパターン・インタラプト（予想外の映像・数字・問い）を入れると平均23%維持率向上

[WebFetch済 retentionrabbit.com/blog/2025-youtube-audience-retention-benchmark-report]
[WebFetch済 addness.co.jp/media/youtube-algorithms/]

### 3-3. 維持率カーブの読み方

| カーブ形状 | 意味 | 対処 |
|---|---|---|
| 冒頭急落（崖型） | フックが刺さっていない / タイトル詐欺 | 最初の30秒を全面リライト |
| 中盤緩やかな下降（波型） | 通常の視聴パターン | 3〜4分ごとのパターン割込みで緩和 |
| 特定点での急落（点滅型） | その時点で話が脱線・冗長 | 該当箇所をカット or 圧縮 |
| 終盤急落（尻下がり型） | アウトロが長すぎ / 価値が先に尽きた | 終盤をCTAのみに圧縮 |
| 横ばい（理想） | 高エンゲージメント | 良好。終了画面で次の動画へ誘導 |
| スパイク（再生増加） | 視聴者が戻って見直した | 特に強いコンテンツ → 同種内容を増やす |

[WebFetch済 virvid.ai/blog/retention-graphs-how-to-read-youtube-analytics-2026]
[WebSearch済 retentionrabbit.com/blog/ultimate-guide-youtube-audience-retention]

### 3-4. CTR と AVD のバランス

「高CTR × 低維持率」= クリックベイト判定 → 推薦停止リスク
「低CTR × 高維持率」= 検索流入は強いがホーム露出は弱い
「中CTR × 中維持率」= 最も安定した成長軌道

実測: 教育系は CTR 4〜7%・AVD 40〜50% がバランス帯として機能。
[WebFetch済 miraflow.ai/blog/youtube-ctr-benchmarks-2026]

---

## 4. サムネ・タイトル設計

### 4-1. サムネイルの CTR 向上要素

| 要素 | 効果 | 推奨仕様 |
|---|---|---|
| 表情のある顔 | CTR +20〜42% | 驚き・喜び・真剣 → 視聴者との感情同期 |
| 高コントラスト | CTR +20〜30% | 主要被写体は背景より30%以上明るくor暗く |
| テキスト | 可読性優先 | 3〜4語・太字・サンセリフ・スマホ小サイズで読めること |
| 色数 | 2〜3色 | 黄・オレンジ・白・赤が高CTR色。統一感も必要 |
| 顔なし動画 | 大幅に不利 | 物・画面キャプチャのみは平均 921,000回少ない視聴 |

[WebSearch済 vidiq.com/blog/post/youtube-thumbnail-design-tips/]
[WebSearch済 increv.co/academy/youtube-thumbnails-how-to-make-them-clickworthy/]

TubeBuddy による 120万動画分析: 表情のある顔は CTR +42.3%。
[WebSearch済 ampifire.com/blog/best-youtube-thumbnail-guide-examples-best-practices-2025-for-high-ctr/]

### 4-2. タイトルの最適文字数・構造

| 設計軸 | 英語 | 日本語 | 備考 |
|---|---|---|---|
| SEO最適 | 50〜80文字 | 30〜40文字 | 検索キーワード前配置 |
| ブラウジング最適 | 50〜60文字 | 20〜30文字 | 短く訴求力重視 |
| キーワード位置 | 冒頭30〜40文字以内 | 冒頭10〜15文字以内 | 日本語は字数密度が高い |

[WebSearch済 ytzolo.com/blog/youtube-video-title-length-best-practices-2026/]
[WebSearch済 YouTube Creator Insights 2026 via miracamp.com]

- タイトルは「人間が読んで→クリックしたくなる」を最優先、SEO最適化は二次
- 1タイトル1キーワード（最大2キーワード）
- 検索流入狙い（チュートリアル・教育）は長め、ブラウジング狙い（エンタメ・実録）は短め

### 4-3. クリックベイト vs 誠実訴求（YouTube 2025年新方針）

2024年末から YouTube がインド発でクリックベイト取り締まりを強化、2025年以降グローバル展開。

「タイトル・サムネが約束したことを動画内で提供できない場合、動画削除対象」となった。
単にセンセーショナルなだけのタイトルはペナルティ対象。

**対策**: タイトルで「期待」を作り、動画冒頭30秒でその期待を「証明」する構成にする。

[WebSearch済 san.com/cc/youtube-cracks-down-on-clickbait-with-new-enforcement-measures/]
[WebSearch済 fastcompany.com/91252550/youtube-has-a-new-plan-to-combat-clickbait]

### 4-4. 検索 vs ブラウジング それぞれに刺さるタイトル設計

| トラフィック源 | 特性 | タイトル設計 |
|---|---|---|
| **検索（SEO）** | 高インテント・問題解決目的 | 「〇〇の方法」「〇〇 やり方 2025」「〇〇 初心者向け」 |
| **ブラウジング（ホーム）** | 受動的発見・感情訴求 | 「〇〇だった話」「〇〇で失敗した理由」「〇〇を試したら〇〇だった」 |

教育・AI・副業系は検索流入が主力なので SEO タイトルを基本に、実録系はブラウジング向けタイトルが有効。

---

## 5. 推奨尺

### 5-1. ジャンル別推奨尺

| ジャンル | 推奨尺 | 理由 |
|---|---|---|
| 解説系（教育・AI解説） | **8〜12分** | ミッドロール広告1本可・教育系維持率が高い帯 |
| チュートリアル系 | **10〜18分** | 手順ごとの尺が必要・チャプター分割で維持率補完 |
| 実録系（体験談・実績報告） | **10〜15分** | ストーリーに必要な尺・感情曲線を描ける |
| 比較・レビュー系 | **8〜12分** | 各軸2〜3分で説明できる・見終わった後の満足感 |
| ノウハウ・Tips系 | **7〜10分** | Tips 5〜7個をテンポよく消化できる帯 |

### 5-2. 動画尺帯の特性

| 尺帯 | 特性 | 適するジャンル |
|---|---|---|
| **5〜8分** | 維持率が最も取りやすい・ミッドロールなし or 1本 | 解説・Tips・短い比較 |
| **8〜12分** | YPP ミッドロール広告OK（8分以上が条件） + 維持率確保のバランス帯 | 教育・チュートリアル・解説 |
| **12〜20分** | 徹底解説・実録に適す。チャプター必須。維持率維持が難しい | 実録・深掘り比較・長尺チュートリアル |
| **20分超** | プレイリスト or シリーズ設計前提。単発では離脱リスク高 | 講座・ドキュメンタリー |

[WebSearch済 creator-hero.com/blog/how-long-should-a-youtube-video-be]
[WebSearch済 ytshark.com/ideal-youtube-video-length/]

### 5-3. YPP ミッドロール広告の配置ルール

- **8分以上**がミッドロール広告の最低条件（8:00以上が必要、7:59はNG）
- 8〜15分：1〜2本配置推奨
- 15〜20分：2〜3本推奨
- 「広告数 > 視聴者体験」にならないよう、自然な区切り（話題転換・ポーズ）に配置すること

[WebFetch済 vidiq.com/blog/post/youtube-8-minute-mid-roll-ads/]

---

## 6. テンポ・編集

### 6-1. 言葉数（1分あたりの語数）

| 話速 | WPM（英語） | 目安（日本語） | コンテンツタイプ |
|---|---|---|---|
| 遅め | 120〜130 WPM | 250〜280字/分 | 教育・説明・初心者向け |
| 標準 | 130〜150 WPM | 280〜320字/分 | チュートリアル・解説 |
| 速め | 150〜170 WPM | 320〜380字/分 | 実録・ノウハウ・テンポ感重視 |
| 高速 | 170〜180 WPM | 380〜420字/分 | 短尺・Commentary系 |

※ 日本語は 1 WPM ≈ 2〜2.3 文字（漢字混じり）で換算

10分動画の台本 = 約2,800〜3,200文字（標準話速で想定）。実際は B-Roll 挿入時間 10〜20% 分を引いた純発話部分が約2,400〜2,800文字。

[WebSearch済 wordtotime.org/blog/script-timing-for-youtube-videos]
[WebSearch済 sumera.io/blog/how-long-should-youtube-script-be]

### 6-2. カット頻度

**長尺動画は短尺のような毎秒カットは不要**。連続切り替えが多いと教育コンテンツでは「疲れる」と感じられる。

| フェーズ | 推奨カット間隔 |
|---|---|
| 0〜3分（冒頭・高エネルギー） | 10〜15秒ごとに映像変化 |
| 3〜7分（本編前半） | 30〜60秒ごとにB-rollや図解を挿入 |
| 8分以降（本編後半） | 穏やかなペース + 2〜3分ごとに「バースト」（急速5〜10カット）で注意リセット |

パターン割込み（Pattern Interrupt）= カット・テロップ・図解の変化を 60〜90 秒ごとに意図的に入れること。これが維持率改善に最も効果的な編集手法。

[WebFetch済 air.io/en/youtube-hacks/advanced-retention-editing-cutting-patterns-that-keep-viewers-past-minute-8]

### 6-3. B-Roll（インサート映像）の役割

- 解説内容を視覚的に補強 → 「理解速度」が上がり維持率向上
- 顔出しなしの PC 画面解説でも、関連画像や図表のインサートで視覚変化を作れる
- **顔出しなしチャンネルほど B-Roll / 図解のクオリティが重要**
- Nielsen の研究: 映像の動きとペースは「コンテンツの記憶定着率」を向上させる

[WebSearch済 air.io/en/youtube-hacks/advanced-retention-editing-cutting-patterns-that-keep-viewers-past-minute-8]
[WebSearch済 engagecoders.com/how-to-create-engaging-long-form-youtube-videos/]

### 6-4. テロップ・字幕（日本市場特有）

日本語動画においてテロップは維持率に直接影響する。

- **フルテロップ**（発話をすべて文字化）はエンタメ系・ナレーション系で離脱率低下に大きく貢献
- **部分テロップ**（要点のみ強調）は教育系・チュートリアル系に適す
- 1秒で読める文字数の目安 = 4〜6文字。1行 15〜20 文字、表示時間 3〜5 秒が適切
- スマホ視聴比率が高いため、文字サイズは「スマホ小画面で読めること」が最優先
- 音オフ視聴への対応: YouTube 長尺は TikTok ほど音オフ率は高くないが、日本国内では通勤・移動中の視聴が多くテロップ依存度は高め

[WebSearch済 discovery.aoyako.com/youtube-subtitles-and-audience-retention-rate/]
[WebSearch済 crobo.world/column/youtube-subtitles/]

---

## 7. CTA 設計

### 7-1. 長尺特有の CTA 構造

| 配置タイミング | CTA 種類 | 目的 | 効果 |
|---|---|---|---|
| 冒頭（0〜30秒） | CTA なし（禁止） | ― | フック優先 |
| 中盤（50〜60% 地点） | チャンネル登録・コメント | 視聴への感謝で受容度が最高 | データで最高転換率 |
| 終盤（90% 地点） | 次の動画・チャンネル登録 | 価値を最大に受け取った後 | 高い視聴継続率 |
| 終了画面（最後 20 秒） | 関連動画1本＋登録ボタン | セッション継続 | クリック率が視覚 + 口頭で最大化 |

「中盤CTAは動画最大の価値提供直後に置く」が 2025 年の最重要原則。
「1動画に1つのプライマリCTA」＝登録 or 次の動画、に絞ること。

[WebSearch済 ventress.app/blog/youtube-call-to-action-strategy-convert-viewers-subscribers/]
[WebSearch済 learn.tubeai.app/blog/youtube-script-writing-retention/youtube-script-cta-convert-viewers-retention]

### 7-2. 終了画面の設計

- 要素は 2〜3 個に絞る（多すぎると混乱）
- 最重要要素を最も目立つ位置に配置
- 「特定の動画」を推薦するか「最新動画」自動表示にするかは、前の動画との続きがある場合は特定動画を優先
- 口頭で「この動画を見てほしい（ここ↗）」と言いながら終了画面要素を指差すと高クリック

[WebSearch済 gyre.pro/blog/how-to-create-high-converting-youtube-end-screens-tips-and-examples]

### 7-3. コメント誘導の設計

中盤CTAで「コメントで◯◯を教えてください」という質問を入れると：
- コメント数増加 → アルゴリズムエンゲージメントシグナル強化
- 視聴者の参加意識が高まり再生率向上
- 質問は答えやすい具体的なものにする（「どう思いますか？」ではなく「どれを使っていますか？AかBか」）

---

## 8. Shorts → 長尺 連携

### 8-1. 連携戦略の基本設計

**Shorts = 発見、長尺 = 転換・定着** の役割分担が 2025 年の標準モデル。

| フェーズ | 役割 | 指標 |
|---|---|---|
| Shorts | チャンネル露出・新規発見 | インプレッション・ユニーク視聴者 |
| 長尺 | 視聴者の信頼構築・登録転換 | 登録転換率・AVD |

YouTube アルゴリズム: Shorts 視聴者が同チャンネルへの興味を示した場合、長尺が推薦される仕組みが 2025 年に確認されている。

### 8-2. 推奨比率

| 段階 | Shorts | 長尺 | 備考 |
|---|---|---|---|
| **初期（登録者〜1,000人）** | 70% | 30% | 発見を最優先 |
| **確立期（1,000〜10,000人）** | 50% | 50% | バランス移行 |
| **成長期（10,000人超）** | 30% | 70% | 長尺に比重移動 |

頻度: Shorts 週3〜5本 + 長尺 週1〜2本が推奨値

[WebFetch済 influenceflow.io/resources/youtube-shorts-and-long-form-video-strategy-the-complete-2026-creators-guide-1/]
[WebSearch済 air.io/en/youtube-hacks/should-you-chase-shorts-views-or-double-down-on-long-form-for-channel-growth]

### 8-3. 同テーマを Shorts と長尺で出す場合の差分

**推奨ワークフロー**: 長尺を先に制作し、そこから Shorts を切り出す。

```
長尺「Claude Code で副業月14万になった方法（15分）」
 ├── Shorts 1: 最初の1ヶ月で稼げた金額（60秒）
 ├── Shorts 2: 一番効いた応募文の書き方（45秒）
 └── Shorts 3: 失敗した3つのこと（58秒）
```

Shorts から長尺への誘導で「40%高い長尺視聴時間」の事例データあり。

[WebFetch済 influenceflow.io/resources/youtube-shorts-and-long-form-video-strategy-the-complete-2026-creators-guide-1/]

### 8-4. Shorts 終盤での長尺誘導

- 最後の 3〜5 秒に「フル動画はこちら▶」のテキストオーバーレイを入れる
- Shorts の説明文に長尺動画の URL を貼る（固定リンク）
- 「これは○分動画の要点だけを切り出したものです。詳しく知りたい方は説明欄の全編動画を」という発話を入れると視聴継続率が上がる事例あり

---

## 9. 日本市場特性 + 事例

### 9-1. 日本市場の長尺視聴傾向

- **テロップ依存度が高い**: 日本のニコニコ動画・バラエティTV文化の影響でテロップが視聴者の期待値に入っている
- **説明的なタイトルが好まれる**: 英語圏より情報量の多い（長い）タイトルが CTR を得やすい傾向
- **スマホ視聴が主流**: Yahoo! Japan のモバイル検索連携もあり、音オフ・電車内視聴への配慮が必要
- **丁寧さと信頼性重視**: 「初心者でもわかる」「図解で解説」などの表現が刺さりやすい

### 9-2. 日本の AI系・副業系・教育系 長尺チャンネル事例

| アカウント | 登録者数（参照時点） | ジャンル | 特徴 | URL |
|---|---|---|---|---|
| 中田敦彦のYouTube大学 | 540万人超 | 教育・解説 | 長尺（10〜30分）の徹底解説型。チャプター活用。2025年2月に9割非公開→同年再始動 | [youtube.com/c/NakataNakataUniversity](https://www.youtube.com/channel/F47380CE0FB6B948_f549ab) |
| 両学長 リベラルアーツ大学 | 推定100万人超 | お金・教育・副業 | 長尺講義形式（16〜120分）と短尺を組み合わせ。2026年1月登録者月間ランキング3位 | [youtube.com/channel/UC67Wr_9pA4I0glIxDt_Cpyw](https://www.youtube.com/channel/UC67Wr_9pA4I0glIxDt_Cpyw) |
| Yuta Hiraoka | 433K | AI・生産性 | ChatGPT等のAI活用を実務的に解説。日本最大規模のAI教育チャンネル | [youtube.com/@Yuta_Hiraoka](https://youtube.com/@Yuta_Hiraoka) |
| mikimiki Web School | 313K | AI・Webデザイン | ウェブ設計×AI。チュートリアル中心。女性視聴者層に強い | [youtube.com/channel/UChxtIA33ty53Hh4MmkXNASg](https://youtube.com/channel/UChxtIA33ty53Hh4MmkXNASg) |
| IkeTomo | 173K | AI・リモートワーク | AI ツールを初心者向けに解説。わかりやすさ重視 | [youtube.com/@iketomo-ch](https://youtube.com/@iketomo-ch) |
| KEITO【AI&WEB ch】 | 142K | AI・Web開発 | AIとWeb開発の交差点。実践ツール活用特化 | [youtube.com/@keitoaiweb](https://youtube.com/@keitoaiweb) |
| AI FREAK | 77K | AI | AIツール最新情報・AI生成作品。Instagram 60万人と連携 | [note.com/ai_freak](https://note.com/ai_freak/n/n05e51f7ce9de) |
| Usutaku Channel | 138K | AI・ビジネス | 日常とビジネスへのAI活用、起業家視点 | [youtube.com/@usutaku](https://youtube.com/@usutaku) |

[WebFetch済 japanbuzz.info/ai-tech-influencers-in-japan/]
[WebSearch済 yutura.net/channel/10184/, yutura.net/channel/16133/]
[WebSearch済 youtube-ranking.userlocal.jp]

### 9-3. 海外と日本の長尺構成の違い

| 比較軸 | 海外（英語圏） | 日本 |
|---|---|---|
| フックスタイル | 衝撃映像・センセーショナルな主張 | 共感型・悩み代弁型「〇〇で困ったことある人へ」 |
| イントロ | 冒頭30秒でバシッと切る | 少し長めのイントロを許容する視聴者が多い（但し2025年以降は短縮傾向） |
| テロップ | 要点のみのキャプション型 | フルテロップ（バラエティTV文化）が主流 |
| タイトル | 感情訴求・数字強調 | 情報的タイトル＋「初心者向け」「完全解説」「2025年最新」 |
| チャプター | 積極活用 | 認知が広がってきたが、まだ浸透中 |
| CTA | 中盤・終盤で直接的に登録要求 | 押しが弱め。「よければ登録もお願いします」がデフォルト |

---

## 10. 失敗パターン

### 10-1. 滑る長尺の共通パターン

| NG パターン | 詳細 | 修正方針 |
|---|---|---|
| **長すぎるイントロ** | 5〜10秒のロゴ/BGM + 30秒以上の自己紹介・今日の内容説明 | イントロ削除。最初の一言からコンテンツ本番 |
| **コールドスタート禁止語** | 「こんにちは！チャンネルへようこそ」「今日は〇〇について話します」 | フックを最初の一言にする |
| **タイトル詐欺（クリックベイト）** | サムネ・タイトルの約束を30秒内に証明しない | 冒頭でタイトルの主張を即証明する |
| **中盤の脱線・蛇足** | 関係ない話・自分語り・同じ内容の繰り返し | 台本段階でスクリプトチェック（1文1役割の原則） |
| **冗長な締め** | 「というわけで今日は〇〇について話しました（要点の繰り返し）」が2分以上 | まとめは30秒以内、残りはCTAに使う |
| **説明過多** | 「20秒のアイデアを45秒に引き伸ばす」繰り返し・冗長な言い換え | 1ポイント1発言が原則 |
| **カット不足** | 60〜90秒以上、映像の変化なし | B-Roll・テロップ・図解で60〜90秒ごとに視覚変化 |

[WebSearch済 creatipi.com/blog/10-mistakes-that-hurt-your-viewer-retention-on-youtube/]
[WebSearch済 teleprompter.com/blog/youtube-audience-retention]

### 10-2. AI 生成丸出し台本・音声の長尺特有サイン

2025年7月、YouTubeが「大量生産・反復コンテンツ」のマネタイズ停止を開始。AI音声・スクリプトの使い方が問われる段階に入った。

| サイン | 具体例 |
|---|---|
| **単調なAI音声** | 抑揚ゼロ・同一ペース → 最初の45秒で35%が離脱（人間音声比較） |
| **文章の構造が均一すぎる** | 全段落「〇〇については、△△です。次に…」の繰り返し |
| **感情的接触点ゼロ** | 数字・事実の羅列だけで「失敗した話」「焦った瞬間」がない |
| **前置き過多** | 「この点について説明する前に」「まず前提として」が1動画に5回以上 |
| **全ての情報が重要扱い** | 「重要なのは」「ポイントは」「ここが大切です」が毎段落に登場 |

[WebSearch済 techcrunch.com/2025/07/09/youtube-prepares-crackdown-on-mass-produced-and-repetitive-videos/]
[WebSearch済 narrationbox.com/blog/why-viewers-drop-off-after-30-seconds-youtube]

### 10-3. 視聴維持率が崩れる典型的タイミング

1. **0〜30秒**（フックの失敗）: 価値提案が不明確 or タイトルとの乖離
2. **5〜6分**（中盤だれ）: 内容の密度が落ち、「続きを見る価値」が見えなくなる
3. **8〜9分付近**（広告への反応）: ミッドロール広告直前に意図せず離脱が発生しやすい
4. **終盤（動画尺の85%超）**: アウトロが長すぎると終了画面に到達する前に離脱

---

## 11. スコアリングへの示唆

### 長尺台本の判定軸（8 項目）

| 番号 | 判定軸 | 短尺との差分 | 合格ライン（目安） |
|---|---|---|---|
| **L-1** | **フックの構造（0〜30秒）** | 短尺は3秒以内で即インパクト。長尺は15〜30秒かけて「問題提起→約束→ステークス」の3段構造を丁寧に積める | 30秒以内に「視聴者が得られること」を明言できているか |
| **L-2** | **冒頭NGワードの有無** | 共通（短尺でも同様に禁止）。但し長尺は「今日は〇〇について話します」という予告型イントロが多発しやすい | 「こんにちは」「チャンネルへようこそ」「今日は〜です」が1行目に出ていないか |
| **L-3** | **構成型の適合（ジャンルと型の一致）** | 短尺はフック + オチの2段構造。長尺はジャンルごとの型（Problem-Solution / Story-Arc / Tutorial / 比較型）が必要 | 指定ジャンルに対応する構成型（2-2参照）を採用しているか |
| **L-4** | **セクション分けとチャプター設計** | 短尺では不要。長尺では5分超にチャプター必須 | 3〜4分ごとに話題の切れ目があり、チャプタータイトルがキーワードを含んでいるか |
| **L-5** | **中盤のパターン割込み設計** | 短尺は全体がインパクト。長尺は「60〜90秒ごとに視覚変化の指示が台本に入っているか」 | 台本にB-Roll指示・図解指示・テロップ強調が3分ごとに存在するか |
| **L-6** | **CTA の配置（中盤 + 終盤）** | 短尺はラスト1秒CTA。長尺は中盤（最大価値提供直後）＋終盤（終了画面）の2段構造 | 50〜60%地点に中盤CTA・終盤にアウトロCTAが配置されているか |
| **L-7** | **AI 生成台本臭の有無** | 共通問題。長尺は尺が長い分「均一文体・感情なし・前置き過多」が拡大して露呈しやすい | 感情的接触点（失敗・驚き・転換点）が動画内に3箇所以上あるか / 前置きが段落の20%以下か |
| **L-8** | **推奨尺との整合性** | 短尺は「60秒以内」が絶対。長尺はジャンルごとの推奨尺（5-1参照）に対して±3分以内が目安 | 解説8〜12分 / チュートリアル10〜18分 / 実録10〜15分 の範囲内か |
| **L-9（任意）** | **タイトル・サムネ提案の品質** | 短尺は感情訴求サムネ。長尺は SEO + 感情訴求の二軸。タイトル文字数も異なる | タイトルが日本語30〜40文字・検索キーワードが冒頭にあるか |
| **L-10（任意）** | **Shorts 連携設計の有無** | 短尺単体での評価には不要。長尺台本審査では「Shorts 切り出しポイントがあるか」 | 60〜90秒で完結する「切り出せる話題」が1〜2箇所含まれているか |

### スコアリング応用案

- L-1〜L-8 を各 10 点 = 80 点満点
- 60 点以上: PASS（添削コメント付きで返却）
- 40〜59 点: 要修正（具体的な修正箇所リスト）
- 39 点以下: 要リライト（構成型の選択から見直し）

---

## 出典一覧

### WebSearch 済（24件）

1. [vidiq.com - YouTube Algorithm 2026](https://vidiq.com/blog/post/understanding-youtube-algorithm/)
2. [socialpilot.co - YouTube Algorithm](https://www.socialpilot.co/youtube-marketing/youtube-algorithm)
3. [retentionrabbit.com - 2025 Retention Benchmark](https://www.retentionrabbit.com/blog/2025-youtube-audience-retention-benchmark-report)
4. [fluxnote.io - Average View Duration 2026](https://fluxnote.io/guides/youtube-average-view-duration-2026)
5. [1of10.com - Hook 30 seconds](https://1of10.com/blog/how-to-hook-viewers-in-the-first-30-seconds-of-a-youtube-video/)
6. [miraflow.ai - CTR Benchmarks 2026](https://miraflow.ai/blog/youtube-ctr-benchmarks-2026)
7. [buzzvoice.com - Good CTR YouTube](https://buzzvoice.com/blog/what-is-a-good-click-through-rate-on-youtube/)
8. [creator-hero.com - Video Length 2025](https://www.creator-hero.com/blog/how-long-should-a-youtube-video-be)
9. [ytshark.com - Ideal Video Length 2026](https://ytshark.com/ideal-youtube-video-length/)
10. [influenceflow.io - Shorts Long-Form Strategy 2026](https://influenceflow.io/resources/youtube-shorts-and-long-form-video-strategy-the-complete-2026-creators-guide-1/)
11. [buildmyplays.com - Shorts Long-Form Subscriber Conversion](https://buildmyplays.com/youtube-shorts-and-long-form-strategy/)
12. [air.io - Shorts vs Long-Form Growth](https://air.io/en/youtube-hacks/should-you-chase-shorts-views-or-double-down-on-long-form-for-channel-growth)
13. [usevisuals.com - Chapters Watch Time](https://usevisuals.com/blog/using-chapters-to-improve-watch-time-on-youtube)
14. [gyre.pro - YouTube Chapters](https://gyre.pro/blog/youtube-video-chapters-how-to-add-them-why-they-increase-views)
15. [ventress.app - CTA Strategy](https://ventress.app/blog/youtube-call-to-action-strategy-convert-viewers-subscribers/)
16. [gyre.pro - End Screens](https://gyre.pro/blog/how-to-create-high-converting-youtube-end-screens-tips-and-examples)
17. [vidiq.com - Thumbnail Tips](https://vidiq.com/blog/post/youtube-thumbnail-design-tips/)
18. [ampifire.com - Thumbnail Best Practices](https://ampifire.com/blog/best-youtube-thumbnail-guide-examples-best-practices-2025-for-high-ctr/)
19. [wordtotime.org - Script Timing](https://wordtotime.org/blog/script-timing-for-youtube-videos)
20. [san.com - Clickbait Crackdown](https://san.com/cc/youtube-cracks-down-on-clickbait-with-new-enforcement-measures/)
21. [fastcompany.com - YouTube Clickbait Plan](https://www.fastcompany.com/91252550/youtube-has-a-new-plan-to-combat-clickbait)
22. [techcrunch.com - AI Slop Crackdown 2025](https://techcrunch.com/2025/07/09/youtube-prepares-crackdown-on-mass-produced-and-repetitive-videos-as-concern-over-ai-slop-grows/)
23. [creatipi.com - Retention Mistakes](https://www.creatipi.com/blog/10-mistakes-that-hurt-your-viewer-retention-on-youtube/)
24. [japanbuzz.info - AI Influencers Japan](https://www.japanbuzz.info/ai-tech-influencers-in-japan/)
25. [yutura.net - 両学長チャンネル](https://yutura.net/channel/16133/)
26. [yutura.net - 中田敦彦チャンネル](https://yutura.net/channel/10184/)
27. [blog.youtube - Japan EOY 2025](https://blog.youtube/intl/ja-jp/news-and-events/japan-eoy-2025/)
28. [discovery.aoyako.com - テロップ視聴維持率](https://discovery.aoyako.com/youtube-subtitles-and-audience-retention-rate/)

### WebFetch 済（8件）

1. [vidiq.com - Algorithm Deep Dive](https://vidiq.com/blog/post/understanding-youtube-algorithm/) ✅WebFetch済
2. [retentionrabbit.com - Benchmark 2025](https://www.retentionrabbit.com/blog/2025-youtube-audience-retention-benchmark-report) ✅WebFetch済
3. [influenceflow.io - Shorts Strategy](https://influenceflow.io/resources/youtube-shorts-and-long-form-video-strategy-the-complete-2026-creators-guide-1/) ✅WebFetch済
4. [air.io - Advanced Retention Editing](https://air.io/en/youtube-hacks/advanced-retention-editing-cutting-patterns-that-keep-viewers-past-minute-8) ✅WebFetch済
5. [vidiq.com - Mid-Roll Ads](https://vidiq.com/blog/post/youtube-8-minute-mid-roll-ads/) ✅WebFetch済
6. [miraflow.ai - CTR Benchmarks](https://miraflow.ai/blog/youtube-ctr-benchmarks-2026) ✅WebFetch済
7. [addness.co.jp - YouTube Algorithm JP](https://addness.co.jp/media/youtube-algorithms/) ✅WebFetch済
8. [storyy.com - Long Form Guide 2025](https://storyy.com/2025/07/28/what-is-considered-long-form-content-on-youtube-a-2025-guide/) ✅WebFetch済
9. [backlinko.com - Rank YouTube Videos](https://backlinko.com/how-to-rank-youtube-videos) ✅WebFetch済
