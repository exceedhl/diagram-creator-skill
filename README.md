[English](README.md) | [简体中文](README_zh.md)

# Diagram Creator Skill

Diagram Creator is a skill that turns your ideas into professional infographic-quality diagrams using AI image generation. Simply describe what you want — a flowchart, architecture diagram, matrix, or timeline — and the AI assembles a structured prompt following proven visual recipes, then generates a polished diagram image in seconds.

## ✨ Core Capabilities

- **9 Diagram Types, One Skill**: Whether you need a decision flowchart, a layered architecture diagram, a 2×2 priority matrix, a product roadmap timeline, or a growth flywheel — just describe your intent in natural language. The AI automatically matches your request to the right diagram structure.
- **3 Curated Visual Styles**: Each diagram can be rendered in **Business** (McKinsey/BCG consulting quality), **Editorial Luxury** (warm paper textures with serif typography), or **Sketch** (hand-drawn whiteboard workshop feel). The AI picks a default or you can specify your preference.
- **Light & Dark Mode**: Every style supports both light and dark color modes. Dark mode is automatically activated when you ask for it or when embedding into a dark-themed slide deck.
- **No Title Pollution**: Tired of AI-generated diagrams that look like full PowerPoint pages with giant headings? A built-in "Canvas Behavior" constraint ensures the output is a clean, tightly-cropped diagram — ready to embed anywhere.
- **Embedding-Ready**: Diagrams can be generated as standalone images or as components designed to drop into slide decks, documents, or web pages. When embedding, you specify the target pixel size and the skill ensures pixel-perfect aspect ratio matching.

---

## 📐 Supported Diagram Types

| Type | Best For | Examples |
|:---|:---|:---|
| **Quadrant** | Priority analysis, SWOT, competitive mapping | 2×2 matrix with items plotted by two dimensions |
| **Timeline** | Roadmaps, milestones, historical progressions | Horizontal/vertical timeline with event markers |
| **Flowchart** | Workflows, decision trees, approval processes | Step-by-step process with branches and loops |
| **Architecture** | System design, tech stacks, microservices | Layered blocks with connections |
| **Pyramid** | Hierarchy models, Maslow's, maturity frameworks | Bottom-up stacked layers |
| **Cycle** | Iterative processes, PDCA, feedback loops | Circular continuous loop |
| **Funnel** | Conversion pipelines, sales stages, filtering | Top-wide to bottom-narrow stages |
| **Org Chart** | Team structure, reporting lines, hierarchy | Tree with parent-child nodes |
| **Flywheel** | Growth engines, self-reinforcing loops | Circular momentum diagram |

---

## 🎨 Visual Styles

### 1. Business (商务经典)
> McKinsey/BCG consulting-grade diagrams. Deep navy accents on pure white, sharp geometric shapes, Helvetica typography, zero decorative noise. Perfect for board presentations and strategy decks.

### 2. Editorial Luxury (暖调奢华)
> Warm ivory paper backgrounds with bronze accents, elegant serif typography (Playfair Display), hairline dividers, and generous whitespace. Ideal for annual reports, brand narratives, and executive storytelling.

### 3. Sketch (手绘白板)
> Authentic sketchnote aesthetic with hand-drawn wobbly borders, hard offset shadows, dot-grid paper texture, marker-style typography, and sticky-note accents. Great for brainstorming sessions, workshops, and creative pitches.

Each style also supports **Dark Mode** — inverting backgrounds while preserving the style's unique character (line weights, node shapes, decorative elements remain unchanged).

---

## 🚀 Installation & Usage

### Method 1: Skill Installer

If your AI environment supports directive-based installation:

```bash
npx skills add exceedhl/diagram-creator-skill
```

### Method 2: Direct Directory Copy

1. Download or clone this repository.
2. Copy the entire `diagram-creator-skill` folder into your project's agent skills directory (e.g., `.agents/skills/`).
3. The agent will automatically detect `SKILL.md` and load the diagram generation capabilities.

---

## 💬 Prompt Examples

**Example 1: Quick flowchart**
> "Generate a flowchart showing our CI/CD pipeline: code push → build → test → deploy to staging → approval → production. Use the Sketch style."

**Example 2: Strategy matrix**
> "Create a 2×2 priority matrix. X-axis is Implementation Effort (low to high), Y-axis is Business Impact (low to high). Plot these items: AI Chatbot (high impact, low effort), ERP Migration (high impact, high effort), Office Redesign (low impact, high effort), Email Templates (low impact, low effort). Use Business style."

**Example 3: Architecture diagram**
> "Draw a 3-layer system architecture: Data Layer (PostgreSQL, Redis, S3), Service Layer (Auth Service, API Gateway, ML Pipeline), Client Layer (Web App, Mobile App, CLI). Show connections between layers. Editorial Luxury style, dark mode."

**Example 4: Growth flywheel**
> "Create a flywheel diagram with 4 stages: Better Product → More Users → More Data → Better AI Models → (back to Better Product). Sketch style."

---

