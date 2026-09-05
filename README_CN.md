# 🎨 DesktopWidget-Themes

[![License](https://img.shields.io/badge/License-MIT-orange)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-blue)](https://github.com/Cherish95279/DesktopWidget)

DesktopWidget 官方**主题**共享仓库。这里收录社区创作的主题，用户可以下载 ZIP 包导入到 [DesktopWidget](https://github.com/Cherish95279/DesktopWidget) 桌面小组件中，自定义表盘外观。

> **适用版本**：DesktopWidget v1.5.0 及以上

<p align="center">
  <a href="README.md"><strong>🇺🇸 English</strong></a> |
  <a href="README_CN.md"><strong>🇨🇳 简体中文</strong></a>
</p>

---

## 📦 主题列表

| 主题 | 作者 | 预览 | 下载 |
|------|------|------|------|
| 赛博2077 | DesktopWidget | [预览](themes/赛博2077-test/face.png) | [ZIP](https://github.com/Cherish95279/DesktopWidget-Themes/releases/download/%E8%B5%9B%E5%8D%9A2077_v1.0.0/Cyber2077_v1.0.0.zip) |

> 标记 ✅ 的主题已通过审核。主题是 PNG 图片包，不包含代码，不存在安全风险。

---

## 📥 如何安装主题

1. 在上方表格中点击 **ZIP** 链接，下载主题压缩包
2. 启动 DesktopWidget，打开 **设置 → 主题**
3. 点击 **管理主题** 按钮
4. 在对话框上半部分点击 **浏览...**，选择下载的 ZIP 文件
5. 查看校验结果，点击 **导入**
6. 导入成功后，关闭对话框，在主题下拉框中选择该主题
7. 表盘即可显示新主题 ✅

> 也可以从 [Releases 页面](https://github.com/Cherish95279/DesktopWidget-Themes/releases) 下载所有主题包。

---

## 🛠️ 制作自己的主题

一个主题由 5 张 PNG 图片组成（400×297 像素）：

| 文件 | 必须 | 说明 |
|------|:----:|------|
| `bg.png` | ✅ | 背景层（受不透明度/着色影响） |
| `face.png` | ✅ | 表盘层（刻度、数字、装饰） |
| `Hour_Hand.png` | ❌ | 时针（指向 12 点，枢轴在像素 199,143） |
| `Minute_Hand.png` | ❌ | 分针 |
| `Second_Hand.png` | ❌ | 秒针 |

### 快速开始

1. 新建 400×297 RGBA 透明画布
2. 绘制 `bg.png`（背景，会被用户颜色着色）
3. 绘制 `face.png`（表盘刻度、装饰——不受着色影响）
4. 绘制三张指针图片（指向正上方 12 点，枢轴在像素 199,143）
5. 导出为 PNG（保留透明通道）
6. 打包为 ZIP（文件夹结构或扁平结构均可）

```
我的主题.zip
└── 我的主题/
    ├── bg.png
    ├── face.png
    ├── Hour_Hand.png
    ├── Minute_Hand.png
    └── Second_Hand.png
```

完整制作指南请参考：
- **中文**：[THEME_DEV_GUIDE.md](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE.md)
- **English**：[THEME_DEV_GUIDE_EN.md](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE_EN.md)

主题制作完成后，按照 [CONTRIBUTING.md](CONTRIBUTING_CN.md) 的规范提交 Pull Request。

---

## 📁 仓库结构

```
DesktopWidget-Themes/
├── README.md                       # 仓库说明
├── CONTRIBUTING.md                 # 提交规范
├── LICENSE
├── themes/                         # 主题源文件（PNG 图片）
│   ├── index.json                  # 主题索引（供 App 端浏览）
│   └── <主题名>/
│       ├── bg.png
│       ├── face.png
│       ├── Hour_Hand.png
│       ├── Minute_Hand.png
│       └── Second_Hand.png
└── releases/                       # 预打包 ZIP
    └── <主题名>_v<版本>.zip
```

---

## 🌐 相关链接

- **主项目**：[DesktopWidget](https://github.com/Cherish95279/DesktopWidget)
- **Microsoft Store**：[下载 DesktopWidget](https://apps.microsoft.com/detail/9P6GSZ8NNW52)
- **主题制作指南**：[中文](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE.md) / [English](https://github.com/Cherish95279/DesktopWidget/blob/main/docs/THEME_DEV_GUIDE_EN.md)
- **插件仓库**：[DesktopWidget-Plugins](https://github.com/Cherish95279/DesktopWidget-Plugins)

---

## 📄 许可证

本项目基于 [MIT License](LICENSE) 开源。提交到本仓库的主题默认采用相同许可证。
