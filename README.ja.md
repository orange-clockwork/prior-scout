[English](README.md) | [日本語](README.ja.md) | [繁體中文](README.zh-TW.md) | [简体中文](README.zh-CN.md)

# Prior-Scout

**既存の成果を探す。根拠を確かめてから伝える。**

Prior-Scout（先例探索）は、開発前に既存の選択肢を調べるための、指示だけで構成された
小さな Agent Skill です。要件、URL、読み取り可能な文書をもとに公開情報を検索し、
関連する機能を確認します。ツール、サービス、Skill、ライブラリ、研究実装の
共通点と重要な違いを簡潔にまとめます。

**`0.1.1-experimental` · GitHub で公開中 · MIT**

## 実際の動作例

`0.1.1-experimental` を使った 2026-10-22 の監査から、実際の入力を日本語に訳しています。

> Markdown のリンクチェッカーを実装する前に、既存のオープンソースの選択肢を探し、
> 関連する違いを説明してください。その後、元のチェッカーの簡単な実装方針をまとめてください。
> ファイルは変更しないでください。

**結果の要約** — 記録された回答を短くまとめた日本語訳です。

| 候補 | 資料で確認できたこと | 用途に関わる違い |
| --- | --- | --- |
| [Lychee](https://github.com/lycheeverse/lychee) — CLI／ライブラリ | Markdown、HTML、Web サイトのリンクを検査する。 | アンカーの検査には `--include-fragments` が必要。JavaScript が生成するアンカーは検査できない。[資料](https://lychee.cli.rs/recipes/anchors/) |
| [markdown-link-check](https://github.com/tcort/markdown-link-check) — Node.js CLI／ライブラリ | リンクの到達可能性を検査し、HTTP 設定や再試行に対応する。 | 読み取った README では、別ファイルの見出しの検証は**確認できなかった**。 |
| [remark-validate-links](https://github.com/remarkjs/remark-validate-links) — remark プラグイン | ローカルのファイル、画像、見出しをオフラインで検査する。 | **別ファイルの見出しの検査は remark CLI で利用でき、Node API では利用できない。** 外部 URL は対象外。 |

機能が資料で裏付けられているか、どの利用方法で使えるか、何が未確認かまで区別します。
比較後は、依頼されていた元の実装方針に戻りました。

この過去のサブエージェント実行では、**検索クエリ2件、外部根拠文書4件**を使用しました。
候補ツールのインストールや実行はしていません。資料に基づく確認であり、精度の測定や
ネイティブ自動選択の証明ではありません。[入力原文・資料・制約](docs/examples.md#t2-markdown-link-checker)。

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
次は呼び出し方の例であり、上記の過去の入力とは別です。

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
