# Visual Style: Sketch (手绘白板)

## 视觉哲学
通过有机的不规则边缘、硬阴影、手写字体和纸质纹理，营造真实、随性和充满人情味的视觉体验。拒绝直线，刻意打破几何完美感。每一个形状都带有"白板马克笔"的质感——imperfect、energetic、human。

## Diagram Tokens

### Palette (调色板)
```
primary:        #2d2d2d     (墨黑 — 主线条/文字)
accent:         #ff4d4d     (马克笔红 — 强调)
accent-light:   #fff9c4     (便利贴黄)
bg-base:        #fdfbf7     (纸张白)
bg-surface:     #ffffff     (卡片白)
text-main:      #2d2d2d     (正文黑)
text-light:     #e5e0d8     (网格浅灰)
grid-line:      #2d2d2d     (墨线)
```

### Typography (字体)
```
heading:  "Kalam", "Yozai Medium", cursive — bold 700 (马克笔手写)
body:     "Patrick Hand", "Yozai Medium", cursive — regular 400 (圆珠笔手写)
mono:     not used
```

### Line Style (线条)
```
stroke-width:    2px (粗笔触)
stroke-type:     hand-drawn / slightly irregular
arrow-style:     hand-drawn arrows (不规则箭头)
connector-color: #2d2d2d (墨黑)
```

### Node Style (节点)
```
fill:           solid (white or accent-light for sticky notes)
border:         2px solid #2d2d2d (粗黑边)
border-radius:  wobbly / irregular (255px 15px 225px 15px / 15px 225px 15px 255px)
shadow:         4px 4px 0px 0px #2d2d2d (硬偏移阴影，无模糊)
```

### Background (背景)
```
background:     warm paper #fdfbf7
texture:        dot grid pattern (圆点网格纸)
grid:           radial-gradient(#e5e0d8 1px, transparent 1px) / 24px 24px
```

### Decoration (装饰)
```
胶带 (tape):      半透明灰色胶带效果贴在卡片顶部
图钉 (tack):      红色圆形图钉
手绘下划线:        不规则波浪线
手绘圈:            粗糙圆圈围绕重点词
微旋转:            ±1~2deg 随机倾斜
语音气泡:          comic-style speech bubbles (optional)
```

## Prompt Injection Fragment

```text
Visual Style & Mood:
- authentic sketchnote / whiteboard workshop aesthetic
- human-centered technical schematic with notebook brainstorming illustration
- tactile paper feeling and organized chaos aesthetic
- playful but structured information design
- thoughtful, collaborative, and educational visual systems-thinking
- workshop brainstorming energy that is emotionally warm and approachable

Paper & Background:
- warm paper-white background (#fdfbf7) with subtle notebook dot-grid texture
- realistic paper grain and soft analog print feeling
- no digital glossy surface

Line & Shape Treatment:
- hand-drawn ink outlines and slightly wobbly pen strokes
- thick black marker contour lines with irregular sketch borders
- imperfect geometry with human inconsistency
- hard offset shadows only (4px 4px solid black), absolutely no blur shadows
- no clean vector precision

Typography & Color:
- handwritten marker-style headings and ballpoint-style body text
- varied handwritten scale hierarchy with imperfect text rhythm
- monochrome grayscale base (deep charcoal #2d2d2d)
- single accent color: sketch red (#ff4d4d) and sticky-note yellow (#fff9c4) for emphasis blocks
- minimal restrained palette with no gradients

Decorative Elements & Layout Personality:
- hand-drawn arrows, rough underlines, circled annotations
- tape decorations, pushpin accents, and sticky-note callouts
- scribbled emphasis marks and rough pencil shading texture
- slight random rotation on decorative cards (±1-2 degrees)
- intentionally imperfect spacing with layered workshop-board feeling
- casual visual rhythm and breathing whitespace

Canvas Behavior & Composition:
- STRICTLY NO TITLE, NO MAIN HEADING, NO HERO TYPOGRAPHY
- NO PRESENTATION HEADER, NO COVER-SLIDE LAYOUT, NO FOOTER CAPTIONS
- ONLY THE DIAGRAM ITSELF, cropped tightly around the diagram
- diagram occupies the full canvas (diagram-only composition)
- all text must belong directly to nodes or annotations, NO LARGE TYPOGRAPHIC ELEMENTS OUTSIDE LABELS
```

## Forbidden Patterns (禁止)
- ❌ 页面大标题与排版修饰 (page title / hero typography / presentation headers / annotations outside nodes)
- ❌ 模糊阴影与特效 (`box-shadow` blur-radius / soft UI shadows / glossy effects / 3D rendering / glassmorphism)
- ❌ 完美的几何与对齐 (perfect geometric alignment / clean vector precision / standard rounded rectangles)
- ❌ 企业无衬线字体 (Helvetica / Arial / Inter / corporate typography)
- ❌ 精致的企业/仪表盘风格 (polished corporate infographic style / modern SaaS dashboard aesthetic / clean minimal startup branding)
- ❌ 矢量插画与渐变色 (flat vector illustration / gradients)
- ❌ 过于夸张的漫画风 (overly decorative comic style)
