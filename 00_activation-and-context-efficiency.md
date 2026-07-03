# 规则目的

定义本 Skill 的显式启用条件、确认流程和按需读取规则，避免零散 Research 误触发以及无关 Reference 占用上下文。

# 一、显式启用门槛

只有用户明确要求使用名为 **Strategy Research** 的 Skill 时才启用，例如：

- “需要你帮我用 Strategy Research 的 skill 帮我做调研”；
- “请调用 Strategy Research Skill”；
- “这个任务按 Strategy Research Skill 来做”。

启用需要同时满足：

1. 用户明确提到 `Strategy Research`；
2. 用户明确要求“使用、调用、按照该 Skill 执行”。

仅提到 Research、调研、竞品、媒体、市场、展会或风险，不构成启用条件。

# 二、不得自动启用的情况

以下请求按普通任务处理，不读取本 Skill：

- “帮我简单查一下这家公司”；
- “看看这个市场怎么样”；
- “找一下这场展会以前有哪些品牌”；
- “帮我补几个竞品”；
- “查一下某家媒体或某篇报道”；
- 其他零散、单点或临时 Research。

即使普通任务与本 Skill 的模块重合，也不得自行升级为完整 Strategy Research 流程。

# 三、启用后的三阶段门槛

## Stage 1：需求确认

收到显式调用后，只读取：

- `SKILL.md`；
- `commands/01_intake.md`；
- `rules/00_activation-and-context-efficiency.md`；
- `rules/01_intake-gate.md`。

此阶段仅识别已知信息并向用户提出最少必要问题，不开展正式研究，不读取其他 Commands 或 Rules。

如用户已说明部分需求，不得重复提问。

## Stage 2：Scope 确认

用户回答 Intake 后，只读取：

- `commands/02_define-scope.md`；
- 与任务路由直接相关的范围规则；
- Meltwater 或活动规则仅在相关时读取。

输出一份简洁的 `Research Scope Confirmation`，包括：

- 研究对象和用途；
- 核心问题；
- 地区、市场、语言和时间范围；
- 企业/活动属性；
- 纳入模块；
- 排除模块；
- 用户将提供的材料；
- 计划读取的 Commands 与 Rules。

用户明确回复“确认、开始、可以”等同意指令后，才可进入正式研究。

## Stage 3：选择性研究

Scope 确认后：

1. 仅读取 `Research Scope Confirmation` 中列出的命令和规则；
2. 不默认读取整个 `commands/` 或 `rules/` 目录；
3. 不执行被排除的模块；
4. 新需求超出已确认 Scope 时，先补充确认，不自动扩展；
5. 汇总时优先使用各模块已经生成的结果，不重新加载全部 Reference。

# 四、Reference 按需路由

## 基础依赖

正式研究模块通常只需共同读取：

- `rules/02_evidence-and-source.md`；
- `rules/08_output-and-downgrade.md`。

## 条件依赖

仅在对应任务存在时读取：

| 任务条件 | 需要读取的规则 |
|---|---|
| 市场范围、跨市场或市场初筛 | `rules/03_scope-and-market.md` |
| B2B / B2C / B2B2C 分流 | `rules/04_business-type-routing.md` |
| Meltwater 舆情或活动媒体数据 | `rules/05_meltwater-gate.md` |
| 历史媒体叙事 | `rules/06_media-boundary.md` |
| 风险识别 | `rules/07_risk-standard.md` |
| 展会、活动或峰会 | `rules/09_event-research-standard.md` |

## 命令依赖映射

| 命令 | 最小 Reference 集合 |
|---|---|
| `/intake` | `rules/00` + `rules/01` |
| `/define-scope` | `rules/00` + `rules/01` + 按任务读取 `rules/03`、`rules/04`、`rules/05` 或 `rules/09` |
| `/company-core` | `rules/02` + `rules/08` |
| `/ecosystem-map` | `rules/02` + `rules/07` + `rules/08` |
| `/market-competition` | `rules/02` + `rules/03` + `rules/08` |
| `/audience-chain` | `rules/02` + `rules/04` + `rules/08` |
| `/media-history` | `rules/02` + `rules/06` + `rules/08` |
| `/meltwater-analysis` | `rules/02` + `rules/05` + `rules/08` |
| `/risk-scan` | `rules/02` + `rules/07` + `rules/08` |
| `/event-profile` | `rules/02` + `rules/09` + `rules/08` |
| `/event-participant-map` | `rules/02` + `rules/09` + `rules/08` |
| `/event-program-awards` | `rules/02` + `rules/09` + `rules/08` |
| `/event-media-history` | `rules/02` + `rules/05` + `rules/06` + `rules/09` + `rules/08` |
| `/event-attention-map` | `rules/02` + `rules/05` + `rules/09` + `rules/08` |
| `/build-dossier` | 已完成模块结果 + `rules/08`；不重新读取全部研究命令 |

# 五、上下文压缩规则

每轮结束时保留一份简短的 `Research State`：

```text
Research State
- Activation: confirmed / not confirmed
- Scope: pending / awaiting confirmation / confirmed
- Object:
- Object Type:
- Core Questions:
- Markets / Languages / Timeframe:
- Selected Commands:
- Selected Rules:
- Excluded Modules:
- Data Gates:
- Outstanding Inputs:
```

后续以该 State 作为路由依据，不重复加载已经确认的背景说明。

# 六、禁止项

- 不得因任务“看起来适合”而自行启用本 Skill；
- 不得在 Intake 阶段读取全部 Reference；
- 不得在用户确认 Scope 前开始正式研究；
- 不得为了完整性加载无关模块；
- 不得重复询问用户已提供的信息；
- 不得把普通零散 Research 自动扩展成 Research Dossier。
