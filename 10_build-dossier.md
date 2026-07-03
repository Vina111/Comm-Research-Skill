# 目标

把已完成的研究模块汇总为结构化 Research Dossier，不新增事实、不扩展 Scope。

# 输入

- 必填：已确认的 Research Scope、Research State、各已完成模块结果及 Source Log；
- 缺失时：缺失模块标记为 `Not Researched`，不得重新执行全部研究。

# 执行步骤

1. 只读取已经生成的模块结果，不重新加载所有 Commands。
2. 读取 `rules/08_output-and-downgrade.md`，统一状态标签和证据不足处理。
3. 按 Research Scope 的模块顺序汇总。
4. 合并重复事实，但保留不同来源和证据强度。
5. 将超出 Scope 的新问题放入 `Information Gaps`，不在汇总阶段展开。
6. 检查输出中是否误含策略、执行名单、KPI 或效果预测。
7. 更新最终 Research State。

# 输出

## Research Dossier

仅包含 Scope 中已纳入的章节：

- Executive Research Summary；
- Scope and Methodology；
- 已完成的企业、市场、受众、媒体、活动或风险模块；
- Information Gaps and Contradictions；
- Client Questions and Material Request List；
- Research Implications for Later Strategy Work；
- Source Log。

不适用或未研究模块按降级规则标注，不为保持篇章完整而补写泛化内容。
