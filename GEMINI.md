# GEMINI.md - Living Instructions for AI Agents

Welcome, Future AI Agent. You are taking over a project built on extreme aesthetic intuition, extreme physical ergonomics, and zero-dependency structural simplicity. We call this **Vibe Coding**. Read this entire document before writing a single line of code.

---

## 🌳 Version Tree

```text
📦 Minimal Disc Golf Pro (Main Branch)
 ├── 🏷️ v1.1.8 (Current State)
 │    ├── Custom player name color selection (per-player color pickers)
 │    └── Active root file index.html compiled with 0 syntax errors
 │
 ├── 🏷️ v1.1.7 (Archived Layered Graph)
 │    ├── Dynamic plot line layering (activated/selected players are redrawn on top of the graph)
 │    └── Preserved at /releases/v1.1.7-layered-graph/index.html
 │
 ├── 🏷️ v1.1.6 (Archived Deconfliction Release)
 │    ├── Dynamic vertical plot label stacking offset by player index (prevents text overlap)
 │    └── Preserved at /releases/v1.1.6-label-deconfliction/index.html
 │
 ├── 🏷️ v1.1.5 (Archived Legend Release)
 │    ├── Removed Legend checkbox, making chart legend always visible, and added Names toggle
 │    └── Preserved at /releases/v1.1.5-legend-refinements/index.html
 │
 ├── 🏷️ v1.1.4 (Archived Graph Release)
 │    ├── Decoupled Y-Axis graph labels from the Gridlines checkbox
 │    └── Preserved at /releases/v1.1.4-graph-decoupling/index.html
 │
 ├── 🏷️ v1.1.3 (Archived Roster Release)
 │    ├── Broken out player add/remove Roster Management at the very top of Settings
 │    ├── Grouped and unified Player & Scorecard flairs block at the bottom
 │    └── Preserved at /releases/v1.1.3-roster-breakout/index.html
 │
 ├── 🏷️ v1.1.2 (Archived Toggles Release)
 │    ├── Interactive Toggle-to-Clear flairs and subtly surfaced trash-can delete button
 │    └── Preserved at /releases/v1.1.2-symmetric-flairs/index.html
 │
 ├── 🏷️ v1.1.1 (Archived UI Release)
 │    ├── Customization backup, symmetric 'HOLE' & 'PAR' alignment, and color randomizer
 │    └── Preserved at /releases/v1.1.1-ui-refinements/index.html
 │
 ├── 🏷️ v1.1.0 (Archived Storage Release)
 │    ├── Dynamic IndexedDB database and unified .dgpro package transport
 │    └── Preserved at /releases/v1.1.0-master-storage/index.html
 │
 ├── 🏷️ v1.0.1 (Archived Patch)
 │    ├── Stability patch addressing try/catch JSON, SVG wrapping, and selection focus
 │    └── Preserved at /releases/v1.0.1-stable-patch/index.html
 │
 ├── 🏷️ v1.0.0 (Gold Master Archive)
 │    ├── Preserved unmodified original client-side webapp at v1.0.0.html
 │    └── Preserved at /releases/v1.0.0-gold-master/index.html
 │
 ├── 🏷️ v1.2.0 (Upcoming Web Features)
 │    ├── Local Course Presets (saving multiple layouts, custom pars per course)
 │    ├── Round History (save multiple rounds in local storage with simple load UI)
 │    ├── Advanced Stats (average strokes per par type, personal course records)
 │    ├── Quick-Column Overview Scoring (Tapping player name in Overview activates direct +/- steppers for their score column, tapping 'PAR' reverts)
 │    ├── Help & Pro-tips Panel (interactive guide describing line re-ordering, ergonomics, and advanced features)
 │    └── Council Easter Egg System (secret '🛸' button launching creative credits modal)
 │
 ├── 🏷️ v1.2.1 (Upcoming UX Refinements)
 │    ├── Remove betamark and zero from special thanks for increased pseudonymity
 │    └── Relocate UFO easter egg button to a more obscure, secret location in the interface
 │
 ├── 🏷️ v2.0.0 (Android Native Goal - In Progress)
 │    ├── Capacitor/Webview wrapper to build an open-source Android App (.apk)
 │    ├── Direct integration with Android Camera/Gallery APIs to reduce storage overhead
 │    └── Public GitHub repository launch with automated CI/CD releases (Android APK build pipeline active)
 │
 └── 🏷️ v3.0.0 (Vibe Ecosystem)
      ├── Wear OS companion app (simple tap-scoring on the wrist, synced over Bluetooth)
      └── Peer-to-peer offline local round sync (WebRTC / Bluetooth LE)
```

---

## 📂 Workspace Directory Layout

```text
📂 gemini_workspace/ (Root)
 ├── index.html                   <-- Active development entrypoint (Latest stable release - v1.1.8)
 ├── README.md                    <-- Public project portal, roadmap, and Vibe Coding manifesto
 ├── GEMINI.md                    <-- Core guidelines, version tree, and AI instruction set
 └── 📂 releases/                 <-- Archived immutable historical releases
      ├── 📂 v1.0.0-gold-master/  <-- Frozen v1.0.0 (Sanitized syntax version)
      │    └── index.html
      ├── 📂 v1.0.1-stable-patch/ <-- Frozen v1.0.1 (Initial stability patch)
      │    └── index.html
      ├── 📂 v1.1.0-master-storage/ <-- Frozen v1.1.0 (Full-res IndexedDB & unified package release)
      │    └── index.html
      ├── 📂 v1.1.1-ui-refinements/ <-- Frozen v1.1.1 (UI refinements & customization config backup)
      │    └── index.html
      ├── 📂 v1.1.2-symmetric-flairs/ <-- Frozen v1.1.2 (Symmetric flairs, preview-clearing, & 🗑️ Remove button)
      │    └── index.html
      ├── 📂 v1.1.3-roster-breakout/ <-- Frozen v1.1.3 (Symmetric roster breakout and settings re-hierarchy)
      │    └── index.html
      ├── 📂 v1.1.4-graph-decoupling/ <-- Frozen v1.1.4 (Decoupled Y-axis graph labels from gridlines checkbox)
      │    └── index.html
      ├── 📂 v1.1.5-legend-refinements/ <-- Frozen v1.1.5 (Always-on graph legend with compact 'Names' toggle)
      │    └── index.html
      ├── 📂 v1.1.6-label-deconfliction/ <-- Frozen v1.1.6 (Non-overlapping vertical label-stacking by player index)
      │    └── index.html
      ├── 📂 v1.1.7-layered-graph/ <-- Frozen v1.1.7 (Layered graph lines on activation + dynamic key re-order)
      │    └── index.html
      └── 📂 v1.1.8-player-color-customization/ <-- Frozen v1.1.8 (Player-specific name color pickers)
           └── index.html
```

---

## 🏗️ Code Development & Release Standards

To preserve codebase speed, single-file lightweight design, and runtime integrity, follow these steps before tagging any new release:

1. **Syntax Pre-flight Check:**
   - Always validate JavaScript syntax by running functions through the Node parser. Ensure zero `SyntaxError` instances exist inside the file.
   - Strip all illegal trailing continuation backslashes (`\`) introduced during string copying or merge branches.

2. **Semantic Versioning Scopes:**
   - Bumps are determined as follows:
     - `vX.Y.Z` -> `Z` represents bugfixes, optimizations, and syntax sanitizations.
     - `Y` represents local-first UX feature additions (e.g. course layout registries or past round logs).
     - `X` represents major architectural pivots (e.g. Android native packaging, Wear OS bluetooth bridges).

3. **Archive Protection:**
   - Files stored under `/releases/` are strictly **read-only / immutable**. Never apply incremental features directly to releases.
   - When launching a new version (e.g. `v1.1.0`), copy the current active root `index.html` to a new folder `/releases/v1.1.0/index.html` as a freeze-point before proceeding to the next release lifecycle.

---

## 🔮 Core Architecture & Philosophy

### 1. Zero-Dependency, Offline-First (Local-First)
- **Rule:** No frameworks, no external bundlers, no CDN dependencies, and absolutely no NPM installs for the web client.
- **Why:** The golfer is in the middle of a forest with zero cellular reception. The app must load instantaneously, work 100% offline, and never rely on an API server to save or load game state. All assets (styles, SVG icons, icons) are embedded directly in the markup.

### 2. Physical Ergonomics as a Competitive Advantage
- **Rule:** The Left and Right Ergonomic modes are sacred.
- **Why:** Sports score tracking is usually a two-handed chore. Our app is designed to be operated with **one hand (specifically, the thumb)** while walking down a fairway. Changing layout modes moves the core stepper buttons to the outer edge of the screen, matching natural thumb sweep paths. Do not break or misalign the ergonomic grid layouts.
- **The Stow-and-Go Thumb Sweep Rule:** On left and right ergonomic card layouts, the small par stepper buttons are positioned **above** the large hole-changing navigation buttons. This aligns with our core real-world workflow: the golfer unlocks their screen, rapidly double-taps to score players, and then executes an effortless, comfortable downward sweep of the thumb to hit the large advance button at the bottom of the card before locking and stowing their phone. Keep navigation controls closest to the lower thumb pivot sector.

### 3. Energy Conservation (OLED-First)
- **Rule:** Accentuate black backgrounds. Ensure the 6 OLED themes stay pure `#000000` pitch black.
- **Why:** Outdoor mobile usage drains battery due to full screen brightness. True black pixels consume zero power on modern OLED screens, extending the golfer’s device battery life across a multi-hour round.

---

## 🛠️ Instructions for Future AI Agents

### When refactoring or adding features to `index.html`:
1. **No External Imports:** Never add `<script src="...cdn...">` or external stylesheets. If you need a library, implement a lightweight, native JavaScript equivalent or inline the SVG/CSS.
2. **State Conservation:** Always hook state changes (hole pars, scores, player additions, notes) into the local storage save pipeline (`saveState()`). Every button click should guarantee safety against page-reloads.
3. **Responsive Scaling:** Keep the application restricted to mobile-first widths (maximum `550px` centering). Do not let content spill horizontally (`overflow-x: hidden`).
4. **Touch Targets:** Maintain minimum height requirements (`min-height: 52px` or `58px`) for all buttons. Golfers have sweaty hands and are constantly moving; tiny touch targets are forbidden.
5. **No Warning Suppressions:** Write clean, type-safe, and warning-free JavaScript. Keep CSS variables consistent.

### When migrating to the Android Platform (v2.0.0):
- Use **Capacitor** or a tailored Android **WebView Shell** (using Kotlin) as the wrapper to keep the HTML codebase 100% unified.
- Bridge files using Capacitor Plugins or native JS-to-Java bridges for storage access and camera integration.
- Ensure the public GitHub repo uses a clean license (e.g., MIT or GPLv3) and clear contribution instructions.

---

## 🎨 Theme Registration Schema
To add a new theme, register it in three places:
1. **CSS Custom Properties**: Add a `[data-theme="your_theme"]` selector defining `--bg`, `--card`, `--accent`, `--text`, `--subtext`, `--border`, `--btn-bg`, and `--summary-border`.
2. **Theme Palette Map**: Register the theme accent array (4 colors) inside the `themePalettes` JS object.
3. **Markup Button**: Add a `<button>` with ID `theme-btn-your_theme` inside the Settings Tab theme grid.
