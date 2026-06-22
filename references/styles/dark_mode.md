# Dark Mode Transform (暗色模式变换)

当 `color-mode: dark` 时，对当前风格的 Palette、Prompt Injection Fragment 和 Forbidden Patterns 应用以下变换。**风格的结构特征（线条粗细、节点形状、装饰元素、字体选择）保持不变**——仅反转明暗色彩通道。

## 通用变换规则

### Palette 映射

| Token | Light 值 → | Dark 值 | 规则 |
|:---|:---|:---|:---|
| `bg-base` | 白/浅色 | `#09090B` (OLED 墨黑) | 主背景反转 |
| `bg-surface` | 浅灰面板 | `#18181B` (深灰) | 卡片/节点填充反转 |
| `text-main` | 深色文字 | `#FAFAFA` (高亮白) | 主文字反转 |
| `text-light` | 中灰辅助 | `#A1A1AA` (锌灰) | 辅助文字反转 |
| `grid-line` | 浅灰网格 | `#3F3F46` (暗灰) | 连线/网格反转 |
| `primary` | 深色主色 | `#FFFFFF` (纯白) | 标题/核心数据反转 |
| `accent` | — | **保持不变** | 强调色不随模式改变 |
| `accent-light` | — | **保持不变** | 次级强调保持 |

### Prompt 追加段 (Dark Mode Addendum)

当 `color-mode: dark` 时，在风格的 Prompt Injection Fragment **末尾追加**以下段落：

```text
Color Mode Override — DARK:
- near-black or very dark background (#09090B or #18181B), NOT white, NOT light gray
- all text labels in white (#FAFAFA) or light gray (#A1A1AA), NOT dark text
- node/card fills in dark charcoal (#18181B or #27272A) with subtle light borders (1px rgba(255,255,255,0.1))
- accent color unchanged, but ensure sufficient contrast against dark background
- no white or light-colored large surface areas
- overall mood: theater-mode, focused, premium dark canvas
```

### Forbidden Patterns 追加

Dark mode 下额外禁止：
- ❌ 白色或浅色大面积背景 (white background / light-mode surfaces / bright canvas areas)
- ❌ 深色文字在深色背景上 (dark text on dark background — invisible)

---

## 风格专属 Dark Mode 覆写

以下覆写**叠加在通用规则之上**，处理各风格的特殊情况。

### Business (Dark)

```
palette overrides:
  bg-base:      #09090B      (替换 #FFFFFF)
  bg-surface:   #18181B      (替换 #F8FAFC)
  text-main:    #FAFAFA      (替换 #333333)
  text-light:   #A1A1AA      (替换 #666666)
  grid-line:    #3F3F46      (替换 #E2E8F0)
  primary:      #FFFFFF      (替换 #051C2C)

node-style overrides:
  fill:         #18181B solid (替换 #F8FAFC)
  border:       1px solid rgba(255,255,255,0.1) (替换 none)

prompt addendum specifics:
  - sharp and formal geometry maintained (still no rounded cards)
  - dark navy accent (#005EB8) may need lightening to #3B82F6 for visibility on dark bg
  - "light-gray segmentation surfaces" → "dark charcoal segmentation surfaces (#27272A)"
```

### Sketch (Dark)

```
palette overrides:
  bg-base:      #1a1a1a      (深色黑板/牛皮纸，替换 #fdfbf7)
  bg-surface:   #2d2d2d      (深色卡片，替换 #ffffff)
  text-main:    #f5f5dc      (粉笔白/米白，替换 #2d2d2d)
  text-light:   #4a4a4a      (暗灰网格点，替换 #e5e0d8)
  grid-line:    #f5f5dc      (浅色粉笔线，替换 #2d2d2d)

node-style overrides:
  fill:         #2d2d2d solid (深灰便利贴)
  border:       2px solid #f5f5dc (粉笔白粗边，替换 #2d2d2d)
  shadow:       4px 4px 0px 0px #f5f5dc (白色硬阴影，替换黑色)

prompt addendum specifics:
  - "warm paper-white background" → "dark chalkboard or dark kraft paper background"
  - "notebook dot-grid texture" → "dark surface with faint chalk-dust dot grid"
  - "thick black marker contour lines" → "thick white chalk or light marker contour lines"
  - "hand-drawn ink outlines" → "hand-drawn chalk outlines on blackboard"
  - sticky-note yellow (#fff9c4) 保持（在深色底上更突出）
  - sketch red (#ff4d4d) 保持
```

### Editorial Luxury (Dark)

```
palette overrides:
  bg-base:      #1a1410      (深色暖调，替换浅米色)
  bg-surface:   #2a2018      (深暖棕，替换浅色面板)
  text-main:    #F5F0E8      (暖白，替换深色文字)
  text-light:   #8A7E6E      (暖灰，替换辅助色)

prompt addendum specifics:
  - "cream/ivory background" → "deep warm-toned dark background (#1a1410)"
  - serif typography and editorial feel maintained
  - gold/copper accents may increase contrast for visibility
  - "sepia tone" → "dark sepia / moody editorial tone"
```
