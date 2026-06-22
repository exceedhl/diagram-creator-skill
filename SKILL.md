---
name: diagram
description: "Generate high-quality diagrams using AI image generation. Supports 9 structure types (quadrant, timeline, flowchart, architecture, pyramid, cycle, funnel, org chart, flywheel) × 3 visual styles (business, editorial luxury, sketch). Uses structured prompts with explicit structure, style, and layout constraints to produce professional infographic-quality output."
---

# Diagram Skill — AI 图表生成

通过结构化 Prompt 驱动 AI 图像生成，产出专业级信息图表。核心理念：**Structure x Style x Canvas x Prompt** 四层分离。

## 核心工作流

### Step 1: 识别结构类型

根据用户意图匹配结构类型。**路由表**：

| 用户意图关键词 | 结构类型 | 契约文件 |
|---|---|---|
| 优先级、分析矩阵、对比、SWOT | `quadrant` | [quadrant.md](references/structures/quadrant.md) |
| 时间、里程碑、roadmap、发展历程 | `timeline` | [timeline.md](references/structures/timeline.md) |
| 流程、步骤、workflow、审批 | `flowchart` | [flowchart.md](references/structures/flowchart.md) |
| 架构、系统、分层、微服务 | `architecture` | [architecture.md](references/structures/architecture.md) |
| 层级、模型、基础、金字塔 | `pyramid` | [pyramid.md](references/structures/pyramid.md) |
| 循环、迭代、loop、PDCA | `cycle` | [cycle.md](references/structures/cycle.md) |
| 转化、漏斗、pipeline、筛选 | `funnel` | [funnel.md](references/structures/funnel.md) |
| 组织、团队、汇报、hierarchy | `org_chart` | [org_chart.md](references/structures/org_chart.md) |
| 飞轮、增长、闭环、自增强 | `flywheel` | [flywheel.md](references/structures/flywheel.md) |

### Step 2: 加载结构契约

阅读对应的 `references/structures/{type}.md`，提取：
- **核心约束 (Structure Contract)**：必须遵守的拓扑规则
- **可配参数 (Structural Parameters)**：节点数、方向、连接方式等
- **Prompt 骨架 (Prompt Template)**：该结构的标准 Prompt 填充模板

### Step 3: 选择视觉风格

根据用户偏好或场景选择风格 Token 文件：

| 风格 | 适用场景 | 文件 |
|---|---|---|
| **Business** | 商业报告、咨询演示、正式汇报 | [business.md](references/styles/business.md) |
| **Editorial Luxury** | 品牌故事、高端报告、杂志风格 | [editorial_luxury.md](references/styles/editorial_luxury.md) |
| **Sketch** | 头脑风暴、白板讨论、创意沟通 | [sketch.md](references/styles/sketch.md) |

若用户未指定，默认使用 **Sketch**。

### Step 3.5: 选择颜色模式 (Color Mode)

每种视觉风格均支持 **light** 和 **dark** 两种颜色模式，形成 **Style × Mode** 矩阵：

| | Light (默认) | Dark |
|---|---|---|
| **Business** | 白底深蓝 | 墨黑底亮蓝 |
| **Editorial Luxury** | 暖调米白底 | 深暖调暗底 |
| **Sketch** | 纸白底墨黑线 | 黑板底粉笔线 |

- **`color-mode: light`** (默认)：使用风格文件中定义的原始 Palette 和 Prompt Injection Fragment。
- **`color-mode: dark`**：在原始风格基础上**叠加** [dark_mode.md](references/styles/dark_mode.md) 中定义的变换规则——反转背景/文字明暗，保持风格结构特征（线条粗细、节点形状、装饰元素、字体）不变。

**Dark mode 触发条件**：
- 用户明确指定 "dark" / "深色" / "暗色"
- 以嵌入模式工作且调用方指定了深色主题容器（如 slide-creator 的 Executive Dark / Ethereal Glass 风格）

**Prompt 组装方式**：读取风格文件的 Prompt Injection Fragment 后，将 `dark_mode.md` 中的"通用 Dark Mode Addendum"和对应风格的"专属覆写"追加到 `Visual style` 段末尾。

### Step 4: 组装 Prompt（四段式协议）

**必须严格遵守以下骨架**：

```text
Create a [STYLE]-style [STRUCTURE TYPE] diagram.

Structure:
- [从结构契约填充：拓扑、节点、层级、连接关系]
- [用户提供的具体内容数据]

Visual style:
- [从风格 Token 的 Prompt Injection Fragment 填充：线条、字体、颜色、背景、装饰]
- [至少 5 个具体的视觉描述词]

Canvas Behavior & Composition:
- STRICTLY NO TITLE, NO MAIN HEADING, NO HERO TYPOGRAPHY
- NO PRESENTATION HEADER, NO COVER-SLIDE LAYOUT, NO FOOTER CAPTIONS
- ONLY THE DIAGRAM ITSELF, cropped tightly around the diagram
- diagram occupies the full canvas (diagram-only composition)
- all text must belong directly to nodes or annotations, NO LARGE TYPOGRAPHIC ELEMENTS OUTSIDE LABELS

Layout constraints:
- [通用约束：清晰层级、无歧义、标注连接]
- [结构特定约束：从结构契约的 Failure Modes 反推]

Avoid:
- [从风格 Token 的 forbidden-patterns 填充]
- page title / hero typography / presentation headers
- overly polished 3D rendering
- cluttered composition
- ambiguous relationships
```

> **Canvas Behavior 段是强制段（MANDATORY）**：此段在所有风格的 `Prompt Injection Fragment` 中均有定义，但为防止因跳过 Step 3 而丢失，此处在骨架中**硬编码为默认值**。如果风格 Token 中有更具体的 Canvas Behavior 描述，应以风格 Token 为准覆盖。

**Prompt 组装规则**：
1. `Structure` 段必须包含**具体的业务数据**（节点名称、层级内容、时间点等），不能只有空壳结构
2. `Visual style` 段必须包含**至少 5 个具体的视觉描述词**，不能只写风格名
3. `Canvas Behavior` 段**必须存在**——这是防止生图模型输出"完整 PPT 页面"而非"纯净图表组件"的核心约束
4. `Layout constraints` 段必须包含**至少 3 条约束**
5. `Avoid` 段必须包含**至少 3 条禁止项**，且**必须包含** `page title / hero typography / presentation headers` 这一条

### Step 5: 生成输出

**主输出：AI 图像生成**

1. **展示 Prompt**：在调用图像生成工具之前或同时，**必须**使用 Markdown 代码块向用户展示你组装好的完整 Prompt。
2. **生成图片**：使用 `generate_image` 工具，将该 Prompt 传入以生成图片。

输出参数建议：
- **尺寸**：默认 landscape 4:3（适合演示）；可选 1:1（社交媒体）、16:9（宽屏）
- **分辨率**：高分辨率 infographic 风格

**Fallback：Mermaid 代码**

当 AI 图像生成不可用或用户明确要求可编辑格式时，输出 Mermaid 代码：

```mermaid
%% 仅用于 quadrant / flowchart / timeline / cycle / org_chart
%% architecture / pyramid / funnel / flywheel 不建议用 Mermaid（表现力不足）
```

> **Mermaid 限制**：Mermaid 对以下结构支持较弱，优先使用 AI 图像：
> - ❌ Pyramid（无原生支持）
> - ❌ Funnel（无原生支持）
> - ❌ Flywheel（弧线箭头无法表达）
> - ❌ Architecture（分层包围盒不自然）
> - ⚠️ SWOT（需要用 quadrantChart 变通）

---

## Prompt 范例速查

详见 [gallery.md](examples/gallery.md)，包含 9 种结构 × 3 种风格的代表性示例。

---

## 万能 Prompt 骨架

当不确定结构类型时，使用以下万能骨架：

```text
Create a [STYLE]-style [DIAGRAM TYPE].

Structure:
[明确描述拓扑关系]

Visual style:
[5+ 个视觉描述词]

Canvas Behavior & Composition:
- STRICTLY NO TITLE, NO MAIN HEADING, NO HERO TYPOGRAPHY
- NO PRESENTATION HEADER, NO COVER-SLIDE LAYOUT, NO FOOTER CAPTIONS
- ONLY THE DIAGRAM ITSELF, cropped tightly around the diagram
- diagram occupies the full canvas (diagram-only composition)
- all text must belong directly to nodes or annotations, NO LARGE TYPOGRAPHIC ELEMENTS OUTSIDE LABELS

Layout constraints:
- clear hierarchy
- no ambiguity
- labeled connections
- balanced composition
- centered layout

Avoid:
- page title / hero typography / presentation headers
- overly polished UI
- 3D rendering
- excessive colors
- cluttered composition
```

---

## 嵌入模式 (Embedding Mode)

当 diagram 作为其他系统（如 `slide-creator`、PPT 生成器、文档排版系统）的**子组件**嵌入时，必须额外注意以下约束：

| 维度 | 独立模式（默认） | 嵌入模式 |
|:---|:---|:---|
| **Canvas Behavior** | 已强制无标题 | 同左，**双重确认**——外部容器已有标题，图表内绝不能重复 |
| **背景** | 由风格 Token 决定 | 优先使用 `pure white` 或 `transparent`，以便与外部容器融合 |
| **宽高比** | 默认 4:3 | **必须使用调用方指定的 `target-size` 隐含的宽高比**，禁止自行假设 |
| **裁切** | 适度留白 | `cropped tightly around the diagram`，减少无用边距 |

**嵌入模式触发条件**：当调用方明确说明图表将嵌入到 HTML/PPT/其他排版系统中时，自动启用。

### 嵌入调用契约 (Embedding Call Contract)

调用方在请求 diagram 生图时，应提供以下参数。**`target-size` 为唯一强制参数**。如 `target-size` 未提供，diagram-creator 应主动询问。

| 参数 | 必须 | 格式 | 说明 |
|:---|:---|:---|:---|
| `target-size` | 🔴 | `{W}x{H}` (如 `1536x1024`) | 目标像素尺寸。调用方根据容器的有效像素推算得出 |

**diagram-creator 收到后的处理**：
1. 从 `target-size` 推导 AR（如 `1536x1024` → `3:2`），注入 Prompt 的 `--ar` 参数
2. 将 `target-size` 直接传递给生图工具的尺寸参数（如 `--size 1536x1024`）

> **尺寸即唯一真理**：Diagram 内容（坐标轴、标签、节点边框）不允许被裁切或拉伸，因此 `object-fit: cover`（裁切）和 `object-fit: fill`（变形）均不可用；而 `object-fit: contain` 虽然安全但会产生死区留白。**唯一正解是生图尺寸的 AR 与容器 AR 精确匹配**——此时不需要任何 object-fit 属性，图片自然填满容器。调用方有责任在请求前精确推算容器的有效像素尺寸（需考虑 CSS Grid gap 对行/列高的侵蚀），并将推算结果作为 `target-size` 传入。
>
> **职责边界**：容器像素推算、栅格跨度计算等均属**调用方职责**。diagram-creator 不感知也不依赖任何外部排版系统的布局实现细节。

---

## 常见问题

### Q: 生成的图带了大标题/看起来像一整页 PPT 怎么办？
A: 检查 Prompt 中是否包含 `Canvas Behavior & Composition` 段。这是防止标题污染的核心机制。如果使用万能骨架，该段已内置。如果自行组装 Prompt，必须手动加入。同时确保 `Avoid` 段包含 `page title / hero typography / presentation headers`。

### Q: 生成的图不够精确怎么办？
A: 在 `Structure` 段增加更多约束，特别是节点数量、连接方向、层级关系。结构描述越精确，输出越稳定。

### Q: 风格不像怎么办？
A: 在 `Visual style` 段增加更多具体的视觉描述词（参考风格 Token 文件的 Prompt Injection Fragment），并在 `Avoid` 段明确排除不想要的元素。

### Q: 中英文内容都支持吗？
A: 支持。在 `Structure` 段使用用户需要的语言填充内容即可。AI 图像生成对中英文内容均有良好支持。
