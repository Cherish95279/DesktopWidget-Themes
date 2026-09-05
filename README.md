# 🎨 DesktopWidget-Themes

[![License](https://img.shields.io/badge/License-MIT-orange)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-blue)](https://github.com/Cherish95279/DesktopWidget)

The official **theme** repository for DesktopWidget. This repo hosts community-created themes that users can download as ZIP packages and import into the [DesktopWidget](https://github.com/Cherish95279/DesktopWidget) desktop widget to customize its appearance.

> **Requires**: DesktopWidget v1.5.5 or later

<p align="center">
  <a href="README.md"><strong>🇺🇸 English</strong></a> |
  <a href="README_CN.md"><strong>🇨🇳 简体中文</strong></a>
</p>

---

## 📦 Theme Catalog

| Theme | Author | Preview | Download |
|-------|--------|---------|----------|
| 赛博2077 | DesktopWidget | [Preview](themes/赛博2077-test/face.png) | [ZIP](https://github.com/Cherish95279/DesktopWidget-Themes/releases/download/%E8%B5%9B%E5%8D%9A2077_v1.0.0/Cyber2077_v1.0.0.zip) |

> Marked ✅ themes have passed review. Themes are PNG image packs — no code, so there is no security risk.

---

## 📥 How to Install a Theme

1. Click the **ZIP** link in the table above to download the theme package
2. Launch DesktopWidget and open **Settings → Themes**
3. Click the **Manage Themes** button
4. In the upper half of the dialog, click **Browse...** and select the downloaded ZIP file
5. Review the validation result, then click **Import**
6. After a successful import, close the dialog and select the theme from the theme dropdown
7. The widget now displays the new theme ✅

> You can also download all theme versions from the [Releases page](https://github.com/Cherish95279/DesktopWidget-Themes/releases).

---

## 🛠️ Create Your Own Theme

A theme is a set of 5 PNG images (400×297 pixels):

| File | Required | Description |
|------|:--------:|-------------|
| `bg.png` | ✅ | Background layer (affected by opacity/tint) |
| `face.png` | ✅ | Clock face layer (markings, numbers, decorations) |
| `Hour_Hand.png` | ❌ | Hour hand (points to 12 o'clock, pivot at pixel 199,143) |
| `Minute_Hand.png` | ❌ | Minute hand |
| `Second_Hand.png` | ❌ | Second hand |

### Quick Start

1. Create a 400×297 RGBA transparent canvas
2. Draw `bg.png` (background, will be tinted by user color)
3. Draw `face.png` (clock markings, decorations — not tinted)
4. Draw the three hand images (pointing up at 12 o'clock, pivot at pixel 199,143)
5. Export as PNG (preserve transparency)
6. Package as ZIP (folder structure or flat)

```
My Theme.zip
└── My Theme/
    ├── bg.png
    ├── face.png
    ├── Hour_Hand.png
    ├── Minute_Hand.png
    └── Second_Hand.png
```

For the complete guide, see:
- **English**: [THEME_DEV_GUIDE_EN.md](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE_EN.md)
- **中文**: [THEME_DEV_GUIDE.md](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE.md)

Once your theme is ready, follow [CONTRIBUTING.md](CONTRIBUTING.md) to submit a Pull Request.

---

## 📁 Repository Structure

```
DesktopWidget-Themes/
├── README.md                       # this file
├── CONTRIBUTING.md                 # submission guidelines
├── LICENSE
├── themes/                         # theme source files (PNG images)
│   ├── index.json                  # theme index (for in-app browsing)
│   └── <theme_name>/
│       ├── bg.png
│       ├── face.png
│       ├── Hour_Hand.png
│       ├── Minute_Hand.png
│       └── Second_Hand.png
└── releases/                       # pre-packaged ZIPs
    └── <theme_name>_v<version>.zip
```

---

## 🌐 Related Links

- **Main project**: [DesktopWidget](https://github.com/Cherish95279/DesktopWidget)
- **Microsoft Store**: [Get DesktopWidget](https://apps.microsoft.com/detail/9P6GSZ8NNW52)
- **Theme dev guide**: [English](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE_EN.md) / [中文](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE.md)
- **Plugin repository**: [DesktopWidget-Plugins](https://github.com/Cherish95279/DesktopWidget-Plugins)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE). Themes submitted to this repository default to the same license.
