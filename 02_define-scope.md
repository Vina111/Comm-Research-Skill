# 目标

把完成的 Intake 转化为一份供用户确认的 Research Scope，并明确本次只需读取哪些 Reference。

# 输入

- 必填：完整的 `Research Intake Status`；
- 选填：交付格式、截止时间、资料限制；
- 缺失时：返回 `/intake`。

# 执行步骤

1. 写明研究对象、用途和核心问题。
2. 锁定企业、业务线、活动名称、届次、市场、语言和时间边界。
3. 区分活动举办地、参与者来源地、媒体市场和报道语言。
4. 选择必要研究模块，明确排除模块。
5. 根据 `rules/00_activation-and-context-efficiency.md` 生成最小 Reference 读取清单。
6. 写明已提供资料、待补资料、Meltwater 数据门槛和方法限制。
7. 将 Scope 状态设为 `Awaiting User Confirmation`。
8. 等待用户明确回复“确认、开始、可以”等同意指令；确认前不得开展正式研究。

# 输出

## Research Scope Confirmation

- 研究对象与对象类型：
- 使用场景：
- 核心研究问题：
- 企业类型与受众结构（如适用）：
- 活动类型、届次与比较年份（如适用）：
- 国家、地区、市场与语言：
- 时间范围：
- 纳入模块：
- 排除模块：
- 已有资料：
- 待补资料：
- Meltwater 数据门槛（如适用）：
- 计划调用的 Commands：
- 计划读取的 Rules：
- 明确不包含事项：
- Scope Status：Awaiting User Confirmation

结尾只询问用户是否确认该 Scope，不开始研究。

## Research State

更新 Selected Commands、Selected Rules、Excluded Modules、Data Gates 和 Scope 状态。
