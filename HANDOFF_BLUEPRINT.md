# 🚀 Developer Handoff Blueprint: Minimal Disc Golf Pro (v1.2.1 Stable Alpha)

This document is the bridge between this agent session and your local Android development environment. Use this to orient your local Gemini agent when you move between machines.

---

## 🏗️ Project Overview
Minimal Disc Golf Pro is a zero-dependency, single-file HTML/CSS/JS application. We have wrapped it in a native Android shell using Capacitor.

*   **Root Entrypoint**: `index.html` (v1.2.1 Stable Alpha)
*   **Release Vault**: `/releases/` (Immutable historical snapshots)
*   **Core Configuration**: `capacitor.config.json` (Configured for `webDir: "www"`)
*   **Remote Repository**: [github.com/betamark1337/minimal-disc-golf-pro](https://github.com/betamark1337/minimal-disc-golf-pro) (Anonymously hosted under pseudonym `betamark1337`)

---

## 🛠️ Environmental Setup & Compilation
We have resolved local machine compatibility obstacles. Future builds should follow this verified recipe:

1.  **Android SDK Path**: Verified and locked in `android/local.properties` pointing to:
    ```properties
    sdk.dir=/Users/zero/Library/Android/sdk
    ```
2.  **Java/JDK Compilation Requirement**: 
    *   Gradle 8.14.3 requires **OpenJDK 21** for compiling this project. Older JDKs (like 17) or newer ones (like 25) will cause compilation errors.
    *   To build from the CLI:
        ```bash
        JAVA_HOME=/usr/local/opt/openjdk@21 ./gradlew assembleDebug
        ```
    *   The compiled installer `app-debug.apk` is generated in `android/app/build/outputs/apk/debug/app-debug.apk`.

---

## 📱 Critical Workflow: Syncing to Android
Before compiling your native app, always propagate your HTML modifications into the native Android assets directory:

```bash
npm run sync-android
```
*This command:*
*   Copies the latest `index.html` to `www/index.html`.
*   Runs `npx cap sync android` to sync those assets into the native `android/app/src/main/assets/public/` directory.

---

## ⚠️ Core Lessons & Technical Stability
*   **Desktop-to-Mobile Swipe Emulation**: When building touch swipe triggers (`touchstart`/`touchend`), mouse drags (`mousedown`/`mouseup`) must be emulated simultaneously. This ensures that horizontal swiping works perfectly in both desktop browsers (click-and-drag testing) and native mobile touch viewports. Always implement an interactive exclusion check (e.g. `isInteractiveElement`) so swiping doesn't conflict with text inputs, sliders, canvas graphs, or custom buttons.
*   **Ergonomic Reparenting (DOM Order Manipulation)**: To support left-to-right single-row layout mirroring under ergonomic hand modes, use CSS Flexbox `order` attributes inside JS. This avoids complex DOM node removal and reparenting, maintaining robust input bindings.
*   **Stray Backslashes**: The JavaScript engine is extremely sensitive to trailing backslashes at the end of lines in the `<script>` block. Never add `\` at the end of lines, especially during copy-paste operations.
*   **Storage Architecture**: High-resolution images must be saved into IndexedDB (`dg_pro_db` ➔ `photos` store) as Base64. Do not store images in `localStorage`, which is capped at 5MB and prone to quiet storage exhaustion.

---

## 💡 Improvement & Design Guidance
*   **OLED-First Layouts**: Keep backgrounds pure pitch black (`#000000`) for the 6 OLED themes. Outdoor high-brightness play drains mobile batteries extremely quickly; pitch-black pixels consume zero power, saving battery life.
*   **Compact UI Select Labels**: On narrow portrait mobile devices, horizontal screen space is a precious commodity. Keep default `<option>` labels short (e.g., use `"Load"` instead of `"Load Saved Preset..."`) to prevent browsers from clipping text into ugly `"Load Sav"` wrappers.
*   **Declarative Orientation Styling**: For landscape viewports on mobile, favor declarative CSS media queries (e.g., `@media (orientation: landscape) and (max-height: 550px)`) to scale down containers (like the relative SVG graph down to `180px` height) rather than complex JS resize listeners. It is faster, transitions smoothly, and has zero CPU overhead.

---

## 🔮 Suggested Future Features (Roadmap Reminder)
*   **Advanced Stats & Course Records**: Add an advanced reporting screen calculating average strokes per par type (averages on Par 3s, Par 4s, Par 5s) and personal layout records over time.
*   **Alternate Layout Duplication**: Build on top of the layout duplicating feature (`duplicateCoursePreset`) to support alternate tee layouts (e.g., "Chippewa Banks - Longs" duplicated from "Chippewa Banks - Shorts" for minor par edits).
*   **Wear OS Scoring Companion**: Create a smartwatch companion interface allowing basic offline scoring adjustments on the wrist, synchronizing via a local Bluetooth bridge.
*   **P2P Offline Local Sync**: Exchange live scorecard data with adjacent cards on the course using local WebRTC or Bluetooth LE—completely bypassing cellular carrier networks.
