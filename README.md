# data-api-demo

connect with codex

## GitHub Actions

This repository includes one PR automation under `.github/workflows`:

- `auto-approve-bot-thumbs-up.yml`: scans PR comments and reviews for Codex bot responses containing `👍` or `thumbs up`, then creates an `APPROVE` review without merging the PR.

### Required setup

- If your Codex bot login is not `codex[bot]` or `chatgpt-codex-connector[bot]`, update `CODEX_BOT_LOGINS` in `auto-approve-bot-thumbs-up.yml`.
- Add the repository secret `PR_APPROVER_TOKEN`. This must be a GitHub App installation token or personal access token that is allowed to submit PR approvals in this repository; the default `GITHUB_TOKEN` is not sufficient here.

### Review source

Codex review generation is expected to come from the ChatGPT/Codex GitHub integration you enabled in settings. This repository workflow only reacts to Codex output and auto-approves when the configured bot leaves a matching thumbs-up signal.



test


1111




2222