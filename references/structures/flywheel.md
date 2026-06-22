# FLYWHEEL (增长飞轮)

## When to Use
- **适用**：增长飞轮、生态正向循环、自增强系统、包含相互促进关系的业务闭环
- **不适用**：无闭环的线性流程（用 flowchart）、无中心核心的简单循环（用 cycle）

**与 Cycle 的区别**：Flywheel 有中心核心（最终目标），强调"越转越快"的增强动能；Cycle 无中心，强调阶段轮回。

## Structure Contract
1. **必须形成闭环**：首尾相连，通过弧线箭头表达循环
2. **必须有中心核心**：圆心有被飞轮驱动的最终目标/价值
3. **必须有方向感**：弧线箭头指示旋转方向（通常顺时针）
4. **节点均匀分布**：3–6 个节点沿圆周均匀排列
5. **每个节点有 Icon + 文字**：图标和标签分离

## Structural Parameters
| 参数 | 选项 | 默认值 |
|---|---|---|
| `stages` | 阶段列表（名称 + 描述） | — |
| `core` | 中心核心名称 | — |
| `direction` | `clockwise` / `counterclockwise` | clockwise |
| `node-count` | 3–6 | 自动 |

## Prompt Template

```text
Create a [STYLE]-style flywheel diagram.

Flywheel stages:
1. [阶段名称]
2. [阶段名称]
3. [阶段名称]
4. [阶段名称]
5. [阶段名称]

Center core: [核心目标/价值]

Structure:
- circular momentum loop
- arrows indicating continuous [clockwise] motion
- center element representing the ultimate outcome

Visual style:
[风格 Token 注入]

Layout constraints:
- centered circular composition
- evenly spaced stages around the ring
- arrows flowing smoothly between stages
- center core visually prominent
- labels outside the ring for readability

Avoid:
- broken loop (must connect all stages)
- missing center core element
- text overlapping with arc arrows
- dead-end stages
```

## Failure Modes
- ❌ **无中心核心**：飞轮中心空白，失去"驱动目标"语义
- ❌ **断裂闭环**：某段弧线缺失，闭环被打断
- ❌ **方向感缺失**：没有箭头或箭头不可见
- ❌ **文字遮挡弧线**：标签与连接弧线重叠
