# Operation manual

## Update rich menu text

LINE Official Account Managerでボタン表示・アクションを更新する。アクションは短いキーワードを維持し、変更時はn8nのKeyword Switchも同時に確認する。

## Update fixed replies

n8nのKeyword Switch後の固定返信ノードを編集し、保存してPublishする。

## Update OpenAI prompt

`prompts/ai-question-box-system-prompt.md`を原本として更新し、n8nのOpenAIノードへ反映する。認証情報は編集・記録しない。

## Publish checklist

- リッチメニューとKeyword Switchのキーワードが一致している
- 固定返信を確認した
- 通常メッセージがOpenAI fallbackへ進む
- ワークフローを保存・Publishした
- credential valuesをJSONやGitへ含めていない

## LINE app test checklist

- 各リッチメニューボタンをタップする
- 6つの固定返信を確認する
- 通常のAI質問を送り、短い回答を確認する
- 返信失敗や重複返信がないことを確認する

## Debug with n8n Executions

n8nのExecutionsで該当イベントを開き、Webhook受信、抽出データ、分岐、OpenAI route、LINE返信の順に確認する。ログや画面共有に認証情報を含めない。
