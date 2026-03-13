# PathAnnotate

A lightweight, client-side pathology specimen annotation tool.

**Live:** [pathannotate.app](https://pathannotate.app)  
**Repository:** [github.com/PathAnnotate/PathAnnotate](https://github.com/PathAnnotate/PathAnnotate)  

---

## Support / Donations

If you find PathAnnotate useful, you can support the project:

[![Support PathAnnotate! 🥹](https://img.shields.io/badge/Support%20PathAnnotate!%20%F0%9F%A5%B9-grey?style=flat)](https://donate.stripe.com/eVqdRa7whfVJgiX34affy01)
[![Ongoing Support 🥰](https://img.shields.io/badge/Ongoing%20Support%20%F0%9F%A5%B0-informational?style=flat)](https://donate.stripe.com/7sYbJ217T38X1o3eMSffy00)

`pathannotate@jjjp.ca` 

---

## Features

- Import gross pathology photos and annotate directly in the browser (or install as web app!)
- Draw rectangles, lines, and block text label overlays
- Automatic block key generation with specimen prefix (e.g. `2A-`, `B1-`)
- Per-annotation notes; copy the full block key to the clipboard in one click to use in your gross description
- Specimen title displayed on the canvas and used as the export filename
- Save / load sessions as JSON; export annotated images
- Undo / redo (Ctrl+Z / Ctrl+Y)
- Light and dark themes
- All data stays on your device — nothing is ever transmitted

---

## Usage

| Key | Action |
|-----|--------|
| Ctrl+Z / Ctrl+Y | Undo / Redo |
| S | Select tool |
| R | Rectangle tool |
| B | Block text tool |
| E | Line tool |
| T | Text tool |
| Double-click | Edit Text |
| Right-click | Paste last annotation |
| Del | Delete selected |

**Workflow**

1. Click **Import Photo** to load a gross image.
2. Click **Set Title** to enter a case number and specimen (e.g. `2 Left Kidney`).
   The block text will be set to the correct format (`A`, `B`, `C`… for numeric specimens; `1`, `2`, `3`… for alpha specimens).
3. Use **Rectangle** or **Block Text** tools to annotate blocks.
4. Add notes in the **Block Key** panel, then click **Copy** to get the formatted for quick import into dictations.
5. Click **Export Photo** to save the annotated image.
6. Click **Save** to save the session as JSON for later.

---

## External Libraries

| Library | Version | License | Source |
|---------|---------|---------|--------|
| [Fabric.js](https://fabricjs.com) | 5.3.1 | MIT | [cdnjs.cloudflare.com](https://cdnjs.cloudflare.com/ajax/libs/fabric.js/5.3.1/fabric.min.js) |
| [DM Sans](https://fonts.google.com/specimen/DM+Sans) | — | OFL-1.1 | [fonts.google.com](https://fonts.google.com) |
| [DM Mono](https://fonts.google.com/specimen/DM+Mono) | — | OFL-1.1 | [fonts.google.com](https://fonts.google.com) |

---

## Privacy

This application runs entirely client-side. No information leaves your device.  
Images, text, and other content remain in the browser's cache and are never sent externally.  
No analytics, tracking, or telemetry of any kind is collected or transmitted.

---

## Changelog

### v1.2.0
- Added ⚠ warning to 'Block Key' for detected missing or duplicate blocks

### v1.1.0
- Block text label inferred based on specimen title:
  - Numeric specimen (e.g. `2 Left Kidney`) → block label starts at `A`
  - Alpha specimen (e.g. `B Kidney`) → block label starts at `1`
- Annotation list and Block Key scroll to the latest added item
- Added version number display in UI header and statusbar
- Added Privacy Policy
- Added README and external library attribution

### v1.0.0
- Initial release: gross pathology image annotation with Fabric.js canvas
- Rectangle, line, and block text label tools
- Title with case number and specimen
- Block key panel with per-block notes and clipboard copy
- Save/load JSON sessions and export annotated images
- Undo/redo, light/dark theme, drag-and-drop image import
