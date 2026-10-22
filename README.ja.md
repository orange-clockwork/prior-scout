[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**既存の成果を探す。根拠を確かめてから伝える。**

Prior-Scout（先例探索）は、開発前に既存の選択肢を調べるための、指示だけで構成された
小さな Agent Skill です。要件、URL、読み取り可能な文書をもとに公開情報を検索し、
関連する機能を確認します。ツール、サービス、Skill、ライブラリ、研究実装の
共通点と重要な違いを簡潔にまとめます。

**`0.1.1-experimental` · GitHub で公開中 · MIT**

## 実際の動作例

以下は、**ユーザーから報告された Prior-Scout の使用例**をまとめたものです。
今回の文書更新では、元資料を別途確認しました。各セッションの入力原文や生ログは
このリポジトリに保存されておらず、会話の再現や独立した性能試験ではありません。

### Demo 01 — Prior-Scout は自分に似た Skill を見つけられるか？

開発後、作者は Prior-Scout を使って似たワークフローを調べました。代表的な3件です。

- **[search-first](https://github.com/affaan-m/ECC/blob/main/skills/search-first/SKILL.md)：** 実装前に既存の成果を調べる点で近く、採用・拡張・新規開発の判断から実装まで進みます。
- **[priorart](https://github.com/duthaho/skillhub/blob/main/.claude/skills/priorart/SKILL.md)：** 既存のアイデアを調べる点で近く、根拠の所在、調査上限、開発・フォーク・利用などの判断を求めます。
- **[find-skills](https://github.com/vercel-labs/skills/blob/main/skills/find-skills/SKILL.md)：** 一部が重なります。導入可能な Skill の発見とインストールの提案が中心で、より広い関連成果の比較とは範囲が異なります。

**独自性を作り出さず、実際の重なりを示す。** Prior-Scout は根拠付きの短い比較で調査を
区切り、許可された元の作業に戻ります。これは対象範囲の選択であり、優位性の証明では
ありません。開発後の確認なので、開発前に何を調べたかも証明しません。
[全5候補・報告された調査量・資料の確認](docs/examples.md#demo-01-agent-skill-discovery)。

### Demo 02 — 歩行者ナビゲーション研究の関連文献を探す

作者が計画中の修士研究は、経路全体の案内、方向と距離の案内、目的地のみの提示を
比較します。報告された3件から、研究手法まで比較する必要性が分かります。

- **[Robinson ら（2012）](https://cronfa.swansea.ac.uk/Record/cronfa17385/Download/0017385-18012016145442.pdf) — 全文：** 方向を伝える触覚フィードバックと経路選択。計画中の3条件を比較した研究ではありません。
- **[Sugimoto ら（2022）](https://ist.ksc.kwansei.ac.jp/~nagata/data/sugimoto_2021_spat_cogn_comput.pdf) — 全文：** スマートフォン地図・紙地図と空間記憶。媒体の違いから情報量だけの効果は切り分けられません。
- **[Heller ら（2020）](https://www.krisluyten.net/publications/dblp_conf_mhci_helleral20/) — 要旨のみ：** 音声による案内、移動効率、作業負荷。測定の詳細はここでは未確認です。

**テーマが似ていても、実験条件や測定指標が同じとは限りません。** 修士研究は計画段階で、
公表済みの結果や新規性の判定ではありません。[詳しい比較](docs/examples.md#demo-02-pedestrian-navigation-research)では、
元の観察と、今回追加で行った Ishikawa & Takahashi（2014）の文献確認を分けています。

以前の [Markdown リンクチェッカー T2 の例](docs/examples.md#t2-markdown-link-checker)も、
保存済みの監査記録とともに残しています。

## インストールと使い方

[Skills CLI](https://github.com/vercel-labs/skills) 1.7.4 には Node.js 22.20 以降が必要です。
ホスト側には Agent Skills の読み込み、検索、資料読み取りの機能が必要です。
対象プロジェクトで実行してください。

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex
```

同名の Skill が導入済みでないか先に確認してください。範囲を聞かれた場合は
プロジェクト単位を選び、`-g` は追加しないでください。配置先は
`.agents/skills/prior-scout/` で、SKILL.md と MIT LICENSE が含まれます。

そのプロジェクトで新しい Codex 会話を開き、Skill を明示的に指定してください。
次は呼び出し方の例であり、上記2件の入力原文ではありません。

> $prior-scout を使って、既存のオープンソースの Markdown リンクチェッカーを探してください。
> 信頼できる資料を読み、確認できた共通点と重要な違いを簡潔に説明してください。

<details>
<summary>一覧の確認とコピー方式のインストール</summary>

```sh
npx skills@1.7.4 add orange-clockwork/prior-scout --list
npx skills@1.7.4 add orange-clockwork/prior-scout --skill prior-scout -a codex --copy -y
npx skills@1.7.4 list -a codex
```

コピー方式は主手順の代わりに選ぶ方法です。対象プロジェクトに同名の Skill がないことを
確認してから実行してください。

</details>

## 処理の流れ

1. 要件、比較したい点、必須条件を整理する。
2. 通常は**検索クエリ6件、外部根拠文書8件**を上限として検索する。
3. 信頼できる資料を読み、主張がどの成果物、バージョン、サービスプラン、利用方法に当てはまるか確認する。
4. 根拠のある共通点、重要な違い、未確認事項を簡潔にまとめ、ほかに許可された作業があれば戻る。

検索スニペットは手がかりです。API、予定機能、部分的な類似だけでは、完成済みの
組み込み機能とは言えません。調査上限は指示であり、プログラムによる強制ではありません。
検索と資料読み取りはホストの機能を使い、Prior-Scout 自体は実行時依存パッケージや
テレメトリーを追加しません。根拠を取得できない場合はその制約を示し、
「提供された資料だけを使う」という指定を優先します。

既存の選択肢や関連研究を明示的に探す依頼、外部との比較が必要な新規計画に使います。
通常の修正、翻訳、方針が確定した実装で新たな検索を始めるものではありません。
採用、新規性、法的な位置付け、事業性の判断、候補の実行、依頼されていない追加調査は
行いません。[対象範囲](docs/scope.md)を参照してください。

## 根拠と制約

- **公開ソースからのインストールを確認済み：** 主手順とコピー方式を、それぞれ新しいプロジェクトで検証しました。中核ファイルと LICENSE は公開版とバイト単位で一致しました。[公開検証](docs/release-checklist.md#public-release-verification-2026-10-22)
- **14ケースの監査：** 品質タスク8件と選択対照6件を、新しい子コンテキストで実施しました。ホストの指示は共有されており、完全に独立した盲検試験ではありません。初期プロンプト全体と構造化されたローダーのイベントは記録されていません。[評価結果](evals/results.md)
- **ホストごとの観察を区別：** Mac の公開検証では、新しい Codex セッションは NOT TESTED のままです。その後の Windows のインストール・使用はユーザー報告で、実行の生記録はこのリポジトリに保存されていません。[Windows の要約と制約](docs/examples.md#windows-user-reported-observation)

これらの観察から、正答率、網羅的な発見、ハルシネーションの排除、適切な通常の
Codex プロンプトや他の Skill に対する優位性は示せません。独立した A/B/C 比較、
開発に使っていない評価ケースによる検証、候補の実際の動作、正確な費用、ホスト間で
安定した自動選択は未検証です。直接インストールできても、skills.sh への掲載、
`skills find` での発見、find-skills による推薦は保証されません。

## 関連資料とライセンス

[ほかの例と元の記録](docs/examples.md) · [既存ワークフローとの比較](docs/comparison.md) ·
[評価方法](evals/README.md) · [M4 当時の公開準備](docs/release-preparation.md)

保守の基準は英語版で、翻訳も同じ主張と制約を保ちます。中核の指示は
[SKILL.md](skills/prior-scout/SKILL.md)、開発時の制約は [AGENTS.md](AGENTS.md) にあります。
非公開の生記録と元の開発 Git 履歴は、この公開リポジトリに含めていません。

MIT License。Copyright (c) 2026 orange-clockwork。[ルートの LICENSE](LICENSE) と
[インストール対象のコピー](skills/prior-scout/LICENSE) は同じ条項です。
第三者の名称やリンク先資料の権利は各権利者に帰属し、元資料の全文は配布しません。
