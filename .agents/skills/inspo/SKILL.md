---
name: inspo
description: >-
  Query real production websites, design systems, palettes, typography, and reference JSX components from the Inspo MCP archive. Use when designing, redesigning, or styling web pages and UI components, or when seeking visual taste, aesthetics, macrostructures, and responsive design patterns.
---

# Inspo Design Reference & Aesthetic Skill

Inspo provides access to an archive of 830+ real production websites, 2,300+ captured desktop and mobile pages, traced color palettes, real fonts, DOM-extracted design systems, and 68 canonical reference components with copy-pasteable JSX.

Use this skill to ground UI designs in proven, high-end production aesthetics instead of generic default templates.

---

## When to Use This Skill
- Designing a new web page, screen, dashboard, or landing section.
- Redesigning or elevating an existing frontend UI.
- The user asks for design inspiration, visual references, moodboards, or aesthetic directions (e.g., editorial, brutalist, warm paper, dark SaaS, luxury agency).
- Selecting harmonious color palettes, font pairings, spacing scales, and layout macrostructures.
- Looking for production component implementations (heroes, pricing cards, footers, navs).

## When NOT to Use
- The project already has an established design system, UI tokens, or strict component library (the project's existing design conventions always take precedence).
- Working strictly on backend logic, database schemas, APIs, bug fixes, or infrastructure.
- The user has already provided an exact, explicit layout or design spec.

---

## Available MCP Tools & Workflow

When the Inspo MCP server is connected (`https://inspomcp.dev/api/mcp`), the following tools are available:

### 1. `recommend(brief, macrostructure?, pageType?, mode?, vibe?, color?, device?)`
**Start here for any new UI task.** Generates a complete design moodboard from a plain-text prompt:
- Recommends a macrostructure pattern and shortlist
- Returns 5 exemplar production sites with screenshot URLs
- Suggests matching reference components
- Recommends an extracted color palette and evidence packet
- Injects critical `heroGuidance` and `spacingGuidance`

### 2. `search_screens(query, style?, industry?, macrostructure?, mode?, vibe?, color?, ...)`
Hybrid lexical and semantic search across the 2,300+ screen archive.
- Returns desktop + mobile screenshot URLs, traced font stacks, palettes, and fold autopsies.

### 3. `get_design_system(slug, live?)`
Extracts the full `DESIGN.md` for any site in the archive:
- Primary, secondary, neutral, and accent colors
- Type ramp (headings, body sizes, weights, line heights)
- CSS variables, spacing scales, container max-widths, and detected tech stack.

### 4. `find_reference_components(type?, macro?)` & `get_reference_jsx(type, id)`
Access 68 canonical production component blueprints:
- Categories: `hero`, `nav`, `pricing`, `footer`, `features`, `cta`, `faq`, `testimonials`
- Use `get_reference_jsx` to retrieve production-ready JSX code directly.

### 5. `get_filters()`
Returns all accepted enumeration values for styles, vibes, industries, page types, and the 19 macrostructures. See detailed descriptions in [Macrostructures Reference](./references/macrostructures.md).

---

## Core Aesthetic & Composition Principles

Inspo enforces two critical composition rules learned from real production websites:

### 1. Hero Guidance (100svh Rule)
- **Constraint**: Compose the hero section to fit cleanly within the first viewport (`~1280×800` or `100svh`). Never allow the primary hero callout to awkwardly overflow below the fold on initial load.
- **Visual Impact**: Place the main headline, subtitle, primary CTA, and supporting visual/mockup within the immediate field of view.

### 2. Spacing & Container Guidance
- **Section Rhythm**: Real production websites use generous block spacing—typically **80px to 160px** between distinct sections. Avoid cramping consecutive blocks together.
- **Content Column**: Keep all body copy and text elements contained inside a centered, padded layout column with appropriate max-width (`1200px` to `1280px` for standard layouts, `640px` to `760px` for readable prose). Never let text touch viewport boundaries.

---

## Local Repository Files
The full source code, component examples, and offline assets are cloned in:
- `inspo/`: Cloned repository
- `inspo/apps/web/public/examples/`: Static HTML example sites and thumbnails
- `inspo/apps/mcp/`: MCP server code, benchmarks, and tools specification
