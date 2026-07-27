# TG URL Gateway

独立 Telegram 链接入口站。`index.html` 负责选择启用链接并展示短暂、用户可见的中转页；`admin.html` 用管理员密钥管理链接；Cloudflare Pages Function 安全读写 GitHub 的 `data/links.json`。

## 重要边界

- 仅用于清晰、可见的用户引导，不用于隐藏跳转或规避平台规则。
- `GITHUB_TOKEN`、`ADMIN_TOKEN` 只能放 Cloudflare Secrets，不能提交到仓库。
- 入口页读取 Function 的最新数据，因此保存后无需重新构建静态页面。
