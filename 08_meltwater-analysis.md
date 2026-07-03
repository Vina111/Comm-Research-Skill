# 目标

基于用户提供并确认口径的 Meltwater 数据，完成可复核的舆情分析。

# 输入

- 必填：Meltwater 导出数据；Query；起止时间；地区；语言；数据源；去重口径；Sentiment 口径；分析目标。
- 选填：竞品对比组、事件节点、客户标签规则。
- 缺失时：停止分析，输出所缺字段，不自行设置条件或用公开搜索替代。

# 执行步骤

1. 按 `rules/05_meltwater-gate.md` 验证数据门槛。
2. 检查字段、时间、重复、异常值和缺失值。
3. 区分新闻稿转载、独立报道、社交内容和其他来源。
4. 按已确认口径分析时间趋势、主题、地区、语言、来源和情绪。
5. 标记重大峰值并用已知事件解释；无法解释时明确写出。
6. 输出方法、限制与不可推断范围。

# 输出

## Meltwater Method Note
## Data Quality Check
## Volume & Time Trend
## Topic Analysis
## Market / Language / Source Analysis
## Sentiment Analysis
## Peak Event Analysis
## Comparative Findings（如适用）
## Limitations
