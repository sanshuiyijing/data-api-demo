# data-api-demo

connect with codex

## GitHub Actions

This repository includes two PR automations under `.github/workflows`:

- `codex-pr-review.yml`: runs Codex review when a pull request is opened or updated, then posts or updates a sticky PR comment.
- `auto-approve-bot-thumbs-up.yml`: scans PR comments and reviews for Codex bot responses containing `👍` or `thumbs up`, then creates an `APPROVE` review without merging the PR.

### Required setup

- Add the repository secret `OPENAI_API_KEY` so `codex-pr-review.yml` can authenticate the Codex CLI.
- If your Codex bot login is not `codex[bot]` or `chatgpt-codex-connector[bot]`, update `CODEX_BOT_LOGINS` in `auto-approve-bot-thumbs-up.yml`.



test


1111




2222