# 配置指南

> 这里只记录「装什么、开什么、为什么」。安装命令一律现场从链接里的 README 获取。
> 最后核对：2026-11-02。

## 能力增强

### Office 能力
- 作用：让 agent 读写 Word / Excel / PPT。
- 安装：把链接直接发给 agent，让它拉取网页内容、按 README 安装。
- 链接：https://github.com/iOfficeAI/OfficeCLI
- 平台：Windows / macOS / Ubuntu 按 README 对应说明执行。

### 本地浏览器控制（技能 + 插件）
- 作用：agent 操作你已登录的浏览器（读页面、点击、填表、截图）。
- 组成：技能 + 插件，两者都要装。
- 安装：把链接直接发给 agent。
- 链接：https://github.com/Tencent/BrowserSkill

### GitHub 增强
- 作用：agent 读写 issue / PR；登录后可突破 GitHub API 的匿名速率限制。
- 路径：Cherry Studio → 设置 → 环境依赖 → GitHub CLI（按需）。
- 登录：`gh auth login`，每个成员用自己的账号。
- 备注：不装也能用，但速率限制会明显影响体验。

## 网络前提

### Clash 需要 TUN 模式
- 原因：agent 会通过 `uv`、`bun`、`curl`、`npm` 等命令行工具从外网拉取内容。这类工具通常不读系统代理设置，只有 TUN 模式能覆盖它们。
- 表现：浏览器能上网，但 agent 安装依赖 / 拉取内容时报连接超时。
- 处理：Clash 开启 TUN 模式；或给命令行工具显式配置代理环境变量（`HTTP_PROXY` / `HTTPS_PROXY`）。
- 注意：TUN 模式对其他软件的影响，按需评估。

## Cherry Studio 设置

### 浏览器
- 路径：设置 → 浏览器 → 通过内置浏览器打开网站链接。
- 推荐：**关闭**。
- 理由：用系统浏览器打开更方便；需要内置浏览器时再按需开启。

### 网络搜索
- 路径：设置 → 网络搜索 → 优先使用模型内置 Web 工具。
- 推荐：**关闭**，优先使用下面的服务商。
- 服务商：去官网注册账号并获取 API Key，可以突破速率限制。
- 推荐：**Firecrawl**、**Tavily**（两者都提供 WebSearch + WebFetch）。

### 渠道（远程控制 agent）
- 飞书、微信：在 Cherry Studio 的渠道设置里接通后，可以用这两个软件控制 agent。
- 手机端：Cherry Studio 有手机客户端（beta），也可以远程控制 agent。
- 备注：渠道里能用的工具受 agent 的 environment / 权限限制；不是所有 agent 都能在渠道里跑全部工具。

## 平台差异

三个平台都适用。差异只在安装命令和配置路径，以上游链接的平台说明为准；遇到平台特有的坑，记到 `traps.md`。
