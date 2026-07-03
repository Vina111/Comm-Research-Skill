# 目标

在用户已确认 Research Scope 后，只编排被选中的原子命令，输出可追溯的 Research Dossier。

# 前置门槛

必须同时满足：

- 用户已明确调用 Strategy Research Skill；
- `/intake` 已完成；
- `Research Scope Confirmation` 已输出；
- 用户已明确确认 Scope；
- `Research State` 中 Scope 为 `confirmed`。

任一条件不满足时停止，不得开始正式研究。

# 输入

- 必填：已确认的 Research Scope 与 Research State；
- 选填：客户材料、指定竞品、官方名单、Meltwater 数据、历史报道。

# 执行步骤

1. 读取 Research State 中的 `Selected Commands` 和 `Selected Rules`。
2. 只加载这些文件，不扫描或读取整个目录。
3. 按已确认顺序执行模块；不得自动加入 Scope 外模块。
4. Meltwater 或活动媒体模块未达到数据门槛时，标记为 `Not Researched`，不以公开搜索替代。
5. 新发现的问题如会扩大 Scope，记录为 `Information Gap`，等待用户确认后另行处理。
6. 执行 `/build-dossier` 时仅汇总模块结果和 Source Log，不重新读取全部命令。

# 路由原则

- 企业任务：仅执行 Scope 选中的企业模块。
- 活动任务：仅执行 Scope 选中的活动模块。
- 混合任务：分别保留企业事实、活动事实和两者交叉关系；不默认执行所有模块。

# 输出

- 数据不足：输出对应模块的 `Not Researched / Unable to Determine` 和待补材料；
- 数据充分：输出已确认 Scope 范围内的 Research Dossier；
- 始终更新 `Research State`。
