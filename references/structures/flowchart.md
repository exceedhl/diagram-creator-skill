# FLOWCHART (流程图)

## When to Use
- **适用**：用户流程、AI 工作流、审批系统、线性路线图、因果逻辑推演、决策树
- **不适用**：有明确时间刻度的场景（用 timeline）、无序平级枚举（用普通列表）

## Structure Contract (核心约束)
1. **必须有节点**：至少 2 个表示流程步骤的节点
2. **必须有连接线**：节点间用箭头连接，箭头指示方向
3. **必须有方向感**：阶段先后顺序与因果关系必须清晰
4. **焦点节点**：至少一个节点视觉突出（当前阶段 / 关键决策点）
5. **分支/循环可选**：支持条件分支（决策菱形）和反馈循环

## Structural Parameters (可配参数)
| 参数 | 选项 | 默认值 |
|---|---|---|
| `direction` | `vertical` / `horizontal` | vertical |
| `steps` | 步骤列表（名称 + 描述） | — |
| `branches` | 是否有条件分支 | false |
| `loops` | 是否有反馈循环 | false |
| `loop-target` | 循环回到哪个节点 | — |
| `variant` | `linear` / `chevron` / `swimlane` / `decision-tree` | linear |

## Prompt Template

```text
Create a [STYLE]-style workflow diagram.

Workflow steps:
1. [步骤名称]
2. [步骤名称]
3. [步骤名称]
4. [步骤名称]
...

Connections:
- linear flow from [top to bottom / left to right]
- [feedback loop from step N to step M] (if applicable)
- [decision branch at step N: condition A → step X, condition B → step Y] (if applicable)

Highlight:
- [特定节点] as the key/active step

Visual style:
[风格 Token 注入]

Layout constraints:
- evenly spaced nodes
- clear directional arrows between all connected steps
- labels inside or adjacent to each node
- no crossing arrows (minimize line intersections)
- clean process visualization

Avoid:
- ambiguous flow direction
- missing arrows between steps
- dead-end nodes without terminal indicator
- overcrowded decision branches
```

### Swimlane Variant Template

```text
Create a [STYLE]-style swimlane workflow diagram.

Lanes (roles):
- [角色 A]
- [角色 B]
- [角色 C]

Steps across lanes:
1. [步骤] — owned by [角色]
2. [步骤] — owned by [角色]
...

Handoff points:
- [步骤 X] hands off to [步骤 Y] (cross-lane)
```

## Failure Modes (反模式)
- ❌ **方向不明**：箭头缺失或双向箭头导致无法判断流程顺序
- ❌ **死胡同**：某个节点没有出口也没有终止标记
- ❌ **箭头交叉**：过多分支导致连线杂乱交叉
- ❌ **标题过长**：把长描述塞进节点内部，应该只放短标题
