# Visual Style: Thoughtful Sketch (沉思手绘风)

## 视觉哲学
强调“视觉思考 (Visual Thinking)”和概念推演的白板/草图风格。与随性活泼的传统手绘不同，这种风格更偏向严肃思考的产物——克制、单色、带有轻微的铅笔阴影质感、大量的呼吸留白。它去除了所有不必要的装饰，只保留最纯粹的信息结构和“正在思考”的动态感。

## Diagram Tokens

### Palette (调色板)
```
primary:        #2b2b2b     (铅笔黑)
accent:         none        (单色调)
bg-base:        #f9f9f9     (极其轻微的暖白纸张)
text-main:      #2b2b2b     (铅笔灰黑)
```

### Typography (字体)
```
heading & body: handwritten (不均匀的手写体，但保持极高可读性)
```

### Line Style (线条)
```
stroke-width:    1.5px - 2px
stroke-type:     imperfect pen lines (不完美的墨水线/铅笔线)
```

### Surface (材质)
```
shading:        light shading with pencil texture (轻微的铅笔排线阴影)
texture:        notebook-style (笔记本质感)
```

## Prompt Injection Fragment

```text
Visual Style & Design Language:
- sketch / hand-drawn appearance
- imperfect pen lines
- notebook-style illustration
- light shading with pencil texture
- minimal monochrome palette
- slightly uneven handwritten typography
- clean composition with lots of whitespace

Layout Constraints:
- each layer proportional and clearly separated
- labels aligned horizontally
- no extra decorative elements
- educational technical schematic
- clean negative space

Mood:
- thoughtful
- conceptual
- visual thinking / whiteboard aesthetic

Canvas Behavior & Composition:
- STRICTLY NO TITLE, NO MAIN HEADING, NO HERO TYPOGRAPHY
- NO PRESENTATION HEADER, NO COVER-SLIDE LAYOUT, NO FOOTER CAPTIONS
- ONLY THE DIAGRAM ITSELF, cropped tightly around the diagram
- diagram occupies the full canvas (diagram-only composition)
- all text must belong directly to nodes or annotations, NO LARGE TYPOGRAPHIC ELEMENTS OUTSIDE LABELS
```

## Forbidden Patterns (禁止)
- ❌ 页面大标题与排版修饰 (page title / hero typography / presentation headers / annotations outside nodes)
- ❌ 完美的直线与精确对齐 (perfect straight lines / perfect alignment)
- ❌ 多余的装饰性元素 (extra decorative elements / doodles / stickers)
- ❌ 鲜艳的色彩与渐变 (bright colors / gradients / colorful palettes)
- ❌ 沉重的容器与阴影 (heavy containers / drop shadows / box-shadow)
- ❌ 抛光的数字 UI 界面感 (polished UI components / glossy effects)
- ❌ 3D 渲染特效 (3D rendering)
