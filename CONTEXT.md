# ui-ux-pro-max-skill Context

## 项目定位

UI UX Pro Max 是一个面向 AI 编程助手的 UI/UX 设计智能库，包含 UI 风格、配色、字体、图表类型、产品建议、UX 规则和多技术栈最佳实践。

它同时分发给 Claude Code、Codex、Cursor、Windsurf、Antigravity、Kiro、GitHub Copilot 等不同助手生态。

## 关键结构

- `.claude/skills/ui-ux-pro-max/`: Claude Code skill。
- `.codex/skills/ui-ux-pro-max/`: Codex skill。
- `.agent/`、`.cursor/`、`.windsurf/`、`.github/`、`.kiro/`: 各助手工作流或 prompt。
- `.shared/ui-ux-pro-max/`: 共享数据副本。
- `cli/`: CLI 包和安装资产。
- `README.md`: 安装和使用说明。
- `CLAUDE.md`: 搜索命令、架构和同步规则。

## 工作规则

- 修改数据、脚本或 SKILL 文档时，必须按 `CLAUDE.md` 的同步规则更新所有对应副本。
- 搜索能力基于 Python 脚本和 CSV 数据，改动后要验证各 domain/stack 查询。
- Git 工作流要求不要直接 push 到 `main`，应创建分支、提交、推分支并开 PR。
- 这是多助手分发项目，避免只改一个生态导致版本漂移。

## 常用命令

```bash
python3 .claude/skills/ui-ux-pro-max/scripts/search.py "saas dashboard" --domain product
python3 .claude/skills/ui-ux-pro-max/scripts/search.py "landing page" --stack nextjs
```

## 验证要求

- Python 脚本修改后运行对应 search 命令。
- CLI 修改后在 `cli/` 下运行 package 脚本或安装测试。
- 同步类修改后全库搜索确认各 assistant 版本一致。
