# CS-transport-expense-agent

Copilot Studio で作成する「交通費精算エージェント」の設計資産、プロンプト、JSONスキーマ、Power Fx、Power Automate Flow定義、テストデータを管理するためのリポジトリです。

## 目的

このリポジトリでは、交通費精算エージェントに関する以下の資産を Git で管理します。

- Copilot Studio のエージェント設計
- プロンプトと Instructions
- 経路検索結果の JSON スキーマ
- Power Fx 式
- Power Automate Flow の入出力仕様
- Excel 登録項目の定義
- テストデータ
- リリース履歴

## 想定するエージェント構成

```text
ユーザー
  ↓
Copilot Studio 交通費精算エージェント
  ↓
Route Agent: 経路検索
  ↓
Expense Agent: 精算データ作成
  ↓
ExpenseRegistration Flow: Excel 登録
  ↓
必要に応じて Approval Agent / Audit Agent
```

## ディレクトリ構成

```text
CS-transport-expense-agent
├─ README.md
├─ docs
│  ├─ 要件定義.md
│  ├─ 業務フロー.md
│  ├─ システム構成.md
│  └─ 運用手順書.md
├─ prompts
│  ├─ route-search-agent.md
│  ├─ route-selection-agent.md
│  └─ expense-registration-agent.md
├─ schemas
│  ├─ route-response.schema.json
│  ├─ expense-request.schema.json
│  └─ approval-request.schema.json
├─ powerfx
│  ├─ ParseJsonExpressions.md
│  ├─ RouteSelection.md
│  └─ ValidationRules.md
├─ flows
│  ├─ RouteSearch
│  │  ├─ README.md
│  │  └─ definition-placeholder.json
│  ├─ ExpenseRegistration
│  │  ├─ README.md
│  │  └─ definition-placeholder.json
│  └─ ApprovalNotification
│     ├─ README.md
│     └─ definition-placeholder.json
├─ agents
│  ├─ RouteAgent
│  │  └─ README.md
│  ├─ ExpenseAgent
│  │  └─ README.md
│  ├─ ApprovalAgent
│  │  └─ README.md
│  └─ AuditAgent
│     └─ README.md
├─ environment
│  ├─ dev.md
│  ├─ test.md
│  └─ prod.md
├─ testdata
│  ├─ sample-user-input.md
│  ├─ sample-route-response.json
│  └─ sample-expense-request.json
├─ releases
│  └─ v0.1
│     └─ release-notes.md
└─ .github
   └─ workflows
      └─ README.md
```

## 管理対象

| 種別 | 管理場所 | 内容 |
|---|---|---|
| エージェント設計 | `docs/` | 要件、業務フロー、構成、運用手順 |
| Prompt / Instructions | `prompts/` | Copilot Studio に設定する指示文 |
| JSON スキーマ | `schemas/` | 経路検索結果、精算登録、承認依頼のデータ構造 |
| Power Fx | `powerfx/` | ParseJSON、入力チェック、選択ロジック |
| Flow定義 | `flows/` | Power Automate の入出力仕様、エクスポート定義 |
| テストデータ | `testdata/` | 動作確認用の駅名、日時、経路JSON |
| リリース履歴 | `releases/` | 変更内容、既知の課題、反映日 |

## ブランチ運用例

```text
main      : 本番反映済み
feature/* : 個別改修用
fix/*     : 不具合修正用
```

例:

```text
feature/route-json-schema
feature/excel-registration-flow
fix/parsejson-null-error
```

## コミットメッセージ例

```bash
git commit -m "経路検索プロンプトを改善"
git commit -m "交通費JSONスキーマにviaStationを追加"
git commit -m "Excel登録Flowの入力項目を整理"
git commit -m "ParseJSONのnull対策を追加"
```

## 初期セットアップ

```bash
git clone https://github.com/fuguchiri0901/CS-transport-expense-agent.git
cd CS-transport-expense-agent
```

このテンプレートの内容をリポジトリに配置したら、次のコマンドで反映します。

```bash
git add .
git commit -m "交通費精算エージェントの初期構成を追加"
git push origin main
```

## 運用ルール

- Copilot Studio の Prompt を変更したら `prompts/` も更新する
- JSON構造を変更したら `schemas/` と `testdata/` を更新する
- Power Fx を変更したら `powerfx/` に変更理由を残す
- Power Automate Flow を変更したら `flows/` の README に入出力差分を記録する
- 本番反映したら `releases/` にリリースノートを追加する

## 現在のステータス

| 項目 | 状態 |
|---|---|
| Copilot Studio エージェント | 作成中 |
| 経路検索Flow | 作成中 |
| Excel登録Flow | 作成中 |
| JSONスキーマ | 初期案 |
| Git管理 | 初期構成 |

## 注意事項

このリポジトリには、個人情報、実際の交通費申請データ、APIキー、接続文字列、トークンを含めないでください。

