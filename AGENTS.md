# AI エージェント向けガイド

このリポジトリは **仕様駆動** の補助文書セットです。実装や変更を行う前に、次の順で読むことを推奨します。

**文書の正**: テンプレ本文の参照元は **リモートにプッシュされた版**（例: `main` または作業ブランチの先端）とすること。他マシン・別セッションにのみ存在するローカルコミットは、ハッシュが異なっていても内容の根拠にしない（未 push のコミットは他環境から参照できない）。

## 読む順序

1. [docs/charters/PROJECT_CHARTER.md](docs/charters/PROJECT_CHARTER.md) — 何のためのプロジェクトか、何をしてはいけないか
2. [docs/charters/DEVELOPMENT_CHARTER.md](docs/charters/DEVELOPMENT_CHARTER.md) — 品質・安全・コラボレーションの原則
3. [docs/process/SPEC_DRIVEN_DEVELOPMENT.md](docs/process/SPEC_DRIVEN_DEVELOPMENT.md) — 仕様と実装の対応付け
4. [docs/process/AGENT_OPERATING_GUIDE.md](docs/process/AGENT_OPERATING_GUIDE.md) — 自律的に進めてよい範囲と、PR で論点提示する範囲
5. [docs/process/HUMAN_IN_THE_LOOP.md](docs/process/HUMAN_IN_THE_LOOP.md) — 人間レビュー時に確認する論点
6. [docs/specs/SPEC-INDEX.md](docs/specs/SPEC-INDEX.md) — 有効な仕様一覧。作業対象の SPEC を開く
7. [docs/process/GIT_WORKFLOW.md](docs/process/GIT_WORKFLOW.md) — ブランチ名、コミット、PR の慣習

## 作業時のルール（要約）

- **仕様が単一の真実の源泉**: 曖昧なら SPEC を更新する PR を先に切る。勝手に仕様を広げない
- **小さな変更単位**: 1 PR（または論理的なまとまり）で一つの意図に寄せる
- **証跡**: テスト・手動確認・レビュー結果は [docs/testing/TESTING_STRATEGY.md](docs/testing/TESTING_STRATEGY.md) に沿って PR や SPEC に残す
- **PR は完走させる**: 中途で止めない。論点があれば PR 本文に明記して人間レビューに委ねる

## 人間へのエスカレーション

本テンプレートは **エスカレーション ＝ PR レビューで人間に判断を委ねる** という設計を採る。エージェントは以下のフローを守る：

1. 作業を最後まで完走させる（テスト追加・リント修正・ビルド成功まで）
2. [HUMAN_IN_THE_LOOP.md](docs/process/HUMAN_IN_THE_LOOP.md) の論点に該当する変更があれば、PR 本文の「マージ前確認事項（HITL）」セクションに該当項目を**チェックして理由を併記**
3. PR を作成し、人間レビュアの承認を待つ
4. レビュアからのコメントには別コミットで応答し、再度承認を待つ

**中途で止まって人間に質問するのは原則しない**。判断材料を PR で揃えてから委ねる。

## 例外: 中途で止まるべき技術的な状況

以下は技術的に不可避なため停止する：

- 秘密情報（鍵・トークン・本番認証情報）に触れざるを得ない
- 破壊的シェル操作（`rm -rf` 等）が必要に見える
- 外部 API への本番書き込み（決済・メール送信等）
- リポジトリの保護ブランチへの直 push が必要に見える

これらは設定（[`.claude/settings.json`](.claude/settings.json)）で技術的にもブロックされている前提。ブロックされた場合のみ、ユーザーに状況を報告して指示を仰ぐ。
