---
name: strategy-research
aliases:
  - pr-pre-strategy-research
description: 仅在用户明确要求调用“Strategy Research” Skill 时启用。用于在公关方案制定前，对企业、品牌、展会、活动、峰会及其业务生态、参与者、市场、受众、历史媒体表现、舆情数据与风险进行结构化调研。Activate only when the user explicitly invokes the "Strategy Research" skill; structured pre-strategy PR research on companies, brands, trade shows, events and summits.
language: zh-CN
version: 5.1
---

# 技能目标

本 Skill 用于完成**公关方案前置研究**，查清研究对象的事实背景、业务和参与者结构、市场环境、历史公开叙事、媒体关注与风险，为后续方案提供可靠底稿。

研究对象可以是：

- 企业、品牌、业务线或产品；
- 展会、会议、峰会、论坛或大型行业活动；
- 企业与特定活动的组合。

# 严格触发条件

只有用户明确要求使用 **Strategy Research** Skill 时才启用，例如：

> “需要你帮我用 Strategy Research 的 skill 帮我做调研。”
> “Use the Strategy Research skill to research ___.”

普通的单点调研、资料搜索、竞品补充、媒体查询或展会信息查询，不自动调用本 Skill。

完整启用与按需读取规则见：

- `rules/00_activation-and-context-efficiency.md`

# 启用顺序

1. **Intake**：先确认研究需求，只提阻塞问题；
2. **Scope Confirmation**：向用户复述范围、模块和资料需求；
3. **User Approval**：用户确认后才开始研究；
4. **Selective Loading**：只读取本次 Scope 对应的 Commands 和 Rules；
5. **Dossier Assembly**：只汇总已完成模块，不补造未研究内容。

# 核心命令

## 入口与总控

- `/intake`：确认需求与资料缺口；
- `/define-scope`：生成待用户确认的 Research Scope；
- `/auto-research`：仅在 Scope 已确认后，编排被选中的模块；
- `/build-dossier`：汇总已完成模块。

## 企业研究

- `/company-core`：企业历史、治理、商业模式、产品与能力；
- `/ecosystem-map`：上下游、供应链、合作伙伴与利益相关方；
- `/market-competition`：地区市场、竞品与替代方案；
- `/audience-chain`：客户、用户、采购与影响决策链；
- `/media-history`：历史媒体与公开叙事；
- `/meltwater-analysis`：基于用户提供并确认口径的数据开展舆情分析；
- `/risk-scan`：生成 Risk Register。

## 展会、活动与峰会研究

- `/event-profile`：活动背景、组织方、历史、定位、规模与演变；
- `/event-participant-map`：参展商、赞助商、演讲者和合作伙伴构成；
- `/event-program-awards`：议程、议题、发布会、品牌发布和奖项；
- `/event-media-history`：基于 Meltwater 和到场证据分析往届媒体、记者、报道与内容角度；
- `/event-attention-map`：基于确认口径的数据分析高关注品牌、主要议题和关注驱动因素。

# 全局边界

- 不默认国家、地区、语言、时间范围、企业属性或研究目的；
- Meltwater 分析前必须向用户索取数据和检索口径；
- 媒体研究只分析历史，建议仅到媒体类别与代表性示例；
- Meltwater 报道不能单独证明记者实际到场；
- 不输出完整传播策略、Campaign 定案、具体执行媒体名单、预算、KPI、AVE、ROI、Outcome 或效果预测；
- 所有事实须有来源，证据不足时输出“无法判断 + 需补材料”；
- 只读取本次 Scope 需要的 Reference，不默认加载整个目录。
