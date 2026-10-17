# HiAnime TV (Android Studio project)

This is a starter Android TV WebView wrapper for `https://hianime.de.com/`.

## Features
- Android TV launcher entry and landscape layout
- Desktop Chrome-style user agent
- JavaScript, DOM storage, cookies and hardware acceleration
- HTML5 fullscreen callback handling
- Basic hard-coded ad/tracker host filtering
- TV remote key events passed to the page/player

## Important limitations
- This project is source code, **not a compiled or TV-tested APK**.
- Desktop user-agent spoofing does not guarantee playback. The site may use unsupported codecs, DRM, browser checks, changing stream hosts, or anti-bot checks.
- The basic host list is not a full ad blocker. Blocking can also break site functions; adjust `blockedHosts` in `MainActivity.kt` if needed.
- It does not extract stream URLs or bypass DRM/paywalls/access controls. If the site needs a separate native HLS/DASH player, this starter needs further development and testing.
- Use only content you are authorized to access, and check the site's terms.

## Build an APK
1. Install Android Studio (current stable) with Android SDK Platform 35.
2. Open this folder as a project.
3. Let Gradle sync.
4. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. The debug APK will be under `app/build/outputs/apk/debug/app-debug.apk`.
6. Install it on an Android TV/TV box. You may need to allow installation from the file-transfer app.

## Test
Try a title on the TV and note whether the page loads, whether the video starts, and whether fullscreen works. If video still fails, send the TV/box model, Android version, and a photo of the error/player screen. The next step may be native Media3/ExoPlayer support for compatible non-DRM streams.

## Build on GitHub without Android Studio
1. Create a new repository on GitHub (a public repo is easiest for initial setup; don't upload secrets).
2. Upload all files/folders from this ZIP, including the hidden `.github` folder, to the repository's `main` branch.
3. Open the repository's **Actions** tab and select **Build HiAnime TV APK**.
4. Click **Run workflow** if it is not already running from the push.
5. When the run finishes with a green check, open the run and download the `HiAnimeTV-debug-apk` artifact.
6. Extract the downloaded artifact ZIP to get `app-debug.apk`.

GitHub Actions uses a cloud runner to compile the project; no local Android Studio is required. The workflow builds a debug APK, not a Play Store release.
