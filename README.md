# App-first Muse Number Two delivery

This archive is organized around the Android APK product described in the supplied specification. The primary project is `dual-muse-apk/`. The Android app opens the live Muse website at `https://muse.ai/` inside its WebView and includes the native wrapper, referral assets, favicon, CSS/JavaScript, promotional images, launcher resources, Gradle files, CI workflow, prompts, and testing notes.

The separate `token-town-site/` folder is included only as downstream promotional/checkout material. It is not the product app.

The package also includes a Windows Electron desktop launcher under `dual-muse-apk/desktop-electron/`; it likewise opens the live Muse website and requires an internet connection. External links from the Android WebView are handed off to the system browser or the appropriate system handler.

## GitHub Actions

The repository-root workflows locate the Android `gradlew` file and Electron `desktop-electron/package.json` dynamically after checkout. This supports either the archive root or `dual-muse-apk/` being used as the repository root. The workflows do not enable npm dependency caching, so they do not depend on a hard-coded lockfile path.
