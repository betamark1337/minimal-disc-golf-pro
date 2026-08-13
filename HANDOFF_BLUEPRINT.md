# 🚀 Developer Handoff Blueprint: Minimal Disc Golf Pro (v1.2.0)

This document is the bridge between this agent session and your local Android development environment. Use this to orient your local Gemini agent when you move to the Mac Mini.

---

## 🏗️ Project Overview
Minimal Disc Golf Pro is a zero-dependency, single-file HTML/CSS/JS application. We have wrapped it in a native Android shell using Capacitor.

*   **Root Entrypoint**: `index.html` (v1.2.0 stable)
*   **Release Vault**: `/releases/` (Immutable historical snapshots)
*   **Core Configuration**: `capacitor.config.json` (Currently configured for `webDir: "www"`)

---

## 🛠️ Critical Workflow: Syncing to Android
Before opening the project in Android Studio, your agent must sync the latest `index.html` into the Android project assets:

1.  **Ensure all files are current**: Verify `index.html` is the latest version.
2.  **Execute the sync**:
    ```bash
    npm run sync-android
    ```
    *This command:*
    *   Copies the latest `index.html` to `www/index.html`.
    *   Runs `npx cap sync android` to propagate these changes into the native `android/app/src/main/assets/public/` directory.

---

## 📱 Android Distribution (Alpha)
To generate the `.apk` for your alpha testers:

1.  **Open in Android Studio**: Open the `android/` folder in Android Studio.
2.  **Gradle Sync**: Allow the IDE to finish the initial Gradle sync (this may take a few minutes as it downloads the Android SDK tools).
3.  **Build APK**: 
    *   Navigate to **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
    *   The compiled `app-debug.apk` will be generated in `android/app/build/outputs/apk/debug/`.

---

## ⚠️ Known Stability Lessons
*   **Stray Backslashes**: The JavaScript engine is extremely sensitive to trailing backslashes at the end of lines in the `<script>` block. If you edit code manually, **never** add `\` at the end of lines.
*   **Storage Limits**: Do NOT revert to `localStorage` for images. We have fully migrated to **`IndexedDB`** (`dg_pro_db`). Raw images are stored in the `photos` object store; course presets and round history are in their own respective stores.
*   **JSON Resilience**: Always use the `safeParseItem()` helper function when accessing `localStorage` to avoid the "White Screen of Death" if data becomes corrupted.

---

## 📂 Version Tree Reference
* **v1.2.0 (Current)**: Master Storage (IndexedDB), Unified `.dgpro` transport, and Course/History logging.
* **v1.1.8**: Player-specific name color customization.
* **v1.1.7**: Layered graph lines and dynamic key re-ordering.
* **v1.1.6**: Deconflicted label stacking.
* **v1.1.5**: Always-on legend with "Names" toggle.
* **v1.1.4**: Decoupled graph labels/gridlines.
* **v1.1.3**: Roster management breakout.
* **v1.1.2**: Symmetric flairs and delete buttons.
* **v1.1.1**: UI refinements and configuration backup.
* **v1.1.0**: Master storage (IndexedDB).
* **v1.0.1**: Stability patch (try/catch).
* **v1.0.0**: Gold Master Archive.
