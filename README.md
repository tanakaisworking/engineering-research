# Engineering Research

**開発者向けに、信頼性の低い情報源を根拠から外し、実装に使える技術情報を調査・検証するAIエージェント用スキル。**

A research skill for developers: filter out weak evidence and verify technical claims against relevant specifications, implementation, and tests.

API調査、ライブラリ選定、バグ調査で、検索上位の記事をそのまま実装の根拠にしていませんか。複数の記事が同じ資料を言い換えているだけなら、根拠が増えたとは言えません。正しい情報でも、バージョンや実行環境が違えば、そのプロジェクトには適用できないことがあります。

Engineering Researchは、情報源の見た目や記事の数ではなく、**その主張を何で確かめられるか**を判断するための指示をエージェントに与えます。

## このスキルが指示すること

- **根拠までたどる**：公式Docs、仕様、ソースコード、テスト、メンテナーのIssue・PRを、調査する問いに応じて使う。
- **弱い情報を根拠から外す**：独自の検証がないまとめ・転載・SEO記事は、一次情報を探す手掛かりとして扱う。同じ出典の繰り返しを独立した証拠として数えない。
- **対象環境と照合する**：バージョン、OS、ランタイム、更新日、修正済みかどうかを確認する。
- **反証も探す**：制約、非対応環境、既知の不具合、非推奨化など、結論が成立しない条件を調べる。
- **事実と仮説を分ける**：仕様に書かれた事実、再現できた挙動、推論、未検証の情報を区別する。
- **必要なところで止める**：公式Docsの確認で解決する問いには不要な深掘りをしない。追加調査で判断が変わり得る場合に調査を続ける。

個人ブログやStack Overflowも、具体的な再現手順や測定結果があれば有用です。情報源の種類だけで一律に排除せず、主張を支える証拠と適用条件を確認します。

## 使う場面

| 調査 | 確認すること |
|---|---|
| API・SDKの使い方 | 対象バージョンの仕様と、サポートされる使い方 |
| ライブラリ選定・移行 | 互換性、制約、変更履歴、既知の問題 |
| バグ・OS固有の挙動 | 再現条件、関連コード、修正状況 |
| 性能比較 | 測定条件、ワークロード、環境、再現可能性 |
| セキュリティ | 影響を受けるバージョン、修正、技術的根拠 |

Web、デスクトップ、モバイル、バックエンドの開発が対象です。市場分析、価格戦略、マーケティングなどのビジネス調査は対象に含めません。

## インストール

[skills CLI](https://github.com/vercel-labs/skills)で、使用するエージェントを選んで導入できます。

```bash
npx skills add tanakaisworking/engineering-research --skill engineering-research
```

CodexまたはClaude Codeのプロジェクトへ導入する例です。

```bash
npx skills add tanakaisworking/engineering-research --skill engineering-research --agent codex
npx skills add tanakaisworking/engineering-research --skill engineering-research --agent claude-code
```

## 使用例

導入したエージェントに、対象のプロジェクトや調査したい条件と一緒に依頼します。

```text
$engineering-research
このプロジェクトで使っているSDKのバージョンを確認して、
このAPIの正式な使い方と対応するランタイムを調べて。
```

```text
$engineering-research
このエラーに関するIssueと修正履歴を調べて。
回避策が今のOS・ライブラリのバージョンに適用できるか確認して。
```

```text
$engineering-research
この2つのライブラリを、今回の用途と実行環境に合わせて比較して。
比較記事の結論だけでなく、仕様・実装・測定条件まで確認して。
```

## 内容

- [SKILL.md](SKILL.md)：技術調査の範囲、証拠の評価、検証、報告の指示。
- [agents/openai.yaml](agents/openai.yaml)：Codex向けの表示名と呼び出し例。

検索・ブラウザ・コード実行には、利用するエージェントが提供するツールを使います。このリポジトリは調査方針を定めるスキルで、検索サービスそのものは含みません。
