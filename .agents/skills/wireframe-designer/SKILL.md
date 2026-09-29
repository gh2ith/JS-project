---
name: wireframe-designer
description: Standardized system for generating low-fidelity schematic wireframes and high-fidelity Figma artboard mockups matching the Bridgeway design language.
---

# Wireframe Designer Skill

This skill defines the exact process and assets for producing UX wireframes and visual design mockups for Bridgeway.

## 1. Low-Fidelity Schematic Syntax
- **Canvas**: `#F5F5F7` background, outer container frame with `#262626` stroke width 3.
- **Components**:
  - `LOGO`: Rectangle with diagonal `X` cross + bold `LOGO` text.
  - `[BUTTON]`: Rectangle with bold centered `[BUTTON]` text.
  - `HEADLINE HERE` / `TITLE HERE`: Uppercase heading text.
  - Paragraphs: Horizontal wire lines or `Lorem ipsum dolor sit amet...`.
  - Metrics: 2x2 or 1x3 grid boxes with `00+`, `00%`, `00/0`, `Title Here`.
  - Input Fields: `TITLE HERE` label, rectangular input with `[X]` icon and placeholder line.
  - Checkbox: Small box with checkmark + `Title Here`.
  - Footer: `&copy; 2026 Bridgeway. Built for a better internship experience.`

## 2. High-Fidelity Figma Artboard Structure
- **Figma Design System Shell**:
  - Top tab: `Figma Wireframe • [Page Name]`.
  - 12-column grid guide overlay in `#EFF6FF`.
  - Left margin: Numbered circular badges (`1`, `2`, `3`, `4`, `5`) and measurement brackets (`64px`, `48px`, `24px`).
  - Top labels: `Main Grid` ↓, `Typography` ⟷, `Navigation` →.
  - Right margin: Autolayout component callout arrows.
  - Real component design: Deep navy `#0F172A`, royal blue `#2563EB`, clean white `#FFFFFF` cards, and glassmorphic badges.
