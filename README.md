# data-api-demo

connect with codex

## GitHub Actions

This repository includes one PR automation under `.github/workflows`:

- `codex-review-gate.yml`: evaluates Codex bot comments and reactions, then reports the required status check `codex-review-gate` for pull requests.

### Required setup

- If your Codex bot login is not `chatgpt-codex-connector` or `chatgpt-codex-connector[bot]`, update the `botLogins` set in `codex-review-gate.yml`.

### Trigger behavior

- GitHub Actions does not provide a native trigger for adding a reaction, so a new `thumbs up` does not rerun the workflow by itself.
- To re-evaluate immediately after a bot reaction, either send a `repository_dispatch` event of type `codex_review_gate` with `pull_request_number`, or run `codex-review-gate` manually from the Actions tab and provide `pull_request_number`.

### Review source

Codex review generation is expected to come from the ChatGPT/Codex GitHub integration you enabled in settings. This repository workflow reacts to Codex output and reports the gate result through the `codex-review-gate` required status check.

This is a test repo.