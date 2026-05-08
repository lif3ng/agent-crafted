# Agent Crafted

> Pages crafted by AI agents through conversations.

本仓库是一个**交互式速查手册集合**，每一份手册都是通过与 AI Agent 的对话交流生成的。

## ✨ 特点

- 🎯 **对话驱动** — 每份手册都源于真实的学习对话，包含用户的实际疑问
- 🎨 **精美排版** — 暗色主题，代码高亮，交互式卡片布局
- 🔊 **术语发音** — 点击即可听到英文术语的神经网络语音朗读
- 📱 **响应式** — 手机、平板、桌面端均可正常浏览
- 🚀 **即开即用** — 纯 HTML 单文件，无需服务器，GitHub Pages 直接托管

## 📚 手册列表

| 标题 | 简介 | 标签 | 路径 |
|------|------|------|------|
| [Tailscale 完全速查手册](tailscale/) | VPN 组网工具全覆盖：日常命令、端口暴露、网络排查、进阶配置 | 🟢 网络 | `tailscale/` |
| [Crontab 交互式学习手册](crontab/) | Cron 定时任务完全指南：语法解析、交互式练习、常用示例、在线调试 | 🟡 运维 | `crontab/` |

## 🏗️ 仓库结构

```
agent-crafted/
├── README.md              ← 本文件（也是入口页的数据源）
├── design.md              ← 入口页设计规范（Vercel 风格）
├── build.py               ← 构建脚本：README.md → index.html
├── index.html             ← 构建产物（入口页）
├── .github/
│   └── workflows/
│       └── build.yml      ← GitHub Actions：push 时自动构建
│
├── tailscale/             ← 每个主题一个目录
│   ├── index.html         ← 速查手册
│   └── pron/              ← 术语发音音频
│       ├── tailscale.mp3
│       └── ...
│
├── crontab/            ← Crontab 交互式学习手册
│   └── index.html
└── {topic}/               ← 未来新增的手册
    ├── index.html
    └── pron/
```

## 🤖 工作流

1. 与 AI Agent 对话交流学习某个工具
2. Agent 生成交互式 HTML 手册 + 术语发音音频
3. 创建 `{topic}/` 目录，推送到本仓库
4. GitHub Actions 自动构建入口页
5. 1-2 分钟后即可在 [lif3ng.github.io/agent-crafted](https://lif3ng.github.io/agent-crafted/) 访问

## 🔧 本地构建

```bash
python3 build.py
# 生成 index.html（入口页）
```

## 📜 License

MIT
# test2
