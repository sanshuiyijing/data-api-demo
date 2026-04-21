Auto-approve Codex bot comments
================================

这个工作流会在 PR 的评论创建时触发；如果评论者是配置中的 Codex 机器人（或多个机器人之一），并且评论里包含指定的触发字符（默认是点赞符号），它会自动为该 PR 创建一个 APPROVE review。

配置
-----
- 在 .github/workflows/auto-approve-codex.yml 中你可以配置两个环境变量：
  - CODEX_BOT_LOGINS：允许触发自动 approve 的 bot 登录名，多个用逗号分隔，默认 codex[bot]。
  - APPROVE_EMOJIS：触发 approve 的文本/emoji 列表，多个用逗号分隔，默认 一个点赞字符。例如可以设置 "👍,👍🏻,LGTM"。

注意事项
--------
- GitHub 自动提供的 GITHUB_TOKEN 需要有 pull-requests: write 权限以创建 review；工作流顶部已声明该权限。请确保组织或仓库没有进一步限制该 token 的权限。
- 如果 PR 来自 fork 仓库，在某些仓库设置下 GITHUB_TOKEN 可能无法对该 PR 做出 review（取决于仓库/组织安全策略）；如果遇到权限问题，考虑使用一个有更高权限的 GitHub App 或者手动审批流程。
- 默认比较是大小写不敏感的（bot 登录名），trigger 比较是包含匹配（comment body includes trigger）。如果需要更严格的匹配规则，可按需修改工作流脚本。

测试
----
1. 将 CODEX_BOT_LOGINS 临时设置为你的账号名（例如 your-username），把 APPROVE_EMOJIS 保持为点赞字符。
2. 在某个 PR 上以你的账号发表评论一个点赞符号。
3. 如果配置正确，工作流会运行并在 Actions 页面显示执行结果，且 PR 应收到由工作流创建的 Approve review。

扩展建议
-------
- 可以增加一个仓库级别的 secrets 或 repository_dispatch 配置来更灵活地控制哪些 bot 能触发 approve。也可以把触发器转为 issue_comment 的 created,edited，以处理机器人更新评论的场景。
