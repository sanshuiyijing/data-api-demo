# data-api-demo

connect with codex

## GitHub Actions

This repository includes one PR automation under `.github/workflows`:

- `codex-review-gate.yml`: evaluates Codex bot comments and reactions, then reports the required status check `codex-review-gate` for pull requests.

### Required setup

- If your Codex bot login is not `chatgpt-codex-connector` or `chatgpt-codex-connector[bot]`, update the `botLogins` set in `codex-review-gate.yml`.

### Review source

Codex review generation is expected to come from the ChatGPT/Codex GitHub integration you enabled in settings. This repository workflow reacts to Codex output and reports the gate result through the `codex-review-gate` required status check.

This is a test repo.