# CYCLE (循环图)

## When to Use
- **适用**：PDCA 循环、学习循环、AI 反馈循环、迭代过程、持续改进模型
- **不适用**：有明确起止点的线性流程（用 flowchart）、有中心核心的增长闭环（用 flywheel）

**与 Flywheel 的区别**：Cycle 强调"阶段轮回"，无中心目标；Flywheel 强调"自增强动能"，有中心核心。

## Structure Contract (核心约束)
1. **必须形成闭环**：首尾相连，无死胡同
2. **必须有方向箭头**：顺时针或逆时针的明确旋转方向
3. **必须有均分节点**：3–6 个阶段均匀分布在环路上
4. **每个节点有标签**：名称必须清晰可读
5. **无中心核心**：与 flywheel 的区别，cycle 中心通常为空或仅放循环名称

## Structural Parameters (可配参数)
| 参数 | 选项 | 默认值 |
|---|---|---|
| `stages` | 阶段列表（名称 + 可选描述） | — |
| `direction` | `clockwise` / `counterclockwise` | clockwise |
| `center-label` | 中心文字（可选） | 空 |
| `node-count` | 3–6 | 自动根据 stages 数 |

## Prompt Template

```text
Create a [STYLE]-style cycle diagram.

Structure:
- circular loop with arrows
- [clockwise / counterclockwise] direction

Stages:
1. [阶段名称]
2. [阶段名称]
3. [阶段名称]
4. [阶段名称]
...

[Center label: [循环名称]] (optional)

Visual style:
[风格 Token 注入]

Layout constraints:
- centered cycle
- evenly spaced stages around the circle
- clear directional arrows connecting each stage to the next
- labels positioned outside the circle for readability
- consistent node sizing

Avoid:
- broken loop (must connect back to first stage)
- missing direction arrows
- uneven stage spacing
- text overlapping with arrows
```

## Failure Modes (反模式)
- ❌ **断裂环路**：最后一个阶段没有连接回第一个阶段
- ❌ **方向缺失**：没有箭头指示旋转方向
- ❌ **间距不均**：节点分布不均匀，某些阶段挤在一起
- ❌ **文字遮挡**：标签与箭头/弧线重叠
