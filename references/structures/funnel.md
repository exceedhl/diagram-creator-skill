# FUNNEL (漏斗图)

## When to Use
- **适用**：销售转化漏斗、用户行为漏斗、线索筛选、技术降噪等逐渐收敛的过程
- **不适用**：无明确筛选/收缩关系的一般性步骤（用 flowchart）

## Structure Contract (核心约束)
1. **必须呈收敛形态**：越往下层宽度/体积越小，视觉上明显收窄
2. **必须有阶段标签**：每层有明确的名称
3. **必须有收敛指标**：每层附带数量、百分比或转化率等指标
4. **方向不可逆**：转化方向由大到小，不能出现反向扩大
5. **底层强调**：最终转化层使用高对比度颜色标识

## Structural Parameters (可配参数)
| 参数 | 选项 | 默认值 |
|---|---|---|
| `stages` | 阶段列表（名称 + 数量/比例） | — |
| `direction` | `vertical` / `horizontal` | vertical |
| `variant` | `smooth`（连续梯形）/ `stepped`（阶梯方块）| smooth |
| `show-metrics` | 是否显示转化率数据 | true |

## Prompt Template

```text
Create a [STYLE]-style funnel diagram.

Stages (from widest to narrowest):
1. [阶段名称] — [数量/比例]
2. [阶段名称] — [数量/比例]
3. [阶段名称] — [数量/比例]
4. [阶段名称] — [数量/比例]
5. [阶段名称] — [数量/比例]

Structure:
- [vertical / horizontal] funnel
- narrowing [downward / rightward]
- each stage labeled with name and conversion metrics
- final stage highlighted as the key outcome

Visual style:
[风格 Token 注入]

Layout constraints:
- centered funnel
- proportional stage sizes reflecting actual conversion ratios
- clean whitespace between stages
- metrics clearly readable alongside each stage
- color progression from light (top) to dark/accent (bottom)

Avoid:
- stages without conversion data (just step names)
- bottom stage wider than top (inverts funnel logic)
- equal-width stages (no visual convergence)
- excessive decoration between stages
```

## Failure Modes (反模式)
- ❌ **无收敛指标**：没有转化率或数量，退化为普通阶段图
- ❌ **无收缩感**：所有层宽度相同，看不出漏斗形态
- ❌ **底层过大**：最终转化层比上层还宽，打破逻辑
- ❌ **指标缺失**：只有阶段名，没有具体数字或百分比
