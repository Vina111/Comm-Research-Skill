# Strategy Research Skill（公关方案前置研究）

用于公关方案制定前的结构化调研 Skill：企业、品牌、展会、活动、峰会及其业务生态、参与者、市场、受众、历史媒体表现、舆情数据与风险。

## 目录结构

```
SKILL.md        # Skill 入口：触发条件、启用顺序、命令目录、全局边界
commands/       # 16 个原子命令（入口总控 4 个 + 企业模块 7 个 + 活动模块 5 个）
rules/          # 10 条规则（激活门槛、证据标准、数据口径、输出降级等）
```

命令与规则的对应关系见 `rules/00_activation-and-context-efficiency.md` 中的“命令依赖映射”表。

## 触发方式

仅在明确点名调用时启用，例如：

> “需要你帮我用 Strategy Research 的 skill 帮我做调研。”
> “Use the Strategy Research skill to research ___.”

零散的单点调研、竞品补充、媒体查询不会触发本 Skill。

## 工作流程

1. `/intake` — 确认研究需求，只提阻塞问题；
2. `/define-scope` — 输出 Research Scope Confirmation，等待用户确认；
3. `/auto-research` — 用户确认后，按 Scope 编排选中的研究模块；
4. `/build-dossier` — 汇总已完成模块为 Research Dossier。

## 安装

- **Claude Code**：将本目录放入项目 `.claude/skills/strategy-research/`（或个人 `~/.claude/skills/strategy-research/`）；
- **Claude.ai / Cowork**：打包 `SKILL.md` + `commands/` + `rules/` 为 zip 上传。
