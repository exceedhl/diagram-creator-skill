# TIMELINE (时间轴)

## When to Use
- **适用**：历史沿革、未来规划、里程碑事件、Roadmap、有真实日期/年份的发展路径
- **不适用**：无时间刻度的阶段展示（用 flowchart）、能力爬坡（用 pyramid）

**路由铁律**：时间轴上必须有明确的时间概念（年份、月份、日期或阶段时间段）。

## Structure Contract (核心约束)
1. **必须有时间轴线**：水平或垂直的实体线段
2. **必须有里程碑节点**：圆点或标记物锚定在轴线上，圆心与线物理重合
3. **必须有时间标签**：每个节点对应明确的时间标记（年份、日期、阶段）
4. **必须有焦点节点**：至少一个节点视觉上突出（颜色、大小、标注不同）
5. **时间间隔诚实**：跨度大的节点间距应更宽，不能均分误导

## Structural Parameters (可配参数)
| 参数 | 选项 | 默认值 |
|---|---|---|
| `direction` | `horizontal` / `vertical` | horizontal |
| `events` | 事件列表（时间 + 标题 + 描述） | — |
| `active-index` | 焦点节点索引 | 最新的节点 |
| `card-layout` | `single-side` / `alternating` | single-side |
| `time-weight` | `equal` / `proportional` | equal |

## Prompt Template

```text
Create a [STYLE]-style [horizontal/vertical] timeline infographic.

Timeline events:
- [年份/日期] — [事件标题]
- [年份/日期] — [事件标题]
- [年份/日期] — [事件标题]
...

Structure:
- [left-to-right / top-to-bottom] timeline
- [evenly spaced / proportionally spaced] milestones
- [circular / diamond / flag] milestone markers
- short annotations [below / alternating above and below] each event

Highlight:
- [特定节点] as current/active milestone with distinct visual emphasis

Visual style:
[风格 Token 注入]

Layout constraints:
- milestone markers anchored precisely on the axis line
- time labels clearly readable and consistently positioned
- content cards do not overlap with each other
- visual storytelling progression from past to future

Avoid:
- misleading time intervals (unequal real gaps shown as equal spacing)
- milestone dots detached from axis line
- cluttered overlapping text
```

## Failure Modes (反模式)
- ❌ **无时间概念**：纯粹用时间轴表现"步骤1→步骤2→步骤3"，无时间标记
- ❌ **圆点跑偏**：里程碑标记未锚定在轴线上
- ❌ **误导性间隔**：2020、2021、2026 三个节点物理距离完全均等
- ❌ **视觉失衡**：某些节点内容极多导致时间轴被挤压变形
