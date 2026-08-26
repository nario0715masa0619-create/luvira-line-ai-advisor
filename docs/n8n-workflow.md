# n8n workflow

## Workflow

- Name: `LINE AI質問箱 v1`
- Production Webhook URL: `https://luvira-devflow.app.n8n.cloud/webhook/line-ai-question-box`

## Node-level processing flow

`LINE Webhook → Extract LINE Data → Keyword Switch → Fixed reply or OpenAI route → Send LINE Reply`

## Keyword switch behavior and fixed replies

| キーワード | 返信 |
| --- | --- |
| AI質問箱 | AIについて分からないことを、このLINEにそのまま送ってください。 |
| AI診断 | AI導入5分診断はただいま準備中です。まずはAIについて気になることを、このLINEに送ってください。 |
| プロンプト | 社長向けプロンプト集はただいま準備中です。準備ができ次第、このLINEでお知らせします。 |
| AIルール | AI利用ルールひな形はただいま準備中です。社員にAIを使わせる前の注意点からお届け予定です。 |
| 今週まとめ | 今週のまとめはただいま準備中です。配信開始後にこちらから確認できるようにします。 |
| お知らせ | お知らせはただいま準備中です。無料勉強会や更新情報はこちらでご案内します。 |

## OpenAI fallback route

上記以外の通常メッセージはOpenAIへ渡し、AI質問箱として回答する。

## Publish and test notes

変更後はワークフローを保存・Publishし、LINEアプリから各キーワードと通常質問を送って確認する。JSONをエクスポートする前にcredential valuesが含まれないことを確認する。

## LINE Scheduled Broadcast v1 — 運用メモ

`LINE Scheduled Broadcast v1` は、将来のLINE公式アカウント向け自動配信に備えて作成した予約配信ワークフローである。現在は **未公開**、`dry_run=true`、Schedule Trigger未稼働の状態で保持する。DRY RUNの手動実行は成功しており、`dry_run=true` の場合はLINE Broadcast APIを呼び出さず、予定本文・日時・`message_id` のログだけを出力する。

今回の10件はLINE公式管理画面で予約済みである。このため二重配信を防止するために、当該予約分にはこのn8nワークフローを使用しない。今回の予約配信がすべて完了するまで、Publish、`dry_run=false` への変更、Schedule Triggerの稼働を行ってはならない。

ワークフローのcredential-free exportは `workflows/line-scheduled-broadcast-v1.json` に保存する。認証情報はn8nのCredentialまたは環境変数（`LINE_CHANNEL_ACCESS_TOKEN`）で管理し、トークン値・APIキー・Credential値をリポジトリに含めない。
