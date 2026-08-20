# Security notes

- APIキー、LINE Channel Access Token、n8n credential valuesはコミットしない。
- `.env`、`secrets/`、`credentials/`はGit管理しない。
- Webhook URLはcredentialではないが、不必要に広く共有せず慎重に扱う。
- AIの回答は正確性を保証しない。重要な判断は一次情報・専門家で確認する。
- 医療、法律、税務、金融などの専門領域では、断定的な助言を避ける。
