# Visual Style: Editorial Luxury (编辑奢华)

## 视觉哲学
暖调米白底色配合极淡噪点纹理，营造高端印刷品的物理存在感。巨大衬线体标题搭配纤细无衬线正文，经典编辑式排版反差。深棕/金铜作唯一 Accent 色。杂志版面般的呼吸感和叙事仪式感。

## Diagram Tokens

### Palette (调色板)
```
primary:        #1A1A1A     (近黑 — 标题)
accent:         #8B6914     (深金铜 — 唯一强调色)
accent-light:   #C9A84C     (浅金 — 次级)
bg-base:        #FDFBF7     (暖调米白)
bg-surface:     #F7F4EE     (象牙面板)
text-main:      #2D2D2D     (正文深灰)
text-light:     #6B6B6B     (辅助灰)
text-faint:     #A8A8A0     (极淡注释灰)
grid-line:      #D4D0C8     (暖灰分割线)
```

### Typography (字体)
```
heading:  "Playfair Display", Georgia, serif — weight 400-600, italic for emphasis
body:     "Inter", sans-serif — weight 300-400
mono:     "JetBrains Mono" — weight 400 (仅用于注释/元数据)
mixed-emphasis: heading italic × body sans-serif 混排
```

### Line Style (线条)
```
stroke-width:    1px (纤细)
stroke-type:     solid
arrow-style:     sharp endpoints (尖锐)
connector-color: #6B6B6B or #D4D0C8
```

### Node Style (节点)
```
fill:           solid (bg-base or bg-surface)
border:         none (去边框化)
border-radius:  0px
shadow:         none
```

### Background (背景)
```
background:     warm ivory #FDFBF7
texture:        paper grain noise (subtle sepia-tinted SVG noise)
grid:           none
```

### Decoration (装饰)
```
Eyebrow 标签:   UPPERCASE · 11px · 0.22em letter-spacing · accent 色
Corner Marks:   图片四角 1px accent 色 L 形标记 (22×22px)
Section Divider: 1px solid grid-line + 两端 label
Image Annotations: monospace 10px 元数据 (Nº 03, MMXXVI)
编号格式:        罗马数字 (I. II. III.) 或 Nº 01
```

## Prompt Injection Fragment

```text
Visual Direction & Design Philosophy:
- analytical enterprise architecture blueprint
- structured infographic panel with luxury minimalist storytelling
- cinematic white-space composition
- elegant editorial restraint and quiet luxury aesthetic
- intellectual, strategic, and emotionally refined enterprise storytelling

Color Palette & Typography:
- warm ivory paper background (#FDFBF7)
- deep charcoal typography (#1A1A1A) with restrained bronze accent (#8B6914)
- elegant serif font ONLY for primary diagram nodes (Playfair Display / PP Editorial)
- thin sans-serif body typography (Inter)
- elegant italic emphasis
- precise structural spacing rhythm

Layout & Diagram Style:
- asymmetrical editorial composition with generous breathing whitespace
- invisible grid alignment and centered conceptual hierarchy
- information-first composition
- thin elegant connector lines and minimal geometric nodes
- understated motion cues and premium infographic geometry

Surface Treatment & Editorial Elements:
- soft paper-tone background with subtle print texture
- no borders, no shadows, no gradients, no glossy UI effects
- subtle divider rules and quiet annotation text
- monospace annotations (Nº numbering, roman numerals)
- timeless business elegance and high-end print publication feel

Canvas Behavior & Composition:
- STRICTLY NO TITLE, NO MAIN HEADING, NO HERO TYPOGRAPHY
- NO PRESENTATION HEADER, NO COVER-SLIDE LAYOUT, NO FOOTER CAPTIONS
- ONLY THE DIAGRAM ITSELF, cropped tightly around the diagram
- diagram occupies the full canvas (diagram-only composition)
- all text must belong directly to nodes or annotations, NO LARGE TYPOGRAPHIC ELEMENTS OUTSIDE LABELS
```

## Forbidden Patterns (禁止)
- ❌ 页面大标题与排版修饰 (page title / hero typography / presentation headers / annotations outside nodes)
- ❌ 粗边框与重型容器 (thick borders / heavy containers)
- ❌ 霓虹色与渐变 (bright tech gradients / neon colors / rainbow colors)
- ❌ 拟物与光泽特效 (glossy UI effects / excessive UI chrome / 3D effects)
- ❌ 阴影 (`box-shadow` / any shadows)
- ❌ 仪表盘式堆砌与繁乱 (dashboard-style clutter / hard visual noise)
- ❌ 活泼的插画与手绘 (startup illustrations / playful SaaS visuals / sketch style / cartoon icons)
