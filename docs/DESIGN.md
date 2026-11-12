# Design system — Dev Browser lite

Everything in the app follows the launcher icon: a blue to violet gradient over a
deep ink surface, white glyph artwork and monospace labels.

## Palette

| Token | Hex | Used for |
| --- | --- | --- |
| Ink | `#060814` | App background, navigation bar, editor surface |
| Deep | `#0b1024` | Card and panel base |
| Blue | `#2b7cf6` | Primary accent, gradient start |
| Blue soft | `#4ea8ff` | Focus rings, eyebrow labels, links |
| Violet | `#8b3dff` | Gradient end, selected states |
| Violet soft | `#9b5cff` | Progress bar end |
| Text | `#f4f7ff` | Body copy |
| Text dim | `#98a3c4` | Secondary copy |
| Line | `rgba(143,180,255,.18)` | Card borders, dividers |

Signature gradient: `linear-gradient(96deg, #4ea8ff, #a9c4ff 48%, #9b5cff)`.

## Typography

- UI and body: system sans stack (Roboto on Android)
- Labels, tabs, version strings, code: monospace
- Eyebrow labels: 10 px, uppercase, 0.22 em tracking
- Headings: 700–800 weight, tight tracking, never all caps

## Shape and depth

- Corner radius: 20 dp for cards, 14 dp for controls, 12 dp for tabs, 999 dp for pills
- Elevation is expressed with a soft outer shadow plus a 1 px inner highlight, never a hard border
- Panels are translucent and blurred so the gradient backdrop shows through

## Icon construction

- Source artwork is cropped to the tile, then exported at 48/72/96/144/192 px for legacy launchers
- Adaptive icon: 108 dp canvas, glyph scaled to 60 % and centred so it stays inside the 66 dp safe zone
- Foreground glyph is extracted from the artwork by luminance and de-saturation, so it stays crisp on the gradient background
- Monochrome layer reuses the same glyph as a white silhouette for Android 13+ themed icons
- Legacy round icon uses a circular mask, legacy square icon a 22.5 % rounded mask

## Motion

- Entrance: 12 px rise, 0.65–0.9 s, `cubic-bezier(.22,.9,.24,1)`
- Press feedback: 0.975 scale on buttons and chips
- No looping decorative animation on the start page
