# Enhanced MotionSites-Optimized Prompt: Interactive Guest Journey Landing Page

> **Role & Directive:** Act as an elite principal frontend engineer and award-winning UI/UX designer. Modify **ONLY the guest-facing Landing/Home Page** of the HR Management System. Do **NOT** change the design, layout, navigation, or functionality of the authenticated HR or Employee pages. The interactive path concept is **exclusively for the public/guest landing page before login**.

---

## 1. Visual Theme & Design System (MotionSites Standard)

* **Design Aesthetic:** MotionSites Liquid-Glass & Modern Executive SaaS.
* **Palette Tokens:**
  * Canvas: `#F8FAFC` with ambient radial glows (`rgba(37, 99, 235, 0.04)` and `rgba(99, 102, 241, 0.04)`).
  * Surfaces: `rgba(255, 255, 255, 0.92)` with `backdrop-filter: blur(16px)` and `border: 1px solid #E2E8F0`.
  * Active/Primary: `#2563EB` (Royal Blue) with glow shadow `0 4px 14px rgba(37, 99, 235, 0.3)`.
  * Typography: `Plus Jakarta Sans` for bold display headings (`letter-spacing: -0.03em`), `Inter` for clean body copy.
* **Prohibited:** No cartoonish gamification, no excessive fluorescent neon, no boxy default templates.

---

## 2. Interactive SVG Winding Path & Traveler Architecture

Implement a continuous, responsive **SVG Winding Path** running vertically through the guest landing page:

1. **Path Physics & Layers:**
   * **Base Path:** Subtle dashed/solid guide path (`stroke: #CBD5E1; stroke-width: 4px; stroke-dasharray: 8 6;`).
   * **Progress Path:** High-contrast illuminated path (`stroke: #2563EB; stroke-width: 5px; filter: drop-shadow(0 0 8px rgba(37, 99, 235, 0.5));`).
   * **Scroll-Bound Math:** Synchronize progress using native `getPointAtLength()` and `getTotalLength()`. As the guest scrolls, `stroke-dashoffset` decreases in direct proportion to scroll depth.
2. **The Visual Traveler:**
   * A sleek, corporate 32px glowing orb with:
     * Outer ambient pulse wave (`animation: pulseOrb 2s infinite`).
     * Inner royal blue core (`#2563EB`) with specular white border and glowing halo.
     * Real-time tangent rotation along the curve: `Math.atan2(dy, dx)`.
   * Follows the real mathematical curve of the SVG path. Moves forward on scroll-down, reverses smoothly on scroll-up.
3. **Milestone Points & Activation:**
   * 8 milestone nodes + 1 destination node placed at the curve apexes.
   * When traveler reaches milestone $N$:
     * Node illuminates to royal blue with an active pulse ring.
     * Corresponding card activates (`opacity: 1; transform: translateY(-4px); border-color: #93C5FD;`).
     * Backward scroll smoothly reverses the activation.

---

## 3. Guest Journey Macrostructure (8 Milestone Points + Login)

### Point 1 — WELCOME & START
* MotionSites SaaS hero:
  * Glowing pill badge: `✨ MotionSite HR 2.0 • Modern People Operations`
  * High-impact headline: **"A Smarter Way to Manage Your Workplace"**
  * Subtitle explaining unified people operations.
  * Dual CTAs: *"Explore the System ↓"* (smooth-scrolls down path) & *"Portal Login →"*.
  * Floating interactive macOS preview card with 3 live KPI stat cards (Total Workforce, Leave Requests, Task Completion) and real-time activity stream.

### Point 2 — ABOUT THE PLATFORM
* Platform mission: Replacing disconnected spreadsheets with an agile, synchronized workspace.
* Highlight badge: **100% LocalStorage Sync • Zero backend required**.

### Point 3 — HR PLATFORM SERVICES
* Clean 6-card bento grid introducing core capabilities:
  1. *Employee Directory* (centralized profiles)
  2. *Leave Management* (date pickers & tracking)
  3. *Task Management* (priority levels & solutions)
  4. *Company Policies* (instant rulebook access)
  5. *Zoom Coordination* (virtual meetings)
  6. *Feedback System* (direct HR inbox)

### Point 4 — EMPLOYEE EXPERIENCE
* Visual step-by-step pipeline showing the frictionless employee lifecycle:
  `Onboarding → Profile → Tasks → Leave Requests → Direct Voice`

### Point 5 — TASK MANAGEMENT
* Agile task delegation workflow preview:
  * **HR Role:** Create tasks, assign priorities, monitor Kanban columns, review submitted deliverables.
  * **Employee Role:** Inspect assigned items, execute work, and submit code deliverables.

### Point 6 — LEAVE MANAGEMENT
* 3-step absence lifecycle:
  `Submit Request (Date Picker) → Balance Check (14 Days) → HR Turnaround (Avg 4h)`

### Point 7 — COMPANY POLICIES
* Centralized governance directory:
  * Dynamic compliance rules loaded from `policies.json`.
  * Searchable code of conduct, remote work guidelines, and team benefits.

### Point 8 — CONTACT & FEEDBACK
* Comprehensive integrated Bootstrap grid:
  * **Col 1 (HQ Info):** King Hussein Business Park, Bldg 23, Amman, Jordan • Direct phone & email.
  * **Col 2 (Feedback Form):** Working form that saves submissions into `localStorage['bridgeway_feedback_inbox']` with toast alert.
  * **Col 3 (Office Map):** Stylized interactive Amman headquarters map embed with pinpoint marker and Google Maps link.

### FINAL DESTINATION — PORTAL LOGIN
* High-impact CTA banner: **"Ready to Enter the Workplace?"**
* Primary action button: **"Login to HR System →"** triggering the login portal modal or redirecting to `login.html`.

---

## 4. Strict Scope Isolation & Unchanged Authenticated Dashboards

* **Guest Only:** The interactive winding path and traveler are active **strictly** when `currentRole === 'guest'`.
* **Zero Disruption to Auth:**
  * When logged in as **Employee (Sarah Jenkins)** or **HR Admin (Alex Vance)**, the winding path is completely **hidden**.
  * Authenticated users receive their standard, professional, uncluttered executive dashboard layout with their personalized tools, metrics, and direct CRUD tables.
* **Zero Backend Breaks:** All existing LocalStorage keys (`bridgeway_current_role`, `bridgeway_feedback_inbox`), mock data, and JS functions remain 100% functional.
