<div align="center">

<img src="https://github.com/sachintha82288-cpu/dev-browser-lite/releases/download/v1.1-lite/dev-browser-lite-icon.png" width="104" alt="Dev Browser lite">

# Dev Browser lite

**A lightweight WebView developer browser for Android — inspect, edit and reload the live web from your phone.**

[![Latest release](https://img.shields.io/github/v/release/sachintha82288-cpu/dev-browser-lite?label=release&color=2b7cf6)](../../releases)
[![Android](https://img.shields.io/badge/Android-7.0%2B-8b3dff)](https://developer.android.com)
[![APK](https://img.shields.io/badge/APK-1.3%20MB-4ea8ff)](../../releases)

<img src="https://github.com/sachintha82288-cpu/dev-browser-lite/releases/download/v1.1-lite/dev-browser-lite-home.png" width="320" alt="Home screen">

</div>

## Download

Grab the signed APK from the [**Releases**](../../releases) page:

| Version | File | Highlights |
| --- | --- | --- |
| **1.1-lite** | `DevBrowser-lite-v1.1.apk` | New launcher icon, redesigned theme |
| 1.0-lite | `DevBrowser-lite-v1.0.apk` | First lite build |

## Install

1. Download the APK on your phone.
2. Allow *Install unknown apps* for your browser or file manager when prompted.
3. Open the APK and install.

The APK is zip-aligned and signed with v1 + v2 + v3 schemes, so it installs on Android 7.0 and newer.

> This build keeps the package id `com.nightshade.devbrowser` but uses its own signing key, so Android will not install it over the original **Dev Browser**. Uninstall the old app first.

## Features

- **Live HTML rewrite** — pull the rendered document into the editor and push it back without leaving the page
- **Element picker** — tap any node on any site, edit its markup and hot-swap it in place
- **CSS injection** — rewrite stylesheets live, no reload and no cache fight
- **Persistent scripts** — stash JavaScript that re-runs on every page you load
- **Console mirror** — logs and uncaught errors land straight in the panel
- http(s) link handling, cleartext traffic allowed, large heap for heavy pages

## Design

The interface follows the launcher icon: a blue to violet gradient over a deep ink surface, glass panels, monospace labels and a subtle grid backdrop.

- Adaptive icon (Android 8+) with a gradient background and a glyph kept inside the safe zone
- Themed monochrome icon for Android 13+ themed icons
- Legacy squircle and round icons for older launchers
- Matching in-app theme across the status bar, navigation bar, browser bar, editor panel and start page

## Tech

| | |
| --- | --- |
| Package | `com.nightshade.devbrowser` |
| Version | 1.1-lite (versionCode 2) |
| Min / target SDK | 24 / 34 |
| Size | ~1.3 MB |
| Stack | Kotlin WebView shell, single `MainActivity`, `assets/home.html` start page |

## Build and sign

```bash
apktool d DevBrowser-lite-v1.1.apk -o apk          # decode
# ...edit resources and assets...
apktool b apk -o unsigned.apk                      # rebuild
zipalign -f -p 4 unsigned.apk aligned.apk          # align
apksigner sign --ks devbrowser-lite.jks \
  --ks-key-alias devbrowserlite \
  --out DevBrowser-lite-v1.1.apk aligned.apk       # sign
apksigner verify --print-certs DevBrowser-lite-v1.1.apk
```

Every update must be signed with the same `devbrowser-lite.jks`, otherwise Android refuses to install it over the previous version. The keystore is intentionally not in this repository.

## Credits

Built on the original Dev Browser base by **Night Shade Cyber Team** (SmokeBoy).

## License

Released for personal and educational use. Test it on sites you own or are authorised to test.
