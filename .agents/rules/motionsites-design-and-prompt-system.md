# MotionSites.ai — Design System & AI Prompt Engineering Guide

This document captures the visual philosophy, aesthetic tokens, component anatomy, and prompt engineering architecture of **MotionSites.ai** (https://motionsites.ai). Use this specification whenever designing, prompting, or recreating MotionSites-caliber websites, hero sections, and UI components.

---

## 1. Core Philosophy: "A Design System Expressed in Language"

Traditional web design uses Figma or visual builders; MotionSites bridges the gap to AI coding agents (Claude, Cursor, Bolt, Lovable, Antigravity) by formalizing high-end design into **structured, constraint-dense natural language prompts**.

### The Problem It Solves
Standard AI-generated websites default to "generic AI slop"—monotonous boxy layouts, plain default colors, lack of micro-animations, and uninspired typography.

### The MotionSites Solution
1. **Explicit Constraints:** Strict color tokens, precise font pairings, exact line heights, and padding.
2. **Layered Visual Depth:** Ambient radial glows, backdrop blurs, liquid-glass borders, subtle elevation shadows.
3. **Cinematic Motion:** Easing curves (`cubic-bezier(0.16, 1, 0.3, 1)`), staggered entrances, interactive previews.
4. **Information Architecture:** Asymmetric bento grids, announcement pills, interactive macOS/browser window frames with live indicators.

---

## 2. MotionSites Visual Language & Aesthetics

### A. Color & Lighting
* **Canvas Styles:**
  * **Sleek Light Mode:** Canvas `#F8FAFC`, Surface `#FFFFFF`, Border `#E2E8F0`, Accent `#2563EB`, Text `#0F172A`.
  * **Dark Cinematic / Cosmic:** Canvas `#090D16` or `#0F172A`, Surface `rgba(30, 41, 59, 0.7)`, Border `rgba(255, 255, 255, 0.08)`, Glows `rgba(99, 102, 241, 0.15)`.
* **Ambient Lighting:** Multi-stop radial gradients fixed behind the canvas:
  ```css
  background: 
    radial-gradient(circle at 15% 20%, rgba(37, 99, 235, 0.08) 0%, transparent 45%),
    radial-gradient(circle at 85% 15%, rgba(99, 102, 241, 0.06) 0%, transparent 45%),
    #0F172A;
  ```

### B. "Liquid-Glass" Glassmorphism Tokens
Signature frosted glass containers with specular edge highlights:
```css
.liquid-glass-card {
  background: rgba(255, 255, 255, 0.85); /* or rgba(15, 23, 42, 0.75) for dark */
  backdrop-filter: blur(16px) saturate(180%);
  -webkit-backdrop-filter: blur(16px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 20px;
  box-shadow: 
    0 20px 40px -15px rgba(15, 23, 42, 0.08),
    0 1px 3px rgba(15, 23, 42, 0.04),
    inset 0 1px 0 rgba(255, 255, 255, 0.6);
}
```

### C. Typography System
* **Display / Headings:**
  * Font: `Plus Jakarta Sans`, `Syne`, `Clash Display`, or `Anton` (for brutalist/cinematic).
  * Letter-spacing: `-0.03em` to `-0.04em` (tight tracking for high-impact editorial feel).
  * Scale: 40px to 64px desktop hero headline with balanced line-height (1.1 to 1.15).
* **Body / Subheadings:**
  * Font: `Inter`, `Geist`, or `Satoshi`.
  * Letter-spacing: `-0.01em`, color `#475569` (light) or `#94A3B8` (dark), line-height 1.6.

### D. Component Anatomy
1. **Announcement / Pill Badge:**
   * Pill shape (`rounded-full`), subtle gradient background, border with 1px accent.
   * Leading pulsing status dot (`animation: pulseDot 2s infinite`).
   * Clean text with subtle arrow: `✨ MotionSite 2.0 • Modern People Operations →`.
2. **Dual CTA Group:**
   * Primary: High-contrast filled button with colored drop shadow (`box-shadow: 0 4px 14px rgba(primary, 0.3)`), subtle translateY on hover.
   * Secondary: Frosted/outline button with light border and background hover tint.
3. **Interactive Window Chrome (Floating Product Mockup):**
   * Top bar with 3 macOS traffic light dots (Red `#EF4444`, Amber `#F59E0B`, Green `#10B981`).
   * Central security lock + simulated URL pill (`https://domain.internal/dashboard`).
   * Inner dashboard with 3 distinct stat cards and real-time activity stream.
4. **Bento Grid Layouts:**
   * Modular 3-column or asymmetric 2-column cards.
   * Each card features an isolated rounded icon container (48x48), bold title, clean multi-line description, and micro-metric or action link.
5. **Integrated 3-Column Footer:**
   * Col 1: Brand identity, address, direct phone, and email.
   * Col 2: Interactive functional form with local persistence or API dispatch.
   * Col 3: Stylized interactive map embed with location coordinates and route pin.

---

## 3. MotionSites Prompt Engineering Architecture

When generating pages or components in the MotionSites style, prompts follow this 6-part structure:

### Section 1: Objective & Role Framing
* **Role:** "Act as an elite frontend engineer and senior UI/UX designer specializing in high-converting, cinematic web applications."
* **Goal:** "Build a production-ready, interactive [Hero Section / Landing Page / Bento Grid] with MotionSites visual polish."

### Section 2: Visual Style & Design Direction
* Explicitly state the aesthetic: e.g., *"Modern Executive Blue & White theme combined with liquid-glass depth and subtle ambient glow."*
* Prohibit generic aesthetics: *"Do NOT use browser defaults, plain flat colors, or boxy templates. Implement rich gradients, subtle shadows, and frosted glass containers."*

### Section 3: Exact Design Tokens
* **Colors:** Explicit hex values for `--bg`, `--surface`, `--border`, `--primary`, `--text`, `--muted`.
* **Typography:** Font family, weight, tracking, and responsive clamp sizes.
* **Elevations & Radii:** 12px, 16px, 20px, 24px corner radii; 3 levels of box-shadows.

### Section 4: Component & Section Breakdown
Step-by-step definition of every visible element:
1. Header / Navbar
2. Hero Announcement Pill + Headline + Subheadline + CTAs
3. Floating Interactive Mockup Card with KPIs & Activity Stream
4. 6-Card Bento / Feature Grid
5. Proof / Social Proof Banner
6. Comprehensive Integrated Footer

### Section 5: Motion, Physics & Micro-Interactions
* Entry animations: Smooth upward fade (`opacity: 0, translateY(20px)` to `opacity: 1, translateY(0)`).
* Transition easing: `cubic-bezier(0.16, 1, 0.3, 1)`.
* Hover physics: `-2px` to `-4px` vertical float with elevated shadow.
* Active status indicators: Continuous keyframe pulse on badge dots.

### Section 6: Responsiveness & Structural Integrity
* Grid rules: `row g-4`, flex-wrap containers.
* Text wrapping: Enforce maximum characters per line to prevent horizontal card overflow.
* Interactive state management: LocalStorage persistence, clean modal dialogs, and instant toast notifications.

---

## 4. Reusable MotionSites AI Prompt Template

```markdown
Build a world-class, production-ready [Page Name] using modern HTML5, Bootstrap grid, and Vanilla CSS/JS (or React/Tailwind/Framer Motion). 

### Visual Theme & Direction
- Style: MotionSites.ai Liquid-Glass & Modern Executive SaaS.
- Palette: Background #F8FAFC, Surface #FFFFFF, Primary #2563EB, Text #0F172A, Muted #64748B, Border #E2E8F0.
- Typography: Plus Jakarta Sans for titles (letter-spacing -0.03em), Inter for body.
- Ambient Effects: Subtle background radial gradient glow, liquid-glass backdrop-filter (blur 16px).

### Required Macrostructure
1. Floating Blur Navbar: Logo with rounded icon box, centered links with hover underlines, right CTA.
2. MotionSites Hero:
   - Glowing announcement pill with pulsing dot ("✨ ...")
   - Punchy display headline (44px, bold, tight tracking)
   - Descriptive subheadline (max-width 640px)
   - Dual CTA buttons (Primary glow + Secondary outline)
   - Floating interactive dashboard preview card with macOS traffic dots, URL pill, live metrics, and activity feed.
3. Feature / Services Grid:
   - 3x2 bento layout with 18px rounded cards.
   - Tinted 48x48 icon containers, bold titles, 3-line wrapped descriptions, and directional action links ("Explore →").
4. Comprehensive 3-Column Footer:
   - Column 1: Brand bio, HQ address, phone, email.
   - Column 2: Working feedback/inquiry form saving to LocalStorage.
   - Column 3: Stylized interactive map card with pin marker and Google Maps link.

Ensure zero text overflow, responsive mobile breakpoints, and high-fidelity micro-animations.
```
