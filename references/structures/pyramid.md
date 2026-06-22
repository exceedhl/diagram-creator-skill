# PYRAMID (金字塔)

## When to Use
- **适用**：层叠状态、能力模型、需求层次、战略层级、成熟度模型、倒三角优先级
- **不适用**：平级要素堆叠（用列表/卡片）、线性递进（用 flowchart）

## Structure Contract (核心约束)
1. **必须呈三角形**：最顶层为物理尖角（Apex），不能是平顶
2. **必须层层递增**：每层宽度从上到下严格递增，形成等差数列
3. **必须有层级标签**：每层有明确的名称和简短描述
4. **文本外置**：层级色块内仅放极短标签，详细说明放在侧面或下方
5. **层级关系不可倒置**：基础层一定在最宽处

## Structural Parameters (可配参数)
| 参数 | 选项 | 默认值 |
|---|---|---|
| `layers` | 3–7 层 | 5 |
| `direction` | `upward`（正金字塔）/ `inverted`（倒金字塔） | upward |
| `levels` | 层级列表（名称 + 描述/要素） | — |
| `annotation-position` | `right-side` / `both-sides` / `inline` | right-side |

## Prompt Template

```text
Create a [STYLE]-style pyramid infographic.

Structure:
- [N]-level pyramid layout
- levels should stack vertically from bottom to top
- each level must have clear labels and short descriptions

Levels from bottom to top:
1. [底层名称]
   - [要素 a], [要素 b], [要素 c]

2. [第二层名称]
   - [要素 a], [要素 b]

3. [第三层名称]
   - [要素 a], [要素 b]

4. [第四层名称]
   - [要素 a]

5. [顶层名称]
   - [要素 a], [要素 b]

Visual style:
[风格 Token 注入]

Layout constraints:
- centered pyramid with perfect straight diagonal edges
- each layer proportional and clearly separated
- labels aligned horizontally
- descriptions positioned beside or below the pyramid
- color gradient from dark (top/accent) to light (bottom)

Avoid:
- flat top instead of apex point
- wavy or jagged edges (must be perfect straight diagonals)
- text crammed inside narrow top layers
- inconsistent layer width progression
```

## Failure Modes (反模式)
- ❌ **平顶**：顶层画成了矩形而不是三角尖角
- ❌ **斜线不直**：各层宽度随意设定，导致侧面边缘成锯齿/折线
- ❌ **文字塞窄层**：把长文本强行写在顶层色块内部导致被裁切
- ❌ **说明错位**：右侧的释义文字与对应的金字塔层不在同一水平线
