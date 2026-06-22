# ARCHITECTURE (系统架构图)

## When to Use
- **适用**：软件平台架构、三层/多层体系结构、SaaS 系统、微服务、AI Agent 架构、生态图
- **不适用**：简单流程步骤（用 flowchart）、数据对比（用图表）

## Structure Contract (核心约束)
1. **必须分层或分区**：通过 Layer（水平分层）或 Pillar（垂直支柱）组织模块
2. **必须有模块卡片**：每个独立系统/服务用标注的盒子表示
3. **必须有连接关系**：模块间用箭头或连线表示依赖、数据流、调用关系
4. **必须有包围盒**：同层模块用可见的边界框圈定，体现层级包含关系
5. **不可有孤立模块**：每个模块至少与另一个模块有连接

## Structural Parameters (可配参数)
| 参数 | 选项 | 默认值 |
|---|---|---|
| `variant` | `3-tier` / `pillars` / `hub-spoke` | 3-tier |
| `layers` | 层列表（名称 + 包含的模块） | — |
| `connections` | 连接关系列表 | — |
| `direction` | `top-down` / `bottom-up` | top-down |

## Prompt Template

```text
Create a [STYLE]-style system architecture diagram.

Structure:
Use a [layered / pillar / hub-spoke] architecture layout.

Layer 1 — [层名称]:
- [模块 A]
- [模块 B]

Layer 2 — [层名称]:
- [模块 C]
- [模块 D]
- [模块 E]

Layer 3 — [层名称]:
- [模块 F]
- [模块 G]

Connections:
- [模块/层 A] connects to [模块/层 B] via [协议/方式]
- [模块 C] routes to [模块 D]
- [模块 E] reads from [模块 F]

Visual style:
[风格 Token 注入]

Layout constraints:
- clean hierarchy with clear layer boundaries
- evenly spaced modules within each layer
- arrows clearly labeled with connection type
- each layer visually enclosed in a bounding box
- no orphan modules without connections

Avoid:
- tangled crossing connection lines
- modules floating outside any layer
- inconsistent module sizing within same layer
- ambiguous data flow direction
```

## Failure Modes (反模式)
- ❌ **孤立模块**：某个模块与其他模块没有任何连接关系
- ❌ **层级不清**：同一层内混入不同抽象级别的模块
- ❌ **连线混乱**：箭头交叉缠绕，无法追踪数据流向
- ❌ **包围盒缺失**：层与层之间没有视觉边界，无法区分归属
