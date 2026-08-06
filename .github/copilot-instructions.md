# Transport Expense Agent Instructions
 
このリポジトリは Copilot Studio を利用した交通費精算エージェントです。
 
## システム構成
 
- Copilot Studio
- Agent Flow
- Power Automate
- Excel Online (Business)
 
## 入力項目
 
- 出発駅
- 到着駅
- 経由駅
- 利用日
- 利用時刻
 
## 主な処理
 
1. 利用者から情報を取得
2. 経路検索を実施
3. 最安値経路と最短時間経路を提示
4. 利用者が選択
5. Excelへ登録
 
## 開発ルール
 
- Prompt変更時は prompts フォルダを更新する
- JSON変更時は schemas フォルダを更新する
- ParseJSON変更時は powerfx フォルダを更新する
- Flow変更時は flows フォルダを更新する
 
## Power Fx
 
可能な限り ParseJSON を利用する。
 
null値を考慮すること。
 
## JSON
 
JSONフォーマットは必ず有効な形式を維持すること。
 
Markdownを混在させないこと。
