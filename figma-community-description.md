# Canvas Warp

## 中文

1.0.3 将 Figma → Photoshop 的单批上限提高到 2000 个图层。请同时更新 Figma 社区插件、本地中转程序和 Photoshop 插件；其他方向的原有限制及 256 MB 请求体上限保持不变。

Canvas Warp 让你在 Figma、Photoshop 和 Illustrator 之间传递素材，尽量保留可编辑的文字、矢量、编组和蒙版。复杂效果或无法兼容的图层会使用图片保底，具体差异会在接收详情中显示。

支持 Figma ↔ Photoshop、Figma ↔ Illustrator、Photoshop ↔ Illustrator 双向传输。Photoshop 与 Illustrator 之间可发送选中元素、当前画板或整个文档。也可将 Figma 或 Photoshop 的透明 PNG 发送到兼容的 FlowGPT Canvas。

首次使用需要安装 Canvas Warp 本地中转程序，以及你要连接的 Photoshop 或 Illustrator 插件。全部传输通过本机 localhost 完成，无需注册 Canvas Warp 账号，素材不会上传到 Canvas Warp 云端。

## 下载与安装

- [全部下载与最新版本](https://github.com/1iinii1/canvas-warp/releases/latest)
- [macOS 中转程序，Intel 与 Apple Silicon 通用](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-mac-universal.dmg)
- [Windows 中转程序，x64](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-win-x64.exe)
- [Photoshop 插件](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-Photoshop.ccx)
- [Illustrator 插件，CEP 开发版](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-Illustrator.zip)
- [安装说明](https://github.com/1iinii1/canvas-warp#安装)

安装中转程序并手动启动一次，再打开目标软件中的 Canvas Warp 面板。在 Figma 中选择内容，点击 Photoshop 或 Illustrator 即可发送；接收 Adobe 素材时，请保持 Figma 插件面板打开。

## 演示

完整演示时长 61.7 秒，在社区页面按原顺序分为 3 段展示，请依次观看。

[下载完整原视频](https://github.com/1iinii1/canvas-warp/releases/download/v1.0.2/Canvas-Warp-Demo.mp4)

## 使用要求

支持 macOS 12+ 或 Windows 10/11 x64、Photoshop 2024+、Illustrator 2023+。中转程序当前未配置系统发行签名；Illustrator 插件需要手动加载未签名 CEP 开发扩展。不同软件的字体、混合模式和复杂外观可能存在兼容差异。

[反馈问题与建议](https://github.com/1iinii1/canvas-warp/issues)

---

## English

Version 1.0.3 increases Figma → Photoshop transfers to 2,000 layers per batch. Update the Figma Community plugin, desktop companion, and Photoshop plugin together. Other directions retain their existing limits, and the request-size limit remains 256 MB.

Transfer assets between Figma, Photoshop, and Illustrator while preserving editable text, vectors, groups, and masks where supported. Complex effects or unsupported layers use image fallbacks, with compatibility details shown after import.

Transfer in both directions between Figma and Photoshop, Figma and Illustrator, and Photoshop and Illustrator. For Photoshop ↔ Illustrator, send a selection, the current artboard, or the entire document. You can also send transparent PNGs from Figma or Photoshop to a compatible FlowGPT Canvas.

Install the Canvas Warp desktop companion and the plugin for each Adobe app you want to connect. Transfers stay on your computer through localhost. No Canvas Warp account is required, and your assets are not uploaded to a Canvas Warp cloud service.

## Downloads and setup

- [All downloads and latest release](https://github.com/1iinii1/canvas-warp/releases/latest)
- [macOS companion, Intel and Apple Silicon](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-mac-universal.dmg)
- [Windows companion, x64](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-win-x64.exe)
- [Photoshop plugin](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-Photoshop.ccx)
- [Illustrator plugin, CEP development build](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-Illustrator.zip)
- [Installation guide](https://github.com/1iinii1/canvas-warp#安装)

Install and launch the companion once, then open Canvas Warp in the destination app. Select content in Figma and click Photoshop or Illustrator to send it. Keep the Figma plugin panel open to receive assets from Adobe apps.

## Demo

The complete demo is 61.7 seconds long and is shown on the Community page as three clips in their original order. Watch them sequentially.

[Download the complete original video](https://github.com/1iinii1/canvas-warp/releases/download/v1.0.2/Canvas-Warp-Demo.mp4)

## Requirements

Requires macOS 12+ or Windows 10/11 x64, Photoshop 2024+, and/or Illustrator 2023+. Companion installers are currently unsigned, and the Illustrator plugin requires manual loading as an unsigned CEP development extension. Fonts, blend modes, and complex appearances may differ between apps.

[Report an issue or suggest an improvement](https://github.com/1iinii1/canvas-warp/issues)
