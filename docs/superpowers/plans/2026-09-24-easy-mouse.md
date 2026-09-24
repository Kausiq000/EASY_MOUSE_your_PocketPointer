# Easy Mouse Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build the complete Easy Mouse website from scratch as a high-performance, single-file HTML/CSS/JS product marketing experience that immediately communicates "PHONE -> WIRELESS CONNECTION -> COMPUTER CONTROL".

**Architecture:** A monolithic, zero-dependency `index.html` structure with modular CSS custom property tokens, semantic markup, and an event-driven vanilla JS runtime handling interactive hardware simulations, custom canvas cursor trails, magnetic physics, and responsive viewports.

**Tech Stack:** Semantic HTML5, Vanilla CSS3 (Custom properties, CSS Grid, Flexbox, Transforms), Vanilla JavaScript ES6+ (Canvas 2D API, IntersectionObserver, MatchMedia).

**Spec:** `docs/superpowers/specs/2026-09-24-easy-mouse-design.md`

## Global Constraints
- Pure HTML, embedded Vanilla CSS (`<style>`), and Vanilla JS (`<script>`) in `index.html`.
- Zero external dependencies: no CDNs, no external font stylesheets, no npm libraries.
- Zero em-dashes (`—` or `–`) anywhere on the page (use standard hyphen `-` only).
- Primary download button MUST have `id="download-app"` and `data-download="true"`.
- Asymmetric split hero; no generic centered hero; no purple/blue AI gradient mesh; no generic 3-card grid.
- Custom cursor disabled on mobile/touch (`(hover: none) or (pointer: coarse)` or viewport `< 768px`).
- Full respect for `prefers-reduced-motion` across all animations and cursor effects.
- Strict WCAG AA contrast (minimum 4.5:1 for body copy).

## Review Focus
1. Viewport resize from desktop to mobile (375px) without horizontal scroll or broken layout.
2. Touch device interaction does not show or get blocked by the desktop custom cursor.
3. Download button click provides immediate user feedback without navigation failure while placeholder link is active.
4. Canvas rendering performance remains stable 60fps without unbounded particle memory growth.
5. All interactive modes (Trackpad, Scroll, Remote) operate smoothly and update the simulated PC display without console errors.

---

### Task 1: Scaffolding HTML5 Structure & Design System Tokens

**Files:**
- Create: `index.html`
- Test: In-browser inspection of root CSS variables, fonts, and dark theme foundation.

**Interfaces:**
- Produces: CSS custom properties (`--bg-base`, `--bg-surface`, `--accent-red`, `--text-primary`, `--font-sans`, `--font-mono`), global reset, responsive container wrappers.

- [ ] **Step 1: Create `index.html` with complete semantic shell and CSS Design System**
  - Set meta tags (viewport, description, title).
  - Define CSS tokens for dark industrial graphite palette and laser crimson accent.
  - Implement system font fallbacks with tight tracking on headings.
  - Add reduced-motion base queries.

- [ ] **Step 2: Verify HTML renders correctly with zero console errors and valid CSS tokens**
  - Run headless browser or server check to ensure clean loading.

- [ ] **Step 3: Commit**
  ```bash
  git add index.html
  git commit -m "feat: scaffold index.html and design system tokens"
  ```

---

### Task 2: Header & Responsive Navigation

**Files:**
- Modify: `index.html`

**Interfaces:**
- Produces: Sticky navigation bar with brand logomark, laser-red status indicator, section anchors, download action button, and mobile hamburger drawer.

- [ ] **Step 1: Write markup and styles for sticky navigation**
  - Brand mark: "EASY MOUSE" with pulsing red connection status dot.
  - Anchor navigation: "How It Works", "Features", "Modes".
  - Nav CTA: "Download App" linking to `#download`.
  - Responsive hamburger button for viewports `< 768px`.

- [ ] **Step 2: Implement mobile navigation toggle logic**
  - Accessible mobile drawer with ARIA attributes and background scroll lock when open.

- [ ] **Step 3: Verify navigation height <= 68px and single line at 1024px+**

- [ ] **Step 4: Commit**
  ```bash
  git add index.html
  git commit -m "feat: add sticky navigation and mobile menu"
  ```

---

### Task 3: Asymmetric Split Hero & Live Connection Visualizer

**Files:**
- Modify: `index.html`

**Interfaces:**
- Produces: Hero section with value proposition, primary download CTA (`id="download-app"`), and live interactive schematic demonstrating Phone -> Wireless Link -> Laptop Pointer.

- [ ] **Step 1: Build asymmetric split hero layout**
  - Left column: Headline "Turn your phone into a wireless mouse.", supporting text, primary download CTA button (`id="download-app"`, `data-download="true"`), secondary action "See How It Works".
  - Right column: Interactive device link schematic container.

- [ ] **Step 2: Implement interactive Phone -> Computer simulation in Vanilla JS**
  - Render phone silhouette with interactive trackpad area.
  - Render animated wireless pulse waves connecting to a simulated laptop screen.
  - Moving the pointer over the phone trackpad causes real-time cursor movement and click cues on the laptop display.

- [ ] **Step 3: Test hero visibility and CTA placement at 1440px and 375px**

- [ ] **Step 4: Commit**
  ```bash
  git add index.html
  git commit -m "feat: implement hero section with interactive device visualizer"
  ```

---

### Task 4: "How It Works" Technical Pipeline

**Files:**
- Modify: `index.html`

**Interfaces:**
- Produces: 3-step continuous flow: 01 Connect -> 02 Pair -> 03 Control.

- [ ] **Step 1: Build linear technical timeline structure**
  - Step 01: Connect (Open Easy Mouse on phone and computer).
  - Step 02: Pair (Instant local wireless link).
  - Step 03: Control (Precision desktop control from your touchscreen).
  - Technical hairline connectors and active step glow.

- [ ] **Step 2: Test responsiveness on 375px (vertical stack) and 1024px+ (horizontal pipeline)**

- [ ] **Step 3: Commit**
  ```bash
  git add index.html
  git commit -m "feat: add How It Works technical pipeline"
  ```

---

### Task 5: Core Capabilities (4 Differentiated Layouts)

**Files:**
- Modify: `index.html`

**Interfaces:**
- Produces: 4 feature presentations avoiding generic 3-card monotony.

- [ ] **Step 1: Implement 4 distinct capability presentations**
  - Feature 1: Wide technical panel for *Wireless Desktop Navigation*.
  - Feature 2: Visual panel with gesture breakdown for *Precision Touch Surface*.
  - Feature 3: Compact hardware-free panel for *Zero Hardware Hassle*.
  - Feature 4: Flow panel for *Instant Setup & Auto-Discovery*.

- [ ] **Step 2: Ensure zero em-dashes and concise, accurate copy**

- [ ] **Step 3: Commit**
  ```bash
  git add index.html
  git commit -m "feat: add 4 differentiated capability sections"
  ```

---

### Task 6: Interactive Controller Sandbox

**Files:**
- Modify: `index.html`

**Interfaces:**
- Produces: Mode switcher (Trackpad, Two-Finger Scroll, Presentation Remote) with live interactive canvas/DOM demo.

- [ ] **Step 1: Build sandbox container with tabbed mode controls**
  - Tab 1: Trackpad Mode (cursor navigation, left/right click, drag).
  - Tab 2: Scroll Mode (two-finger vertical swipe simulation).
  - Tab 3: Presentation Remote (slide next/prev, media control).

- [ ] **Step 2: Implement stateful Vanilla JS sandbox interactivity**
  - Interactive touch pad updates simulated screen preview live.

- [ ] **Step 3: Test accessibility with keyboard arrow navigation between tabs**

- [ ] **Step 4: Commit**
  ```bash
  git add index.html
  git commit -m "feat: add interactive controller mode sandbox"
  ```

---

### Task 7: High-Impact Download CTA & Minimalist Footer

**Files:**
- Modify: `index.html`

**Interfaces:**
- Produces: Closing download block with `id="download-app"` and technical footer.

- [ ] **Step 1: Implement closing download block**
  - Headline: "YOUR PHONE. YOUR COMPUTER. ONE SIMPLE CONNECTION."
  - High-visibility primary CTA with `id="download-app"` and `data-download="true"`.
  - Platform support tags (Windows, macOS, Linux, Android, iOS).

- [ ] **Step 2: Implement minimalist technical footer**
  - Status beacon "System Ready", copyright, back-to-top link, keyboard shortcut tips.

- [ ] **Step 3: Commit**
  ```bash
  git add index.html
  git commit -m "feat: add download CTA and technical footer"
  ```

---

### Task 8: Desktop Custom Cursor & Motion Engine

**Files:**
- Modify: `index.html`

**Interfaces:**
- Produces: Dual-element custom cursor with subtle red glow, 60fps canvas particle/streak trail, magnetic CTA attraction, and strict mobile/reduced-motion disablement.

- [ ] **Step 1: Implement custom cursor DOM elements and HTML5 canvas trail**
  - Inner dot + outer lerp ring.
  - Offscreen/overlay canvas rendering fading velocity streaks.
  - Magnetic pull on primary buttons.

- [ ] **Step 2: Add device & preference gating**
  - Completely disable cursor and canvas on `(hover: none)`, `(pointer: coarse)`, or width `< 768px`.
  - Respect `prefers-reduced-motion: reduce` by freezing trailing effects.

- [ ] **Step 3: Benchmark 60fps performance and verify no memory leaks**

- [ ] **Step 4: Commit**
  ```bash
  git add index.html
  git commit -m "feat: implement custom cursor and canvas trail motion engine"
  ```

---

### Task 9: Multi-Viewport Audit, Pre-Flight Check & Final Review

**Files:**
- Test: `index.html` across 375px, 768px, 1024px, 1440px using `browser_subagent`.

- [ ] **Step 1: Run browser subagent at 375px, 768px, 1024px, 1440px**
  - Verify zero horizontal overflow (`scrollWidth <= clientWidth`).
  - Verify touch nav works at 375px.
  - Verify hero fits viewport nicely and CTA is visible.

- [ ] **Step 2: Run Anti-AI Design Pre-Flight Check**
  - Verify 0 em-dashes (`—` or `–`).
  - Verify shape consistency, contrast ratios, and no generic purple gradients.
  - Check browser console for 0 warnings/errors.

- [ ] **Step 3: Final commit and summary report**
  ```bash
  git add index.html
  git commit -m "test: multi-viewport verification and anti-ai audit pass"
  ```
