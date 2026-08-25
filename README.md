# Luvira LINE AI Advisor

LINE Official Accountで、中小企業の経営者へAIの基礎を経営目線で届ける無料の価値提供パッケージです。

## Current MVP

- LINEリッチメニュー
- n8n WebhookとLINE Messaging APIの連携
- リッチメニューの固定返信
- 通常メッセージを受けるAI質問箱
- 経営者向けの短いAI回答

## Technologies used

- LINE Official Account / LINE Messaging API
- n8n
- OpenAI
- GitHub

## What currently works

リッチメニューの各ボタンは短いキーワードを送信します。n8nがキーワードを判定し、固定返信またはOpenAIによるAI質問箱の回答をLINEへ返します。

## Planned features

- AI導入5分診断
- 社長向けプロンプト集
- AI利用ルールひな形
- 週次まとめ配信
- コンテンツ作成・レビュー・配信の自動化

## Repository structure

- `docs/`: プロダクト、設計、運用、安全性の文書
- `prompts/`: OpenAIで使うプロンプト原本
- `data/`: コンテンツ企画の元データ
- `workflows/`: n8nワークフローの安全なJSONエクスポート

## Operations documentation

- [コンテンツ運用](docs/content-operations.md): 配信頻度、人間レビュー、本文重複管理
- [スプレッドシート運用](docs/spreadsheet-operations.md): `AI顧問配信管理` の管理項目と運用
- [AI質問箱運用](docs/ai-question-box-operations.md): 回答モデル、利用範囲、規模拡大時のガードレール

## Secret handling

APIキー、LINE Channel Access Token、n8nの認証情報は絶対にコミットしません。ワークフローJSONにもcredential valuesを含めません。
