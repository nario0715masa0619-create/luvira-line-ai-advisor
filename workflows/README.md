# Workflows

このディレクトリには、n8nワークフローのsource-of-truthとなるJSONを保存します。

`line-ai-question-box-v1.json` は、n8nワークフローのcredential-free exportです。構造とバージョンの追跡だけを目的とします。

`line-scheduled-broadcast-v1.json` は、未公開・DRY RUNのLINE Broadcast予約配信ワークフローのcredential-free exportです。今回のLINE公式管理画面で予約済みの10件には使わず、将来の自動配信用に保持します。

実際の認証情報はn8nで管理し、credential values、APIキー、LINE Channel Access Token、またはその他の認証情報をこのリポジトリへコミットしてはいけません。
