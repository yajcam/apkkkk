# macQUERY Online — Android App

A lightweight Android wrapper app for **https://macquery-online-1.jimdosite.com**, styled to match
the site's look — dark charcoal background, gold "macQUERY" branding, elegant serif accents.

Features:
- Branded splash screen (logo + the Da Vinci quote from the homepage)
- Full-screen WebView of the site, with the "View" reviewer links opening inside the app
- Pull-to-refresh, slim gold loading bar, in-app back navigation
- Offline screen with a Retry button
- Custom gold "M" app icon (adaptive icon ready)

---

## ⚠️ Important — about the APK

This project is the **complete Android Studio source code**, ready to compile. Producing the actual
`.apk` file requires Android's official build tools (Android SDK + Gradle + Google's Maven
repository), which aren't available in this chat environment. The good news: you can get a real,
installable APK for **free in a few minutes** using either option below — no coding required.

---

## Option 1 — Build the APK for free with GitHub Actions (easiest)

1. Create a free account at [github.com](https://github.com) if you don't have one.
2. Create a new repository (e.g. `macquery-app`).
3. Upload **all files and folders** from this project to that repo, keeping the structure intact —
   including the hidden `.github` folder (this contains the build workflow).
   - Easiest way: on the repo page, use "Add file → Upload files" and drag the whole extracted
     folder in (GitHub supports dragging folders in the web UI on desktop browsers).
4. Go to the **Actions** tab of your repo. A workflow called **"Build APK"** will run
   automatically. If it doesn't, click on it and press **"Run workflow"**.
5. Wait ~2–4 minutes for the green checkmark ✅.
6. Open the finished run, scroll down to **Artifacts**, and download **`macquery-online-app`**
   (a zip containing `app-debug.apk`).
7. Send `app-debug.apk` to your Android phone (Google Drive, email, USB, etc.).
8. On your phone, tap the file. If asked, allow "Install unknown apps" for that app, then tap
   **Install**.

That's it — `macQUERY` will appear on your home screen with its own icon.

---

## Option 2 — Build locally with Android Studio

1. Install [Android Studio](https://developer.android.com/studio).
2. Open this folder via **File → Open**.
3. If you see a banner saying the Gradle wrapper is missing, click the **"Create Gradle wrapper"**
   fix it offers (or just let Gradle Sync run — Android Studio repairs this automatically).
4. Press **Run ▶** to install on a connected phone/emulator, or use
   **Build → Build App Bundle(s) / APK(s) → Build APK(s)**.
5. The output APK appears at `app/build/outputs/apk/debug/app-debug.apk`.

---

## Customizing

| What | Where |
|---|---|
| App name | `app/src/main/res/values/strings.xml` → `app_name` |
| Website URL | `app/src/main/res/values/strings.xml` → `site_url` |
| Colors / gold theme | `app/src/main/res/values/colors.xml` |
| Splash quote | `app/src/main/res/values/strings.xml` → `splash_quote`, `splash_author` |
| App icon | `app/src/main/res/mipmap-*/ic_launcher*.png` and `drawable/ic_launcher_foreground.png` |
| Logo (splash + toolbar) | `app/src/main/res/drawable/logo_macquery.png` |

---

## Notes

- The debug APK is signed with Android's default debug key — perfectly fine for installing on
  your own device or sharing with friends to sideload, but **Google Play requires a release build
  signed with your own keystore**.
- The app keeps all navigation (including the "View" links to the GitHub Pages reviewers) inside
  the WebView for an app-like feel, while `tel:`/`mailto:`/etc. links open in the appropriate
  external app.
