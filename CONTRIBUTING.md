# 🤝 Contributing Guidelines

Thanks for your interest in contributing a theme to DesktopWidget! This file explains the **directory structure**, **file requirements**, and **submission process** for themes.

> Before submitting, please read the [Theme Development Guide](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE_EN.md) to understand the canvas specs, layer order, and hand pivot requirements.

---

## Table of Contents

- [1. Prerequisites](#1-prerequisites)
- [2. Directory Structure](#2-directory-structure)
- [3. File Requirements](#3-file-requirements)
- [4. Naming Conventions](#4-naming-conventions)
- [5. Design Guidelines](#5-design-guidelines)
- [6. Submission Process](#6-submission-process)
- [7. Review Process](#7-review-process)
- [8. Updating the Theme Index](#8-updating-the-theme-index)
- [9. Testing Checklist](#9-testing-checklist)

---

## 1. Prerequisites

- DesktopWidget v1.5.5 or later (for local import testing)
- An image editor that supports PNG with RGBA transparency (e.g., Photoshop, GIMP, Krita, Aseprite)
- Read the [Theme Development Guide](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE_EN.md)

---

## 2. Directory Structure

Each theme is a folder under `themes/`, containing 2–5 PNG images:

```
themes/
└── Your Theme Name/
    ├── bg.png            ← required, 400×297
    ├── face.png          ← required, 400×297
    ├── Hour_Hand.png     ← optional, 400×297
    ├── Minute_Hand.png   ← optional, 400×297
    └── Second_Hand.png   ← optional, 400×297
```

### Rules

- The **folder name** is the theme's display name (shown in the dropdown). It can be in any language, including Chinese
- `bg.png` and `face.png` are **both required** — the theme is invalid without them
- Hand images are optional; if missing, the default theme's hands are used
- Do not commit non-PNG files (no `.svg`, `.psd`, `.xcf`, etc.)

---

## 3. File Requirements

| File | Required | Size | Format | Description |
|------|:--------:|------|--------|-------------|
| `bg.png` | ✅ | 400×297 | PNG (RGBA) | Background layer, tinted by user color |
| `face.png` | ✅ | 400×297 | PNG (RGBA) | Clock face, drawn as-is (not tinted) |
| `Hour_Hand.png` | ❌ | 400×297 | PNG (RGBA) | Hour hand, points up at 0°, pivot at (199,143) |
| `Minute_Hand.png` | ❌ | 400×297 | PNG (RGBA) | Minute hand, same specs |
| `Second_Hand.png` | ❌ | 400×297 | PNG (RGBA) | Second hand, same specs |

### Critical Specs

- **All images must be exactly 400×297 pixels**
- **Format must be PNG with RGBA** (transparency channel required)
- **Hand images**: in the unrotated state (0°), the hand must point **straight up** (12 o'clock)
- **Hand pivot**: the rotation axis must be at pixel **(199, 143)** inside the image
- Transparent areas must have alpha=0 (not white-filled)

---

## 4. Naming Conventions

| Item | Rule | Example |
|------|------|---------|
| Theme folder name | Any language, descriptive | `Neon Clock`, `简约时光`, `Sunset Glow` |
| Image filenames | Fixed English names, case-sensitive | `bg.png`, `face.png`, `Hour_Hand.png` |
| ZIP filename | `<theme_name>_v<version>.zip` | `Neon_Clock_v1.0.0.zip` |

> The folder name supports spaces and Unicode. For the ZIP filename, replace spaces with underscores.

---

## 5. Design Guidelines

### 5.1 Background (bg.png)

- This layer is **tinted** by the user's selected color via `SourceAtop` blend mode
- Use semi-transparent or neutral colors for best tinting results
- Transparent areas remain transparent after tinting
- Avoid pure white (#FFFFFF) or pure black (#000000) — they reduce tinting effectiveness

### 5.2 Clock Face (face.png)

- Drawn **as-is**, not affected by tint or opacity
- Suitable for: clock markings, numbers, decorative borders, center decorations
- This is where your theme's visual identity lives

### 5.3 Hands (Hour/Minute/Second)

- Each hand image is 400×297 with the hand shape drawn from the pivot (199,143) **upward**
- The rest of the canvas must be fully transparent
- At 0° rotation, the hand points to 12 o'clock
- The pivot point (199,143) in the image aligns with the canvas center (201,144)

### 5.4 Text Slot Areas

The program draws 8 text items on top of the images. **Avoid these areas** or ensure sufficient contrast:

| Slot | X | Y | W | H | Position |
|------|---|---|---|---|----------|
| 1 | 20 | 30 | 105 | 43 | Top-left |
| 2 | 20 | 86 | 85 | 43 | Left |
| 3 | 20 | 166 | 70 | 50 | Left |
| 4 | 20 | 235 | 88 | 50 | Bottom-left |
| 5 | 280 | 30 | 94 | 43 | Top-right |
| 6 | 314 | 86 | 71 | 43 | Right |
| 7 | 324 | 166 | 60 | 50 | Right |
| 8 | 273 | 238 | 97 | 43 | Bottom-right |

---

## 6. Submission Process

### 6.1 Fork & Clone

```bash
git clone https://github.com/<your-username>/DesktopWidget-Themes.git
cd DesktopWidget-Themes
```

### 6.2 Add Your Theme

1. Create a folder under `themes/` with your theme name
2. Add `bg.png` and `face.png` (required) plus any hand images (optional)
3. Package as ZIP: zip the folder so the ZIP contains a top-level folder
4. Import the ZIP into DesktopWidget and verify it displays correctly

### 6.3 Submit a PR

```bash
git checkout -b add-<theme-name>
git add themes/<theme-name>/
git commit -m "Add theme: <Theme Name>"
git push origin add-<theme-name>
```

Then open a Pull Request against this repository.

### 6.4 PR Description Template

```markdown
## Theme Info
- **Name**: xxx
- **Author**: xxx
- **Version**: 1.0.0

## Description
Briefly describe the theme's visual style and design concept.

## Files Included
- [x] bg.png
- [x] face.png
- [ ] Hour_Hand.png
- [ ] Minute_Hand.png
- [ ] Second_Hand.png

## Preview
(Screenshots or descriptions of how the theme looks)

## Test Results
- [ ] Imported successfully in DesktopWidget
- [ ] Background tinting works correctly
- [ ] Hands rotate correctly (if included)
- [ ] Text slots are readable
```

---

## 7. Review Process

```
PR submitted
  │
  ▼
① Check file structure: folder name, required files, image format
  │
  ▼
② Verify image specs: 400×297, RGBA, hand orientation/pivot
  │
  ▼
③ Visual review: aesthetics, text slot contrast, tinting behavior
  │
  ▼
④ Import test: import into DesktopWidget and verify display
  │
  ▼
✅ Approved → merge PR
  │
  ▼
⑤ Package ZIP and publish to GitHub Release
  │
  ▼
⑥ Update themes/index.json and the README theme catalog
```

### Review Notes

- Themes are **pure image assets** — there is no code, so there is no security risk
- Review focuses on **visual quality** and **technical correctness** (dimensions, format, hand orientation)
- Initial review typically within **2 business days**

---

## 8. Updating the Theme Index

When adding or updating a theme, also update `themes/index.json`:

```json
{
  "name": "Theme Name",
  "author": "Author",
  "version": "1.0.0",
  "preview_url": "themes/Theme Name/face.png",
  "download_url": "https://github.com/Cherish95279/DesktopWidget-Themes/releases/download/Theme_Name_v1.0.0/Theme_Name_v1.0.0.zip",
  "source_path": "themes/Theme Name"
}
```

> The `download_url` points to a GitHub Release asset and is filled in after the Release is published.

---

## 9. Testing Checklist

Confirm each item before submitting:

- [ ] `bg.png` and `face.png` are both present
- [ ] All images are exactly 400×297 pixels
- [ ] All images are PNG format with RGBA transparency
- [ ] Hand images point straight up (12 o'clock) at 0°
- [ ] Hand pivot is at pixel (199, 143) inside the image
- [ ] No non-PNG files included in the folder
- [ ] Text slot areas have sufficient contrast
- [ ] Packaged as ZIP and import-tested in DesktopWidget
- [ ] `themes/index.json` updated

---

> If you have questions, leave a comment on your PR or refer to the [Theme Development Guide](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE_EN.md).
