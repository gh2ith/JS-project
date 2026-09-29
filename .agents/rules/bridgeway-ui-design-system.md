# Bridgeway UI Design System: Modern Executive Blue & White

This document defines the official **Modern UI Design System** for Bridgeway.
It replaces the legacy warm dark ("Harnen") theme (`#181713` / `#f0e9de`) with a clean, high-clarity, modern SaaS aesthetic inspired by modern enterprise cloud dashboards (Linear, Stripe, Vercel).

Always adhere to these design tokens, component rules, and layout standards when creating or updating any frontend page, component, modal, or template in Bridgeway.

---

## 1. Visual Theme & Atmosphere

- **Theme Identity:** Modern Executive White & Royal Blue.
- **Atmosphere:** Clean, luminous, trustworthy, structured, and fast.
- **Key Visual Elements:**
  - Crisp white cards with ultra-soft shadows on a gentle slate canvas.
  - Vibrant Royal Blue accents (`#2563EB`) providing focal points and energy.
  - High-readability slate typography with strong contrast hierarchy.
  - Subtle ambient radial gradients in the background to avoid clinical starkness.
  - Clean hairline borders (`#E2E8F0`) with rounded interactive components.

---

## 2. Core Color Palette & Design Tokens

### Backgrounds & Surfaces
| Token | Variable | Hex / CSS Value | Description & Usage |
| :--- | :--- | :--- | :--- |
| **Canvas Background** | `--bg` / `--adm-bg` / `--cd-bg` | `#F8FAFC` (Slate 50) | Main page background |
| **Surface (Card / Modal)** | `--surface` | `#FFFFFF` (Pure White) | Card containers, dropdowns, modal dialogs, data tables |
| **Surface Muted / Alt** | `--surface-muted` | `#F1F5F9` (Slate 100) | Secondary blocks, filter bars, subtle callouts |
| **Surface Subtle** | `--surface-subtle` | `#F8FAFC` (Slate 50) | Inner table rows on hover, subtle input fields |
| **Border Default** | `--border` | `#E2E8F0` (Slate 200) | Standard 1px divider and container outline |
| **Border Hover** | `--border-hover` | `#CBD5E1` (Slate 300) | Interactive borders on card/input hover |
| **Border Subtle** | `--border-subtle` | `rgba(15, 23, 42, 0.06)` | Table dividers, delicate separators |

### Primary Brand (Blue)
| Token | Variable | Hex / CSS Value | Description & Usage |
| :--- | :--- | :--- | :--- |
| **Primary Brand** | `--primary` | `#2563EB` (Blue 600) | Primary CTA buttons, active tabs, icon highlights, active links |
| **Primary Dark / Hover** | `--primary-dark` | `#1D4ED8` (Blue 700) | Hover state for primary buttons |
| **Primary Active** | `--primary-hover` | `#1E40AF` (Blue 800) | Active/pressed state for primary buttons |
| **Primary Light / Tint** | `--primary-light` | `#EFF6FF` (Blue 50) | Icon badge containers, active pill backgrounds, row highlights |
| **Primary Border** | `--primary-border` | `#DBEAFE` / `#BFDBFE` | Border for active/selected items, blue pill outlines |
| **Primary Glow** | `--primary-glow` | `rgba(37, 99, 235, 0.22)` | Button box-shadows, input focus halos |

### Typography & Text Hierarchy
| Token | Variable | Hex / CSS Value | Description & Usage |
| :--- | :--- | :--- | :--- |
| **Text Primary** | `--text` | `#0F172A` (Slate 900) | H1–H4 titles, card headers, primary metric numbers |
| **Text Secondary** | `--text-secondary` | `#475569` (Slate 600) | Body paragraphs, descriptive subtitles, form labels |
| **Text Muted** | `--text-muted` | `#94A3B8` / `#64748B` | Timestamps, counters, placeholder text, secondary icons |

### Functional / Semantic States
| State | Text & Accent | Background (Light Tint) | Border Tint | Usage |
| :--- | :--- | :--- | :--- | :--- |
| **Success / Approved** | `#059669` / `#10B981` | `#ECFDF5` / `#F0FDF4` | `#A7F3D0` | Approved applications, verified badges, positive KPI deltas |
| **Warning / Pending** | `#D97706` | `#FFFBEB` | `#FDE68A` | Pending approvals, action required, warnings |
| **Danger / Rejected** | `#DC2626` / `#EF4444` | `#FEF2F2` | `#FECACA` | Rejected applications, delete triggers, error banners |
| **Indigo / Accent** | `#4F46E5` / `#7C3AED` | `#EEF2FF` / `#FAF5FF` | `#C7D2FE` | Supervisor / company badges, special highlights |
| **Teal / Secondary** | `#0D9488` | `#F0FDFA` | `#99F6E4` | Secondary metric badges |

---

## 3. Shadows & Elevation

```css
--shadow-xs: 0 1px 2px 0 rgba(15, 23, 42, 0.04);
--shadow-sm: 0 1px 3px 0 rgba(15, 23, 42, 0.05), 0 1px 2px -1px rgba(15, 23, 42, 0.05);
--shadow-md: 0 4px 6px -1px rgba(15, 23, 42, 0.06), 0 2px 4px -2px rgba(15, 23, 42, 0.04);
--shadow-lg: 0 10px 15px -3px rgba(15, 23, 42, 0.08), 0 4px 6px -4px rgba(15, 23, 42, 0.04);
--shadow-xl: 0 20px 25px -5px rgba(15, 23, 42, 0.08), 0 8px 10px -6px rgba(15, 23, 42, 0.03);
--shadow-primary: 0 4px 14px 0 rgba(37, 99, 235, 0.28);
```

---

## 4. Typography Rules

- **Primary Headings & Key Metrics:** `'Plus Jakarta Sans', sans-serif`
  - Weights: `600` (Semi-bold), `700` (Bold), `800` (Extra-bold)
  - Letter-spacing: `-0.015em` to `-0.02em` for tight, modern headings
- **Body & Interface Elements:** `'Inter', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif`
  - Weights: `400` (Regular), `500` (Medium), `600` (Semi-bold)
  - Line-height: `1.5` to `1.6` for clean readability

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
```

---

## 5. Background Ambience System

Modern pages use a layered ambient background rather than a flat plain gray:

```css
/* Ambient Background Glow */
.ambient-glow {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    height: 400px;
    background: radial-gradient(circle at 50% -80px, rgba(37, 99, 235, 0.08), transparent 70%);
    pointer-events: none;
    z-index: 0;
}

/* Subtle Ambient Dot Grid Pattern */
.ambient-pattern {
    position: fixed;
    inset: 0;
    z-index: 0;
    background-image: radial-gradient(rgba(15, 23, 42, 0.055) 1px, transparent 1px);
    background-size: 28px 28px;
    mask-image: radial-gradient(ellipse at 50% 35%, black 40%, transparent 85%);
    -webkit-mask-image: radial-gradient(ellipse at 50% 35%, black 40%, transparent 85%);
    pointer-events: none;
}
```

---

## 6. Core Component Standards

### A. Cards & Containers
- **Base Style:**
  ```css
  background: #ffffff;
  border: 1px solid #e2e8f0;
  border-radius: 16px;
  box-shadow: 0 1px 3px 0 rgba(15, 23, 42, 0.05);
  transition: all 0.2s ease;
  ```
- **Interactive Card Hover State:**
  ```css
  border-color: #cbd5e1;
  transform: translateY(-2px);
  box-shadow: 0 10px 15px -3px rgba(15, 23, 42, 0.08);
  ```

### B. Buttons
- **Primary Action:**
  ```css
  background: #2563eb;
  color: #ffffff;
  border: none;
  border-radius: 10px;
  font-weight: 600;
  padding: 0.65rem 1.25rem;
  box-shadow: 0 4px 12px rgba(37, 99, 235, 0.25);
  transition: all 0.2s ease;
  ```
  *Hover:* `background: #1d4ed8; transform: translateY(-1px); box-shadow: 0 6px 16px rgba(37, 99, 235, 0.35);`

- **Secondary / Outline:**
  ```css
  background: #ffffff;
  color: #0f172a;
  border: 1px solid #e2e8f0;
  border-radius: 10px;
  font-weight: 500;
  padding: 0.65rem 1.25rem;
  transition: all 0.2s ease;
  ```
  *Hover:* `background: #f8fafc; border-color: #cbd5e1; color: #0f172a;`

- **Ghost / Tertiary:**
  ```css
  background: transparent;
  color: #475569;
  border: none;
  border-radius: 8px;
  padding: 0.5rem 0.85rem;
  ```
  *Hover:* `background: #f1f5f9; color: #0f172a;`

### C. Form Controls & Inputs
- **Base Input:**
  ```css
  background: #ffffff;
  border: 1px solid #e2e8f0;
  border-radius: 10px;
  color: #0f172a;
  padding: 0.65rem 0.95rem;
  font-size: 0.875rem;
  transition: border-color 0.15s ease, box-shadow 0.15s ease;
  ```
- **Input Focus State:**
  ```css
  border-color: #2563eb;
  box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.15);
  outline: none;
  ```
- **Labels:**
  ```css
  font-weight: 600;
  font-size: 0.825rem;
  color: #334155;
  margin-bottom: 0.4rem;
  display: block;
  ```

### D. Status Badges & Pills
Always use pill-shaped badges (`border-radius: 9999px`) with 1px border and matching light tint:
```html
<!-- Approved / Success -->
<span class="badge" style="background: #ecfdf5; color: #059669; border: 1px solid #a7f3d0; border-radius: 9999px; font-weight: 600; padding: 0.3rem 0.75rem; font-size: 0.75rem;">
    <i class="bi bi-check-circle me-1"></i>Approved
</span>

<!-- Pending / Warning -->
<span class="badge" style="background: #fffbeb; color: #d97706; border: 1px solid #fde68a; border-radius: 9999px; font-weight: 600; padding: 0.3rem 0.75rem; font-size: 0.75rem;">
    <i class="bi bi-clock me-1"></i>Pending
</span>

<!-- Rejected / Danger -->
<span class="badge" style="background: #fef2f2; color: #dc2626; border: 1px solid #fecaca; border-radius: 9999px; font-weight: 600; padding: 0.3rem 0.75rem; font-size: 0.75rem;">
    <i class="bi bi-x-circle me-1"></i>Rejected
</span>

<!-- Blue / Informational -->
<span class="badge" style="background: #eff6ff; color: #2563eb; border: 1px solid #dbeafe; border-radius: 9999px; font-weight: 600; padding: 0.3rem 0.75rem; font-size: 0.75rem;">
    Active
</span>
```

### E. Tables & Data Grids
- **Header:** Background `#f8fafc`, uppercase text (`font-size: 0.75rem`, `letter-spacing: 0.5px`, color `#64748b`), border-bottom `1px solid #e2e8f0`.
- **Rows:** White `#ffffff`, border-bottom `1px solid #f1f5f9`, hover: `background: #f8fafc`.
- **Text Alignment:** Metric numbers right-aligned, status badges centered or aligned with headers.

### F. Navigation Topbar
- **Background:** `#ffffff` with `border-bottom: 1px solid #e2e8f0`.
- **Shadow:** `box-shadow: 0 1px 3px rgba(15, 23, 42, 0.05)`.
- **Profile Pill:** `#f8fafc` pill with `border: 1px solid #e2e8f0`, avatar with `border: 2px solid #2563eb`, name `#0f172a`.
- **Dropdown:** Floating card `#ffffff` with `border-radius: 12px`, `box-shadow: 0 10px 25px -5px rgba(15, 23, 42, 0.1)`.

---

## 7. Migration Checklist from Legacy Dark Theme

When updating any page from the legacy dark theme (`#181713`) to the modern blue-and-white system:
1. Replace body background `#181713` with `#f8fafc`.
2. Replace `.premium-card` dark background (`#211f1a`) with clean white (`#ffffff`).
3. Replace cream borders `rgba(240, 233, 222, 0.14)` with `#e2e8f0` (hover `#cbd5e1`).
4. Replace cream text `#f0e9de` with `#0f172a` (primary) and `#475569` (secondary).
5. Replace solid cream buttons (`.premium-btn`) with Royal Blue CTA (`#2563eb`, hover `#1d4ed8`, text `#ffffff`).
6. Update dark form inputs (`.premium-input`) from `#181713` to clean white `#ffffff` with `#e2e8f0` border and `#2563eb` focus halo.
7. Ensure Google Fonts (`Plus Jakarta Sans` + `Inter`) and Bootstrap Icons are loaded.
