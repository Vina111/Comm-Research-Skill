# 目标

基于用户提供并确认口径的 Meltwater 数据和可验证到场资料，分析活动往届媒体、记者、报道表现与内容角度。

# 输入

- 必填：Meltwater 导出数据；Query；届次/起止时间；地区；语言；数据源；去重口径；Sentiment 口径；分析目标。
- 到场分析必填：组织方媒体认证/注册名单、用户提供的到场记录或其他可靠到场证据。
- 选填：官方 Press Room、媒体合作伙伴名单、采访日程、现场照片或签到记录。
- 缺失时：按 `rules/05_meltwater-gate.md` 停止相关分析；只有 Meltwater 时只能输出“报道媒体/作者”，不能写“到场媒体/记者”。

# 执行步骤

1. 验证 Meltwater 数据门槛及活动名称、别名、标签和届次窗口。
2. 检查字段、重复、新闻稿转载、异常值、作者缺失和跨届 Query 可比性。
3. 分开整理：已验证到场媒体/记者、报道媒体/作者、官方媒体伙伴。
4. 按届次、时间、地区、语言、媒体类别和内容形式分析报道。
5. 按活动角度分类法编码报道主题，分析数量、占比和代表性内容。
6. 识别峰值时段及其与 Keynote、发布会、奖项或争议事件的关系。
7. 写明样本限制和无法证明的事项。

# 输出

## Event Media Method Note
## Data Quality & Comparability Check

## Verified Attendance Evidence
| Edition | Media | Journalist | Attendance Evidence | Evidence Type | Confidence | Notes |

## Coverage Media & Authors
| Edition | Media | Author | Market | Language | Media Category | Unique Coverage | Content Type | Evidence/Link | Notes |

## Coverage Angle Analysis
| Angle | Unique Coverage | Share | Representative Stories | Main Entities | Editions | Notes |

## Time, Market and Source Findings
## Peak Event Findings
## Limitations
