# ORG_CHART (组织结构图)

## When to Use
- **适用**：公司组织结构、团队层级、AI Agent 层级、汇报关系
- **不适用**：无层级的平级协作（用 cycle 或 flowchart）

## Structure Contract
1. **单一根节点**：顶层有且仅有一个根节点
2. **树形层级**：自上而下，每个子节点归属唯一父节点
3. **连接线**：父子节点间用直线连接
4. **同级对齐**：同一层级节点水平对齐

## Structural Parameters
| 参数 | 选项 | 默认值 |
|---|---|---|
| `root` | 根节点名称 | — |
| `levels` | 层级列表 | — |
| `variant` | `top-down` / `left-right` | top-down |

## Prompt Template

```text
Create a [STYLE]-style organizational chart.

Structure:
[根节点] at top

Second layer:
- [部门 A]
- [部门 B]
- [部门 C]

[部门 B] sub-teams:
- [子团队 1]
- [子团队 2]
- [子团队 3]

Visual style:
[风格 Token 注入]

Layout constraints:
- hierarchical top-down structure
- evenly spaced nodes at each level
- clean reporting lines (no crossing)
- root node visually emphasized

Avoid:
- crossing connection lines
- orphan nodes without parent
- inconsistent node sizing at same level
```

## Failure Modes
- ❌ **多根节点**：顶层出现多个无父节点的节点
- ❌ **连线交叉**：子节点的连接线互相穿越
- ❌ **层级不齐**：同一层的节点没有对齐
