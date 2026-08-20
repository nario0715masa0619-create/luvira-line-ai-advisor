# Architecture

## Components

- **LINE Official Account**: 利用者の入口とリッチメニュー
- **LINE Messaging API**: メッセージ受信・返信
- **n8n**: Webhook、分岐、返信処理の自動化
- **OpenAI**: 通常メッセージへの短いAI回答
- **GitHub repository**: 文書、プロンプト、ワークフローJSONのsource of truth

## Current data flow

`LINE Official Account → LINE Messaging API → n8n Webhook → Extract LINE Data → Keyword Switch → Fixed reply または OpenAI → Send LINE Reply`

リッチメニューは短いキーワードだけを送信し、長い返信本文はn8nで管理する。
