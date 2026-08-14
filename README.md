# 🥏 Minimal Disc Golf Pro

> The ultimate vibe-coded, offline-first, one-handed disc golf scorecard. 

Minimal Disc Golf Pro is a high-speed, zero-dependency, ultra-lightweight scorecard application. Designed specifically for outdoor play in areas with poor cellular coverage, it provides beautiful performance charts, ergonomic single-handed controls, and absolute data privacy.

---

## ⚡ Development & Technical Approach

This application is built using a collaborative human-AI development approach (often referred to as **Vibe Coding**) leveraging automated AI code generation (via Gemini CLI agents) under the close guidance and functional testing of the project owner.

### Key Technical Aspects:
- **AI-Assisted Assembly:** The codebase was generated, restructured, and expanded by AI-powered developer agents responding to iterative human feedback and on-course requirements.
- **Not Fully Human-Audited:** Because much of the logic, layout calculations, and styling adjustments were written automatically, not all code paths have been manually audited by a human software engineer. Use the application on-course with the understanding that local database schemas and complex edge cases are generated programmatically.
- **Zero-Dependency, Single-File Architecture:** The entire web frontend consists of a single `index.html` file combining all DOM structures, layout styling (Vanilla CSS), and offline runtime logic (Vanilla JS). This completely eliminates dependency rot, NPM build steps, or CDN latency, ensuring total offline reliability.
- **Native Android Bridging:** Leverages **Capacitor** to wrap the single-file web client inside a native Android WebView container, allowing simple `.apk` packaging without native Java/Kotlin rewrites.

---

## 📊 Current Progress Analysis (v1.0.0)

We have successfully audited the codebase and established the **v1.0.0 baseline**. Here is where we stand:

### Core Principles
1. **Offline-First Sovereignty:** The app relies strictly on the web standard `localStorage` API. No server-side databases. No cellular data required.
2. **Physical Thumb Ergonomics:** Scorekeepers usually have a disc in one hand, a bag on their shoulder, and a phone in the other. We relocate primary navigation and score adjusters to match your thumb’s sweep arc.
3. **Power-Efficient Outdoors:** We feature 17 custom-designed themes, with **6 specialized OLED themes** (pure `#000000` pitch black) that shut down pixels on modern mobile displays to preserve critical battery life under direct sunlight.

### What MDG Pro Offers That Others Don't
* **True Left & Right-Hand Ergonomics:** Standard scorecards force you to reach across large screens. MDG Pro shifts the score adjustment cluster dynamically.
* **SVG Interactive Performance Engine:** We draw relative (`+/-` from par) and cumulative charts inside a responsive SVG canvas using zero external charting libraries. Players can be clicked in the legend to toggle their lines.
* **Local Media Attachments:** Golfers can type weather/round notes and upload photos directly into their scorecard, stored locally as compact Base64 strings.
* **Double Import/Export Portability:** Supports both structural JSON exports (for backups) and flat CSV exports (perfect for importing into Excel/Sheets to run personal statistics).

---

## 🗺️ Feature Roadmap

Here is our proposed development roadmap. We invite you to review, alter, and approve these plans:

* [x] **IndexedDB Master Storage (v1.1.0):** Native zero-dependency browser database storing 100% full-resolution, uncompressed photos with zero quality loss.
* [x] **Unified .dgpro Package System (v1.1.0):** Unify JSON, CSV, and master packages under a single prominent file processor and 2x2 settings action grid.
* [x] **Local Course Catalog (v1.2.0):** Create and save multiple course layouts (e.g., "Chippewa Banks - Longs" vs "Shorts") with custom pars per layout so you don't have to redefine them.
* [x] **Multi-Round Logging (v1.2.0):** Support saving and loading past rounds locally. Introduce a simple "Past Rounds" history shelf on the Settings tab.
* [x] **Fairway Stats Dashboard (v1.2.0):** Track metrics like *Birdie Rate*, *Scrambling %*, and *Par-3 Scoring Averages* directly inside the Overview panel.
* [x] **Quick-Column Overview Scoring (v1.2.0):** Tapping a player's name in the Overview panel activates direct +/- stepper buttons for their score column, letting you adjust recorded scores easily. Only one column is adjustable at a time. Tap 'PAR' to go back to editing par values.
* [x] **Help & Pro-tips Panel (v1.2.0):** Added a beautiful, integrated user guide describing advanced features, including line re-ordering, thumb ergonomics, and upcoming column-focused scoring.
* [x] **Council Easter Egg System (v1.2.0):** Embedded a hidden, flying-saucer (`🛸`) button inside Settings that launches a celebratory "Thank You" transmission.

### 🟡 Phase 2: Open-Source Android App (v2.0.0)
* [ ] **WebView Native Shell:** Package the client using Capacitor or a lightweight native Android WebView wrapper to generate a lightweight, lightning-fast `.apk` installable on any Android device.
* [ ] **Public GitHub Release:** Publish the source code to a public GitHub repository. Set up automated GitHub Actions to compile and attach the Android build (`MinimalDiscGolfPro.apk`) to every Git release.
* [ ] **Native Hardware Bridges:**
  * Connect the HTML Camera button directly to the Android Camera API to compress, optimize, and save disc golf photos to the local app directory instead of bloating `localStorage`.
  * Support file-system exports to the native Android Downloads folder with one-click sharing hooks.

### 🔵 Phase 3: The Connected Vibe (v3.0.0)
* [ ] **Wear OS Scoring Companion:** A minimal Bluetooth scoring interface for smartwatches, allowing the phone to stay in the bag while you log throws directly from your wrist.
* [ ] **P2P Offline Round Sync:** Share live scoring with cards nearby using WebRTC or local Bluetooth LE—completely bypassing the need for cellular data.

---

## 📂 Repository Subfolder Structure

To preserve developer ease and keep release histories perfectly separated, our workspace is structured as follows:
* **`index.html`** (Root): The active development entrypoint. ALWAYS reflects the latest stable version (currently v1.1.8).
* **`releases/`**: Subfolder containing read-only, immutable historical builds (e.g. `/releases/v1.0.0-gold-master/`, `/releases/v1.0.1-stable-patch/`, `/releases/v1.1.0-master-storage/`, `/releases/v1.1.1-ui-refinements/`, `/releases/v1.1.2-symmetric-flairs/`, `/releases/v1.1.3-roster-breakout/`, `/releases/v1.1.4-graph-decoupling/`, `/releases/v1.1.5-legend-refinements/`, `/releases/v1.1.6-label-deconfliction/`, and `/releases/v1.1.7-layered-graph/`, and `/releases/v1.1.8-player-color-customization/`).
* **`GEMINI.md`**: Core system-wide standard rulebook and instructions for future AI developer agents.

---

## 📲 Android Alpha Testing (Use at Own Risk)

An installable Android package is available for pre-release testing!

### ⚠️ Disclaimer
> **This is a pre-release Alpha version under active development.** Local database corruption or unexpected round score crashes may occur. Use on the course at your own risk!

### How to Install:
1. Navigate to the **Releases** section on the right side of this GitHub repository.
2. Download the `app-debug.apk` file directly to your Android device.
3. Locate and open the downloaded APK file. Your device will prompt you to **"Allow installation from unknown sources"** (since the application is side-loaded and not yet registered on the Google Play Store).
4. Approve the prompt, tap install, launch the app, and start vibe-scoring!

---

## 🚀 Future Development Hand-off
To hand off development to future AI agents or other developers, we have established `./GEMINI.md` as our living rulebook. It specifies:
1. Our zero-dependency, single-file architectural boundaries.
2. The strict left/right physical ergonomic layout rules.
3. Theme registration schemas to easily expand visual accents.
