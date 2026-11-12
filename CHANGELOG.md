# Changelog

All notable changes to Dev Browser lite are recorded here.

## 1.1-lite — 2026-11-12

### Added

- New launcher icon set built from the supplied artwork:
  - adaptive icon (Android 8+) with a gradient background and the glyph kept inside the safe zone
  - themed monochrome icon for Android 13+ themed icons
  - legacy squircle and round icons for mdpi, hdpi, xhdpi, xxhdpi and xxxhdpi
- Release assets: signed APK, icon preview and start-page preview
- `docs/DESIGN.md` describing the palette, typography and icon rules

### Changed

- Full theme redesign to match the icon: blue `#2b7cf6` to violet `#8b3dff` over ink `#060814`
- Start page rebuilt with glass cards, a grid backdrop, monospace toolkit labels and a developer badge
- Browser bar, editor panel, tabs, progress bar and buttons recoloured to the new palette
- `versionCode` 2, `versionName` 1.1-lite
- APK size 2.0 MB to 1.3 MB

### Fixed

- Status and navigation bars now match the app surface on all Android versions

## 1.0-lite — 2026-11-12

- First lite build: renamed from Dev Browser, versionName `1.0-lite`, signed with a dedicated release key
