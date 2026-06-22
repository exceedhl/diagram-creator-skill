# Visual Style: Business (商务经典)

## 视觉哲学
以深沉的商务蓝传递稳定感与权威性。全场零圆角，塑造顶级商业咨询特有的严谨与硬朗体系。克制的面状分割，去边框化，纯粹依靠浅色背景区块确立物理隔断。

## Diagram Tokens

### Palette (调色板)
```
primary:        #051C2C     (深海蓝 — 主色调)
accent:         #005EB8     (亮蓝 — 强调色)
accent-light:   #009CE4     (浅蓝 — 次级强调)
chart-red:      #C93B3B     (数据红 — 仅用于关键数据)
bg-base:        #FFFFFF     (白底)
bg-surface:     #F8FAFC     (浅灰面板)
text-main:      #333333     (正文深灰)
text-light:     #666666     (辅助浅灰)
grid-line:      #E2E8F0     (网格线)
```

### Typography (字体)
```
heading:  "Helvetica Neue", Arial, sans-serif — bold 800
body:     "Helvetica Neue", Arial, sans-serif — regular 400
mono:     not used
```

### Line Style (线条)
```
stroke-width:    2px
stroke-type:     solid
arrow-style:     rounded endpoints
connector-color: #E2E8F0 (grid-line) or #333333 (text-main)
```

### Node Style (节点)
```
fill:           solid color (primary or bg-surface)
border:         none
border-radius:  0px (严禁圆角)
shadow:         none (严禁阴影)
```

### Background (背景)
```
background:     pure white #FFFFFF
texture:        none
grid:           none
```

### Decoration (装饰)
```
编号徽章:       深色直角小方块 + 白色数字 (01, 02...)
超大数字水印:   极浅淡巨大数字背景 (optional)
其他装饰:       无
```

## Prompt Injection Fragment

```text
Visual Style & Mood:
- technical enterprise architecture blueprint quality
- analytical systems diagram style
- strategic, analytical, and systems thinking mood
- enterprise transformation and operational excellence

Design Language & Palette:
- monochrome grayscale palette with restrained deep navy accent color (#051C2C & #005EB8)
- pure white empty background canvas outside the main diagram
- subtle light-gray segmentation surfaces MUST be strictly confined inside the shape boundaries
- presentation-grade iconography (minimal vector line icons / Lucide-style outline icons)
- sharp and formal geometry (absolutely no rounded cards)
- no gradients, no shadows, no texture overlays

Typography:
- Helvetica Neue style sans-serif typography
- structured consulting framework chart typography
- clean corporate labels and concise stage titles
- dark gray text instead of pure black for high readability
- no handwritten text

Diagram Rules & Structure:
- clean vector infographic and structured geometric composition
- information-first composition with clean negative space
- continuous and unbroken outer shape borders (never occluded by background color bands)
- thin geometric connector arrows and precise alignment
- minimal visual noise and subtle directional emphasis

Canvas Behavior & Composition:
- STRICTLY NO TITLE, NO MAIN HEADING, NO HERO TYPOGRAPHY
- NO PRESENTATION HEADER, NO COVER-SLIDE LAYOUT, NO FOOTER CAPTIONS
- ONLY THE DIAGRAM ITSELF, cropped tightly around the diagram
- diagram occupies the full canvas (diagram-only composition)
- all text must belong directly to nodes or annotations, NO LARGE TYPOGRAPHIC ELEMENTS OUTSIDE LABELS
```

## Forbidden Patterns (禁止)
- ❌ 页面大标题与排版修饰 (page title / hero typography / presentation headers / annotations outside nodes)
- ❌ 色块溢出与遮挡 (color bands extending outside shapes / outer borders truncated or occluded by backgrounds)
- ❌ 圆角与柔和形状 (border-radius / absolutely no rounded cards / organic imperfections)
- ❌ 阴影与特效 (box-shadow / any shadows / gradients / texture overlays)
- ❌ 手绘与涂鸦 (hand-drawn elements / sketch style / notebook aesthetic / doodles / rough marker strokes)
- ❌ 活泼插画与艺术渲染 (playful illustration / startup cartoon style / artistic rendering)
- ❌ 手写体 (handwritten typography)
- ❌ 多彩图标 (colorful icons / non-monochrome palettes)
