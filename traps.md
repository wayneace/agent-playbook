# 踩坑索引

> 一行一条：症状 → 先查什么 → 搜什么。只指路，不抄答案。

| 症状 | 先查什么 | 搜索词 |
|---|---|---|
| 浏览器能上网，但 agent 用 uv / bun / curl / npm 拉取内容超时 | Clash 是否开了 TUN；命令行工具是否配了代理 | clash tun mode command line proxy |
| GitHub 操作提示 rate limit | GitHub CLI 是否登录 | gh auth login github api rate limit |
| Cherry 网络搜索慢或经常失败 | 是否用了模型内置 Web 工具；是否配了 Firecrawl / Tavily | cherry studio web search provider firecrawl tavily |
