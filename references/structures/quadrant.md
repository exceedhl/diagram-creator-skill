# QUADRANT (四象限 / 矩阵)

## When to Use
- **适用**：交叉维度评估、优先级排序、风险/影响分析、2×2 定性阵列、SWOT 分析
- **不适用**：单一维度对比（用表格/柱状图）、纯流程展示（用 flowchart）

## Structure Contract (核心约束)
1. **必须有两条坐标轴**：X 轴和 Y 轴各有明确的维度标签（如 Effort / Impact）
2. **必须有 4 个象限**：每个象限有命名标签和至少 1 项内容
3. **坐标轴方向必须一致**：左低右高、下低上高（除非刻意翻转并标注）
4. **象限逻辑不可矛盾**：右上角通常为双高（High-High），内容需匹配坐标语义

## Structural Parameters (可配参数)
| 参数 | 选项 | 默认值 |
|---|---|---|
| `axes` | 自定义 X/Y 标签 | Effort / Impact |
| `quadrant-names` | 4 个象限名称 | Quick Wins / Major Projects / Low Priority / Time Wasters |
| `items` | 每个象限内的条目列表 | — |
| `weight` | 是否不等权（某象限放大） | equal |
| `variant` | `cross`（中心十字）/ `L-shape`（L 型边界） | cross |

### Preset: SWOT
当用户意图为 SWOT 分析时，使用以下固定参数：
- `axes`：Internal/External × Positive/Negative
- `quadrant-names`：Strengths / Weaknesses / Opportunities / Threats
- `variant`：`cross`
- 每个象限内部使用 bullet list 格式

## Prompt Template

```text
Create a [STYLE]-style quadrant diagram.

Structure:
- 2×2 quadrant layout
- X-axis: [X轴标签] ([低端] → [高端])
- Y-axis: [Y轴标签] ([低端] → [高端])

Quadrants:
- Top-left: [名称]
- Top-right: [名称]
- Bottom-left: [名称]
- Bottom-right: [名称]

Items:
- [条目名] → [象限位置]
- [条目名] → [象限位置]
...

Visual style:
[风格 Token 注入]

Layout constraints:
- balanced spacing between quadrants
- centered composition
- clear separation between quadrants
- axis labels clearly readable
- items positioned within their quadrant boundaries

Avoid:
- overlapping items across quadrant boundaries
- missing axis labels
- inconsistent quadrant sizing (unless weighted)
```

### SWOT Preset Template

```text
Create a [STYLE]-style SWOT analysis diagram.

Structure:
- 2×2 grid
- Top row: Internal factors
- Bottom row: External factors
- Left column: Positive factors
- Right column: Negative factors

Quadrants:
- Top-left: Strengths
- Top-right: Weaknesses
- Bottom-left: Opportunities
- Bottom-right: Threats

Content:
Strengths:
- [条目]
- [条目]

Weaknesses:
- [条目]
- [条目]

Opportunities:
- [条目]

Threats:
- [条目]

Visual style:
[风格 Token 注入]

Layout constraints:
- equal quadrant spacing
- centered composition
- strategic planning workshop style
```

## Failure Modes (反模式)
- ❌ **坐标标签丢失**：只画了格子但没有 X/Y 轴说明
- ❌ **象限逻辑错乱**：内容与坐标轴语义矛盾（如低影响条目放在高影响象限）
- ❌ **文字重叠**：条目过多导致象限内文字互相覆盖
- ❌ **方向不明**：没有标注轴的高低方向
