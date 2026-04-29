# aidev_template

汎用の **仕様駆動 AI 開発** テンプレートです。特定の言語・フレームワーク・クラウドに依存せず、プロジェクトにコピーまたは参照して使えます。

## 含まれるもの

| 領域 | パス | 概要 |
|------|------|------|
| エージェント向け入口 | [AGENTS.md](AGENTS.md) | AI エージェントが最初に読むガイド |
| プロジェクト憲章 | [docs/charters/PROJECT_CHARTER.md](docs/charters/PROJECT_CHARTER.md) | 目的・スコープ・ステークホルダー |
| 開発憲章 | [docs/charters/DEVELOPMENT_CHARTER.md](docs/charters/DEVELOPMENT_CHARTER.md) | 品質・安全・協働の原則 |
| 仕様駆動開発 | [docs/process/SPEC_DRIVEN_DEVELOPMENT.md](docs/process/SPEC_DRIVEN_DEVELOPMENT.md) | 仕様のライフサイクルとレビュー |
| Git ワークフロー | [docs/process/GIT_WORKFLOW.md](docs/process/GIT_WORKFLOW.md) | ブランチ・コミット・PR・マージ |
| Human-in-the-loop | [docs/process/HUMAN_IN_THE_LOOP.md](docs/process/HUMAN_IN_THE_LOOP.md) | 人の判断が入るポイント |
| エージェント運用 | [docs/process/AGENT_OPERATING_GUIDE.md](docs/process/AGENT_OPERATING_GUIDE.md) | 自動化と人の役割の境界 |
| 仕様インデックス | [docs/specs/SPEC-INDEX.md](docs/specs/SPEC-INDEX.md) | 全仕様への目次 |
| 仕様テンプレート | [docs/specs/SPEC-000-template.md](docs/specs/SPEC-000-template.md) | 新規 SPEC のひな形 |
| テスト戦略 | [docs/testing/TESTING_STRATEGY.md](docs/testing/TESTING_STRATEGY.md) | 方針とテスト証跡の残し方 |
| PR テンプレート | [.github/PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md) | レビュー用チェックリスト |

## 使い方

1. このリポジトリをフォークするか、`docs/` と `AGENTS.md` を自分のプロジェクトにコピーする。
2. [PROJECT_CHARTER.md](docs/charters/PROJECT_CHARTER.md) と [DEVELOPMENT_CHARTER.md](docs/charters/DEVELOPMENT_CHARTER.md) をプロジェクトに合わせて埋める。
3. [SPEC-000-template.md](docs/specs/SPEC-000-template.md) を複製し、`SPEC-001-...` のように番号と題名を付け、[SPEC-INDEX.md](docs/specs/SPEC-INDEX.md) に登録する。
4. チームで [GIT_WORKFLOW.md](docs/process/GIT_WORKFLOW.md) と [HUMAN_IN_THE_LOOP.md](docs/process/HUMAN_IN_THE_LOOP.md) を合意する。

## ライセンス

リポジトリのルートに `LICENSE` を置く場合は、プロジェクト方針に従ってください（本テンプレートは文書のみのため、デフォルトではライセンスファイルは含めていません）。
