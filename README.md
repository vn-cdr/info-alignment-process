# info-alignment-process


# Obsidian × GitHub × GitHub Pages × Medium ナレッジ管理・情報発信構想

## 1. 目的と基本方針

Obsidianを情報管理の中心（Knowledge Hub）に据え、GitHub・GitHub
Pages・Mediumを公開・共有先として使い分ける。

基本方針は、同じ情報を各サービスで何度も書かず、Obsidianに知識の原本を蓄積し、公開先に応じて編集・加工して展開すること。

-   **Obsidian**：情報の原本、整理、検索、再利用
-   **GitHub**：コード、専門技術資料、OSS、バージョン管理
-   **GitHub Pages**：技術ブログ、技術ナレッジ、ドキュメントサイト
-   **Medium**：技術・一般生活・キャリアなど幅広い読者向けの記事
-   **Claude / ChatGPT**：調査、要約、構成、執筆、レビューの支援

ObsidianをSingle Source of
Truth（情報の原本）として扱い、公開先は原則として派生コンテンツとする。ただし、コードやOSSなどGitHub自体が原本となる成果物は例外とする。

## 2. 全体アーキテクチャ

``` text
                 Claude / ChatGPT / Web / GitHub
                              |
                              v
                     +------------------+
                     |     Obsidian     |
                     |  Knowledge Hub   |
                     |                  |
                     | Inbox / Knowledge|
                     | Projects / Drafts|
                     +------------------+
                              |
                    整理・編集・公開先選択
                              |
             +----------------+----------------+
             |                |                |
             v                v                v
       +-----------+    +-------------+   +-----------+
       |  GitHub   |    | GitHub Pages|   |  Medium   |
       |           |    |             |   |           |
       | Code/OSS  |    | 技術記事    |   | 一般公開  |
       | 専門資料  |    | 技術ガイド  |   | ブログ    |
       +-----------+    +-------------+   +-----------+
             |                |                |
             +----------------+----------------+
                              |
                       URL・成果物を記録
                              |
                              v
                         Obsidian
```

### 情報の流れ

1.  Claude、ChatGPT、Web、GitHub、Mediumなどから情報を収集する。
2.  収集した情報をObsidianのInboxに一時保存する。
3.  内容を確認し、KnowledgeやProjectsに整理する。
4.  公開する価値のある情報を記事・成果物として編集する。
5.  公開先に応じてGitHub、GitHub Pages、Mediumへ展開する。
6.  公開URL、公開日、更新履歴をObsidianに記録する。
7.  公開後の知見やフィードバックをKnowledgeに反映する。

## 3. 各サービスの役割

  --------------------------------------------------------------------------------------------------------
  サービス                主な役割                主なコンテンツ
  ----------------------- ----------------------- --------------------------------------------------------
  Obsidian                個人ナレッジ管理        調査メモ、学習記録、アイデア、記事原稿、参照情報

  GitHub                  技術資産の管理・共有    ソースコード、サンプル、設定ファイル、専門的なMarkdown

  GitHub Pages            技術情報の公開          技術ブログ、設計ガイド、手順書、アーキテクチャ解説

  Medium                  幅広い読者向けの発信    技術考察、AI活用、キャリア、働き方、生活、趣味

  Claude                  AIによる作業支援        調査、構成案、文章作成、ファイル編集

  ChatGPT                 AIによる作業支援        調査、分析、要約、レビュー、記事作成
  --------------------------------------------------------------------------------------------------------

### GitHub PagesとMediumの使い分け

**GitHub Pages：技術特化**

-   GitHub Enterprise / Copilotの設計・運用
-   DevSecOps
-   AI Governance
-   AWS / GCP / Azure
-   技術アーキテクチャ
-   実装手順、設定例、技術検証
-   コードや設定ファイルへのリンク

**Medium：幅広い読者向け**

-   技術的な経験や考察
-   AI活用の一般的な知見
-   キャリアや働き方
-   ランニング、音楽、趣味
-   日常生活で得た知見

同じテーマを扱う場合でも、GitHub
Pagesでは実装や詳細を中心に、Mediumでは背景・課題・学び・読者にとっての意味を中心に編集する。

## 4. Obsidian Vaultの推奨フォルダ構成

``` text
MyKnowledge/
│
├── 00_Inbox/
│   ├── AI_Conversations/
│   ├── Web_Clippings/
│   └── Quick_Notes/
│
├── 10_Knowledge/
│   ├── Technology/
│   │   ├── AI/
│   │   ├── GitHub/
│   │   ├── DevSecOps/
│   │   ├── Cloud/
│   │   └── Architecture/
│   ├── Business/
│   ├── Career/
│   ├── Life/
│   ├── Running/
│   └── Music/
│
├── 20_Projects/
│   ├── AI_Governance/
│   ├── GitHub_Enterprise/
│   └── Personal_Blog/
│
├── 30_Publications/
│   ├── GitHub_Pages/
│   ├── Medium/
│   └── GitHub_Repository/
│
├── 40_References/
│   ├── Books/
│   ├── Websites/
│   └── Research/
│
├── 90_Templates/
│   ├── Knowledge.md
│   ├── Technical_Article.md
│   ├── Medium_Article.md
│   └── AI_Research.md
│
└── 99_System/
    ├── Dashboard.md
    ├── Publication_Index.md
    └── Settings/
```

### フォルダの使い分け

-   `00_Inbox`：未整理の情報を一時的に置く場所。
-   `10_Knowledge`：再利用できる知識をテーマ別に蓄積する場所。
-   `20_Projects`：特定の目的・成果物に関する作業情報を管理する場所。
-   `30_Publications`：公開用に編集した記事や成果物の原稿を管理する場所。
-   `40_References`：書籍、Webサイト、論文、公式ドキュメントなどの参照情報。
-   `90_Templates`：ノートや記事のテンプレート。
-   `99_System`：ダッシュボードや運用設定。

### 具体例：AI Governanceの情報を整理する場合

-   `10_Knowledge/Technology/AI/`：NIST AI RMF、OWASP、ISO
    42001などの知識
-   `20_Projects/AI_Governance/`：特定プロジェクトの検討・設計・意思決定
-   `30_Publications/GitHub_Pages/`：技術者向けの公開記事
-   `30_Publications/Medium/`：一般読者向けに編集した記事

情報そのものと、特定プロジェクトの作業記録、公開記事を分離することで、知識を複数の成果物に再利用しやすくする。

## 5. ノート間のリンク

Obsidianでは、関連情報を独立したノートとして管理し、Wikilinksで相互に関連付ける。

例：

``` markdown
# GitHub Copilot Governance

## 関連知識
- [[NIST AI RMF]]
- [[OWASP Top 10 for LLM Applications]]
- [[ISO 42001]]
- [[GitHub Enterprise Managed Users]]

## 関連プロジェクト
- [[AI Governance Project]]

## 公開記事
- [[GitHub Copilot Governance Guide]]
```

同じ内容を複数のノートに複製するよりも、関連ノートへのリンクを使って知識をつなぐ。

## 6. Propertiesによる公開管理

ObsidianのProperties（YAML
Frontmatter）を使い、記事の状態や公開先を管理する。

### 記事のFrontmatter例

``` yaml
---
title: GitHub Copilot AI Governance
type: article
category: technology
status: draft

publish:
  github_pages: false
  medium: false
  github_repo: false

created: 2026-11-07
updated: 2026-11-07

tags:
  - AI
  - GitHub
  - Governance

publication:
  github_pages_url: ""
  medium_url: ""
  github_repo_url: ""
  published_at: ""
---
```

公開準備が整った場合は、対象の公開先を`true`にする。

``` yaml
publish:
  github_pages: true
  medium: true
  github_repo: false
```

このフラグは公開対象を示すメタデータであり、フラグを変更しただけで自動公開されるわけではない。実際の公開処理は、GitHub
Actionsや投稿スクリプトなど別の仕組みで実装する。

### 公開ステータス

  ステータス    意味
  ------------- ----------------
  `draft`       下書き
  `review`      内容確認中
  `ready`       公開準備完了
  `published`   公開済み
  `archived`    保管・公開終了

公開先ごとにURLと公開日を記録し、Obsidianから公開状況を確認できるようにする。

## 7. GitHub Pagesの構築方式

GitHub Pagesは、Markdownを静的サイトとして公開する仕組みと組み合わせる。

候補は以下の2つ。

### 7.1 Quartz

公式サイト：<https://quartz.jzhao.xyz/>

-   Obsidianとの親和性が高い静的サイトジェネレーター。
-   Wikilinks、バックリンク、グラフなどを活用できる。
-   技術ブログ、技術ナレッジ、デジタルガーデンに向いている。

### 7.2 Material for MkDocs

公式サイト：<https://squidfunk.github.io/mkdocs-material/>

-   技術ドキュメントや体系的なガイドに向いている。
-   ナビゲーション、検索、コード表示などを構成しやすい。
-   手順書、設計ガイド、標準・ルール集などに適している。

### 推奨方針

最初はQuartzで技術ブログを構築する。情報量やドキュメントの体系性が増えてきたら、MkDocs
Materialを専門ドキュメント向けに追加する。

最初から複数サイトを運用する必要はない。

## 8. Obsidianの連携プラグイン候補

  ---------------------------------------------------------------------------------------------
  プラグイン              用途                                         導入方針
  ----------------------- -------------------------------------------- ------------------------
  Obsidian Git            VaultのGitバックアップ、Commit、Push、Pull   最初に検討

  Obsidian Web Clipper    Web情報の取り込み                            最初に検討

  Publish on GitHub       ノートのGitHub公開                           公開方式を確認して選択

  Blog Publisher          ブログ記事のGitHub公開                       Publish on
                                                                       GitHubと比較して選択
  ---------------------------------------------------------------------------------------------

公開系プラグインは機能が重複する可能性があるため、最初から複数を導入しない。現在のメンテナンス状況、対応するObsidianバージョン、Quartz等との互換性、公開対象の制御方法を確認して選ぶ。

### Git管理で重要なこと

Obsidian
GitによるVault全体のバックアップと、公開記事だけを別リポジトリに出す処理は分離する。

推奨構成：

-   Private Repository：Vault全体のバックアップ
-   Publicまたは公開用Repository：公開を許可した記事・資料のみ
-   OSS Repository：コードやサンプルなど、独立した技術成果物

## 9. Mediumへの投稿フロー

Mediumは、ObsidianのMarkdown原稿をMedium向けに編集・変換して投稿する運用を推奨する。

``` text
Obsidian
   |
   v
Markdown原稿
   |
   v
Medium向け編集
   |
   +-- タイトル調整
   +-- 導入文の追加
   +-- 一般読者向けの表現に修正
   +-- 画像・リンクの調整
   +-- タグ設定
   |
   v
Mediumへ投稿
   |
   v
公開URLをObsidianに記録
```

GitHub
Pagesの記事をそのままコピーするのではなく、読者層に合わせて編集する。

  GitHub Pages         Medium
  -------------------- ----------------------------------
  詳細な設定手順       なぜその技術・仕組みが重要なのか
  YAML・コード例       実務での活用事例
  GitHub設定一覧       企業導入時の課題
  技術アーキテクチャ   設計・導入で学んだこと

Mediumへの投稿は、初期段階では手動投稿を基本とする。投稿頻度が増え、APIや投稿方式の制約を確認できた段階で自動化を検討する。

## 10. Claude・ChatGPTとの連携

AIとの会話や調査結果を一過性の情報にせず、ObsidianのMarkdownファイルとして蓄積する。

### 推奨する連携方法

-   Claude Code：ローカルのVaultを参照・編集するワークフローを検討する。
-   ChatGPT：ファイルの受け渡しや、利用可能なGitHub連携などを通じて知識資産を扱う。
-   Git：変更履歴を確認し、AIによる編集内容をレビューする。

### AIに依頼する作業

  作業       依頼内容
  ---------- --------------------------------
  情報収集   技術調査、Web情報の整理
  情報蓄積   Obsidian用Markdownの作成
  情報整理   既存ノートとの関連付け
  記事作成   技術ブログ、Medium原稿
  品質確認   内容、リンク、コードのレビュー
  公開準備   Frontmatter、画像、目次の整備

### AIへの依頼テンプレート例

``` text
ObsidianのVaultを参照してください。

テーマ：
GitHub CopilotのAIガバナンス

実施内容：
1. 既存の関連ノートを検索
2. 関連情報を整理
3. 不足情報を調査
4. 新しいKnowledgeノートを作成
5. 既存ノートとのリンクを追加
6. GitHub Pages向け記事のドラフトを作成
7. Medium向け記事のドラフトを作成

注意：
- 公開前の原稿はdraftとする。
- 公開操作は実行しない。
- 事実、推測、未検証事項を区別する。
- 参照元URLを記録する。
- 社内情報や個人情報を公開用原稿に含めない。
```

## 11. セキュリティ・情報管理上の注意

特に業務上のGitHub Enterpriseや顧客情報を扱う場合、個人のKnowledge
Vaultと業務情報は分離する。

-   PrivateなVault全体を公開リポジトリにPushしない。
-   公開用リポジトリは別にする。
-   公開対象を明示的に選択する。
-   API Tokenや認証情報をVault内に平文保存しない。
-   公開前に個人情報、社内情報、顧客情報、秘密情報をチェックする。
-   AIが生成した内容は、原典・事実関係・ライセンスを確認してから公開する。
-   公開処理は原則として人間のレビューを経由させる。
-   GitHub Actionsでは最小権限のトークンを使用する。

業務情報については、所属組織の情報セキュリティポリシーやAI利用ルールを優先する。

## 12. 推奨する導入ロードマップ

  -------------------------------------------------------------------------------------------------------------------------------
  フェーズ                実施内容                                                             到達目標
  ----------------------- -------------------------------------------------------------------- ----------------------------------
  Phase 1                 Obsidian                                                             情報を集約できる
                          Vault構築、フォルダ・Properties・テンプレート整備、Gitバックアップ   

  Phase 2                 GitHub PagesとQuartzの連携、公開用Repository、GitHub Actions         技術記事を公開できる

  Phase 3                 Medium向けテンプレート、投稿フロー、URL管理                          複数媒体へ効率よく発信できる

  Phase 4                 Claude Code・ChatGPTによる整理、執筆、レビュー支援                   情報整理と記事作成を効率化できる

  Phase 5                 公開候補の抽出、変換、品質チェックの自動化                           半自動の情報発信基盤を実現する
  -------------------------------------------------------------------------------------------------------------------------------

## 13. 最初に採用する技術スタック

  領域                   採用候補
  ---------------------- -------------------------------------------
  ナレッジ管理           Obsidian
  バージョン管理         Git
  Vaultバックアップ      GitHub Private Repository
  技術ブログ             Quartz
  専門技術ドキュメント   MkDocs Material（必要になった段階で導入）
  公開パイプライン       GitHub Actions
  AI調査・執筆           Claude Code / ChatGPT
  一般向けブログ         Medium
  情報収集               Obsidian Web Clipper

## 14. 推奨する初期運用

最初からすべてを自動化すると、プラグインの保守や同期トラブルに時間を取られる可能性がある。まずは以下の運用を推奨する。

1.  情報はObsidian Inboxに集める。
2.  定期的にKnowledgeへ整理する。
3.  記事化するテーマを選び、Obsidianで原稿を作成する。
4.  Propertiesで公開先を指定する。
5.  GitHub Pages向け記事はQuartz用Repositoryに反映する。
6.  Medium向け記事は読者層に合わせて編集し、手動で投稿する。
7.  公開URLと公開日をObsidianに記録する。
8.  公開後の修正や学びをKnowledgeへ戻す。

**初期推奨構成：Vault全体のPrivateバックアップ＋公開用Repositoryの分離＋半自動運用。**

この構成であれば、情報の安全性を保ちつつ、日々の情報整理とブログ投稿の手間を段階的に減らせる。
