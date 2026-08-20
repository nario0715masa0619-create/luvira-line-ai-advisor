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
