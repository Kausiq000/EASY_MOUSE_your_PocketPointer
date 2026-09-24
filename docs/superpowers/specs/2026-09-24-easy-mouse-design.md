# Easy Mouse Product Website — Specification

## 1. Product Overview & Core User Journey

**Product:** Easy Mouse is a desktop-control utility that converts any smartphone into a wireless trackpad/mouse for controlling laptops and PCs.

**Core Narrative:**
`PHONE` -> `WIRELESS CONNECTION` -> `COMPUTER CONTROL`

**Visitor Journey:**
1. **First Glance (0-3s):** The visitor arrives at an asymmetric dark-tech hero. The headline "Turn your phone into a wireless mouse" and an interactive live visual (smartphone trackpad transmitting wireless signals to a responsive laptop pointer) immediately establish what the product does.
2. **Action Path:** A prominent, high-contrast CTA button "DOWNLOAD EASY MOUSE" (`id="download-app"`, `data-download="true"`) gives an immediate action route.
3. **Understanding (3-10s):** The visitor explores the 3-step technical flow (01 Connect, 02 Pair, 03 Control) followed by 4 distinct capability presentations without repetitive 3-card templates.
4. **Interactive Sandbox:** The visitor tests interactive controller modes (Trackpad touch surface, Two-finger scroll simulation, and Media presentation remote) directly on the website.
5. **Conversion (Final CTA):** High-impact closing download section reinforces the premise with platform indicators and ready placeholder link.

---

## 2. Design System & Aesthetics (Taste Skill Directives)

### Brief Inference & Dials
- **Design Read:** Consumer utility / desktop-control hardware landing page, industrial dark-tech tactile language, graphite surfaces with precise technical linework and selective laser-crimson accents.
- **Dial Values:**
  - `DESIGN_VARIANCE: 7` (Asymmetric hero composition, diverse section structures, no repetitive card clones).
  - `MOTION_INTENSITY: 6` (60fps canvas pointer trailing physics, CTA magnetic hover, viewport reveal animations; strict fallback to static on `prefers-reduced-motion`).
  - `VISUAL_DENSITY: 5` (Balanced breathing room with technical micro-annotations and connection schematics).

### Color Palette
- **Canvas Base:** Obsidian `#090a0d`, Deep Charcoal `#0e1015`
- **Surface Elevation:** Graphite `#15181f`, Elevated Panel `#1c212c`
- **Linework & Borders:** Hairline `#272d3b`, Subtle Border `rgba(255, 255, 255, 0.08)`
- **Typography:** Primary Off-White `#f4f5f7`, Secondary Steel `#9aa2b1`, Muted `#5c6475`
- **Accent:** Laser Crimson `#ff2a4b`, Subtle Glow `rgba(255, 42, 75, 0.25)`, Active Highlight `rgba(255, 42, 75, 0.4)`
- *Strict Rule:* No purple/cyan AI gradients. Zero rainbow meshes.

### Typography (Local / System Stack, No External CDNs)
- **Headings / Display:** `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif` (`font-weight: 700-800`, optical tracking `-0.03em`).
- **Body:** System UI Sans (`font-weight: 400`, line-height `1.6`, max-width `60ch`).
- **Technical & Monospace Accents:** `"SF Mono", "Segoe UI Mono", "Roboto Mono", "Cascadia Code", monospace` (`font-size: 11-13px`, letter-spacing `0.06em`).

### Anti-AI Tells Checklist
- [x] **Zero em-dashes (`—` or `–`) anywhere.** Standard hyphens `-` only.
- [x] **No generic 3-card grid.** Each section uses an intentional, differentiated layout family.
- [x] **No centered generic hero.** Asymmetric 50/50 split layout.
- [x] **Eyebrow restraint:** Maximum 1 eyebrow per 3 sections (hero counts as 1).
- [x] **Shape consistency lock:** 6px-8px industrial corner radii on containers; tactile pill toggles.
- [x] **No fake precision metrics:** No fake "99.99% latency" or "500,000+ users" invented.
- [x] **Single-line desktop navigation** under 72px height.
- [x] **CTA button wrap ban:** All CTAs fit on a single line at desktop.

---

## 3. Architecture & Technical Structure

### File Structure
- `index.html` as the single self-contained, deployment-ready file containing:
  - `<style>`: Core design tokens, layout grid, typography, custom cursor styles, responsive breakpoints, animations.
  - Semantic HTML: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`.
  - `<script>`: Interactive hero device connection visualizer, custom canvas cursor trail + magnetic button physics, interactive controller mode sandbox, mobile menu toggle, scroll reveal observers.
- Zero dependencies: No npm packages, no build steps, no CDNs.

### Section Breakdown
1. **Header & Navigation (≤ 68px)**
   - Logo: `EASY MOUSE` with laser-red power/status glyph.
   - Links: How It Works (`#how-it-works`), Features (`#features`), Interactive Demo (`#interactive-demo`).
   - Nav CTA: "Download App" linking to `#download`.
   - Responsive mobile overlay toggle (accessible, single-tap drawer).
2. **Hero Section**
   - Asymmetric split layout (desktop `grid-template-columns: 1.1fr 0.9fr`).
   - Left: Value proposition "Turn your phone into a wireless mouse.", concise supporting copy explaining wireless laptop/PC control, primary CTA `DOWNLOAD EASY MOUSE` (`id="download-app"`, `data-download="true"`), secondary action "See how it works".
   - Right: Interactive Device Link Schematic. A stylized tactile phone trackpad wired with dynamic signal arcs to an animated laptop display screen where an on-screen cursor tracks movements in real-time.
3. **How It Works (Technical Pipeline)**
   - Layout: Continuous linear timeline connecting 3 technical stages:
     - `01 Connect` - Launch Easy Mouse on your phone and target laptop/PC.
     - `02 Pair` - Establish low-latency wireless communication across your local network.
     - `03 Control` - Glide, click, and navigate your computer desktop seamlessly from your screen.
4. **Core Capabilities (4 Differentiated Layouts)**
   - Tile 1 (Wide Technical Panel): *Wireless Desktop Navigation* (Freedom from fixed desk setups).
   - Tile 2 (Interactive Visual): *Precision Touch Surface* (Multi-touch gesture input with instant tactile feedback).
   - Tile 3 (Compact Metric Panel): *Always in Your Pocket* (No dongles, AAA batteries, or lost receivers).
   - Tile 4 (Quick-Start Flow): *Instant Zero-Fuss Pairing* (Ready in seconds whenever you need a mouse).
5. **Interactive Controller Sandbox**
   - Interactive live widget allowing visitors to toggle between:
     - Mode A: *Standard Trackpad* (move cursor + left/right click buttons).
     - Mode B: *Two-Finger Scroll Surface* (smooth vertical document pan).
     - Mode C: *Presentation Remote* (slide advance, laser pointer cue, media volume).
6. **Download CTA Section**
   - Striking high-contrast closing panel.
   - Headline: "YOUR PHONE. YOUR COMPUTER. ONE SIMPLE CONNECTION."
   - Prominent download button (`id="download-app"`, `data-download="true"`).
   - Clean platform indicators (Windows / macOS / Linux / iOS / Android) ready for download links.
7. **Footer**
   - Minimalist copyright, technical status indicator ("System Ready"), navigation links, and back-to-top trigger.

---

## 4. Cursor System & Motion Engine

- **Custom Dual-Element Cursor:**
  - Dot: 8px red center dot with smooth instant tracking.
  - Ring: 32px outer tracking ring with spring interpolation (`lerp: 0.18`).
  - Canvas Trail: Lightweight offscreen/overlay canvas rendering subtle fading red velocity streaks behind the cursor.
  - Hover Morph: Over buttons and links, the outer ring smoothly scales and locks to the button borders with a magnetic pull (`transform: translate`).
  - Touch/Mobile Handling: Completely removed when `(hover: none) or (pointer: coarse)` or viewport width `< 768px`.
  - Motion Preference: `@media (prefers-reduced-motion: reduce)` disables trailing particles and magnetic displacement.

---

## 5. Verification & Testing Protocol

1. **Responsive Testing:**
   - `375px` (Mobile portrait): Full navigation collapse into clean drawer, hero stack, touch targets ≥ 48px, zero horizontal overflow, custom cursor deactivated.
   - `768px` (Tablet): Clean 2-column or fluid stacked grid.
   - `1024px` (Laptop): Full desktop nav, balanced split hero.
   - `1440px` (Desktop): Controlled container `max-width: 1280px`, rich negative space, no stretched assets.
2. **Keyboard Navigation & Accessibility:**
   - Full Tab navigation with high-visibility red focus outlines (`:focus-visible`).
   - Valid ARIA attributes on interactive tabs and toggles.
   - WCAG AA contrast (minimum 4.5:1 on all text against dark surfaces).
3. **Anti-AI Design Audit:**
   - Verification of 0 em-dashes across all copy.
   - Confirmation of distinct layout families.
   - Confirmation of zero external network requests.
