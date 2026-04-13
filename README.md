# PathAnnotate

A lightweight, client-side gross pathology specimen annotation tool.

**Live:** [pathannotate.app](https://pathannotate.app)
**Repository:** [github.com/PathAnnotate/PathAnnotate](https://github.com/PathAnnotate/PathAnnotate)

---

## Support / Donations

If you find PathAnnotate useful, you can support the project:

<a href='https://ko-fi.com/T6T61V3JID' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://storage.ko-fi.com/cdn/kofi5.png?v=6' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>

`pathannotate@jjjp.ca`

---

## What It Does

PathAnnotate lets you annotate gross pathology photos directly in the browser — no server, no account, no installation. Draw rectangles over submitted tissue blocks, assign sequential block labels, add per-block notes, and copy the formatted block key directly into your dictation.

---

## Features

- Import gross pathology photos and annotate directly in the browser (or install as a PWA)
- Draw rectangles, lines, and block text label overlays
- Automatic block label sequencing — numeric specimens (e.g. `2 Left Kidney`) use A, B, C…; alpha specimens (e.g. `B Kidney`) use 1, 2, 3…
- Adjacent rectangles share a perfect edge (cassette model — no gap, no double border)
- Block labels snap to rectangle hotpoints and line endpoints in Anchor mode
- Line endpoint snapping while drawing — chain connected lines precisely
- Overlap clipping — the selected (front) rectangle's border is never obscured
- Custom colour picker alongside the preset colour swatches
- Anchor / Freeform label mode toggle accessible from the edit popup
- Per-annotation notes; copy the full block key to the clipboard in one click
- Specimen title displayed on the canvas and used as the export filename
- Save / load sessions as JSON; export annotated images
- Undo / redo with full state preservation (Ctrl+Z / Ctrl+Y)
- Light and dark themes
- First-run onboarding modal, shown once per version
- All data stays on your device — nothing is ever transmitted

---

## Workflow

1. Click **Import Photo** to load a gross specimen image (or drag and drop).
2. Click **Set Title** to enter a case number and specimen (e.g. `SP-26-99999` / `2 Left Kidney`).
3. Use the **Rectangle** tool to draw outlines over each submitted tissue block.
4. Click the letter button (⊞) on a rectangle to assign the next sequential block label.
5. Add notes in the **Block Key** panel, then click **Copy** to get the formatted key for your dictation.
6. Click **Export Photo** to save the annotated image.
7. Click **Save** to save the session as JSON for later.

---

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `R` | Rectangle tool |
| `E` | Line tool |
| `B` | Block label tool |
| `T` | Free text tool |
| `S` | Select / Move tool |
| Double-click | Edit label text |
| Right-click | Paste last annotation at cursor |
| `Del` | Delete selected object |
| `Ctrl+Z` / `Ctrl+Y` | Undo / Redo |
| `Ctrl+C` / `Ctrl+V` | Copy / Paste selected annotation |

---

## External Libraries

| Library | Version | License | Source |
|---------|---------|---------|--------|
| [Fabric.js](https://fabricjs.com) | 7.x | MIT | [cdn.jsdelivr.net](https://cdn.jsdelivr.net/npm/fabric@7/dist/index.min.js) |
| [DM Sans](https://fonts.google.com/specimen/DM+Sans) | — | OFL-1.1 | [fonts.google.com](https://fonts.google.com) |
| [DM Mono](https://fonts.google.com/specimen/DM+Mono) | — | OFL-1.1 | [fonts.google.com](https://fonts.google.com) |

---

## Privacy

This application runs entirely client-side. No information leaves your device.
Images, text, and other content remain in the browser's cache and are never sent externally.
No analytics, tracking, or telemetry of any kind is collected or transmitted.

---

## Changelog

### v2.0.0
- Custom colour picker (+ swatch) in the colour row
- Anchor / Freeform toggle moved into the double-click edit popup (padlock icons)
- Block label tool uses popup editor — consistent with labelled rectangles
- Block counter advances to max+1; intentional label skips no longer interrupted
- Overlap clipping: front rectangle always displays its full border over back rectangles
- Z-order persists after deselection (`lastElevatedRect` clip logic)
- Adjacent rectangles created with the + buttons share a single perfect edge (cassette model)
- Block labels snap to line endpoints with a magnetic pull zone
- Line drawing snaps the tip to nearby existing line endpoints
- Undo/redo: background no longer becomes selectable after undo; block anchor state preserved across undo/redo; undo snapshots no longer embed base64 images (reduced memory usage)
- First-run onboarding modal shown once per version

### v1.3.0
- Upgraded to Fabric.js v7 (async API, renamed classes, updated origin defaults)

### v1.2.0
- Added ⚠ warning to Block Key for detected missing or duplicate blocks

### v1.1.0
- Block text label inferred based on specimen title:
  - Numeric specimen (e.g. `2 Left Kidney`) → block label starts at `A`
  - Alpha specimen (e.g. `B Kidney`) → block label starts at `1`
- Annotation list and Block Key scroll to the latest added item
- Added version number display in UI header and status bar
- Added Privacy Policy
- Added README and external library attribution

### v1.0.0
- Initial release: gross pathology image annotation with Fabric.js canvas
- Rectangle, line, and block text label tools
- Title with case number and specimen
- Block key panel with per-block notes and clipboard copy
- Save/load JSON sessions and export annotated images
- Undo/redo, light/dark theme, drag-and-drop image import
