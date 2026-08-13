# 🚀 Developer Handoff Blueprint: Minimal Disc Golf Pro (v1.2.0 Stable)

This document is the bridge between this agent session and your local Android development environment. Use this to orient your local Gemini agent when you move between machines.

---

## 🏗️ Project Overview
Minimal Disc Golf Pro is a zero-dependency, single-file HTML/CSS/JS application. We have wrapped it in a native Android shell using Capacitor.

*   **Root Entrypoint**: `index.html` (v1.2.0 Stable)
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
    *   The compiled installer `app-debug.apk` is generated in `android/app/build/outputs/apk/debug/`.

---

## 📱 Critical Workflow: Syncing to Android
Before compiling your native app, always propagate your HTML modifications into the native Androidassets directory:

```bash
npm run sync-android
```
*This command:*
*   Copies the latest `index.html` to `www/index.html`.
*   Runs `npx cap sync android` to sync those assets into the native `android/app/src/main/assets/public/` directory.

---

## ⚠️ Known Stability Lessons
*   **Status Bar Style**: We modified `android/app/src/main/res/values/styles.xml` to force a **pure black status bar** (`#000000`) with white icons in both dark and light modes.
*   **Stray Backslashes**: The JavaScript engine is extremely sensitive to trailing backslashes at the end of lines in the `<script>` block. Never add `\` at the end of lines.
*   **Storage Limits**: Raw images are stored in the `photos` object store in IndexedDB (`dg_pro_db`); course presets and round history are in their own respective stores. Do not fall back to `localStorage` for media.

---

## 🔮 Future Backlog (v1.2.1 / v1.3.0)
*   **Anonymize Secret Modal**: Remove names `betamark` and `zero` from the secret UFO modal credits (leaving CMaster, G Unit, and the Gemini CLI Agent).
*   **Obscure Easter Egg Button**: Relocate the UFO easter egg button to a more obscure, secret location in the app (rather than right next to the Help button in Settings).
*   **Multi-Round Storage Enhancements**: Support exporting individual older rounds from history as standalone `.dgpro` files directly from the Past Rounds card.
