# Canvas Warp 1.0.3

## 中文更新说明

Figma → Photoshop 的单批图层上限从 200 提高到 2000，发送端、本地中转程序和 Photoshop 接收端同步支持。

### 更新内容

- 单批最多发送 2000 个实际导出图层，递归子图层和补出的背景图层计入数量。
- 本次仅提高 Figma → Photoshop 的上限。其他传输方向保持原有限制：Illustrator 相关导出与 Photoshop → Illustrator 仍为 2000，Figma → Illustrator、Figma → FlowGPT 及其他原为 200 的方向仍为 200。
- 单次请求体上限仍为 256 MB。图层数量符合要求时，大量图片或 PNG 保底仍可能先达到体积上限。

### 更新方式

请同时更新 **Figma 社区插件、Canvas Warp 本地中转程序、Photoshop 插件**。只更新其中一端，超过 200 层的任务仍可能被旧版拦截。保存文档后重启中转程序与 Photoshop，关闭并重新打开 Figma 插件，再发送内容。

- [全部下载与最新版本](https://github.com/1iinii1/canvas-warp/releases/latest)
- [Figma 社区插件](https://www.figma.com/community/plugin/1689327694454521056/canvas-warp)
- [安装说明](https://github.com/1iinii1/canvas-warp#安装)

### 验证与兼容性

**812 项完整自动测试全部通过，0 失败、0 跳过；源码语法检查通过。** 测试覆盖图层数量边界和其他方向限制保持不变。尚未进行 2000 层文档在 Figma 与 Photoshop 宿主中的实际收发验证；实际导入耗时与资源占用取决于文档复杂度。

文字、矢量和蒙版沿用既有兼容策略。macOS 中转程序尚未配置 Apple Developer ID 公证，Windows 尚未配置 Authenticode 签名；Illustrator 插件仍为需手动加载的 CEP 开发扩展。

### 操作演示

沿用 1.0.2 的完整操作演示（61.7 秒），社区页面按原顺序分为 3 段展示。

[观看或下载完整演示视频](https://github.com/1iinii1/canvas-warp/releases/download/v1.0.2/Canvas-Warp-Demo.mp4)

---

## English release notes

The per-transfer limit for Figma → Photoshop increases from 200 to 2,000 layers, with support in the Figma exporter, desktop companion, and Photoshop receiver.

### Changes

- Send up to 2,000 exported layers per transfer. Nested child layers and generated background layers count toward the limit.
- This change applies only to Figma → Photoshop. Other directions retain their existing limits: Illustrator exports and Photoshop → Illustrator remain at 2,000; Figma → Illustrator, Figma → FlowGPT, and other directions previously limited to 200 remain at 200.
- The request-size limit remains 256 MB. Image-heavy transfers and PNG fallbacks may reach the size limit before reaching the layer limit.

### Updating

Update all three components: **the Figma Community plugin, the Canvas Warp desktop companion, and the Photoshop plugin**. Updating only one component can leave older components rejecting transfers above 200 layers. Save your documents, restart the companion and Photoshop, reopen the Figma plugin, and resend your content.

- [All downloads and latest release](https://github.com/1iinii1/canvas-warp/releases/latest)
- [Figma Community plugin](https://www.figma.com/community/plugin/1689327694454521056/canvas-warp)
- [Installation guide](https://github.com/1iinii1/canvas-warp#安装)

### Validation and compatibility

**All 812 automated tests passed, with 0 failures and 0 skipped; runtime syntax checks passed.** Coverage includes layer-count boundaries and unchanged limits for other directions. A 2,000-layer transfer has not yet been tested in the actual Figma and Photoshop hosts. Import time and resource usage depend on document complexity.

Existing compatibility behavior for text, vectors, and masks is retained. The macOS companion is not Apple Developer ID notarized, and the Windows installer is not Authenticode signed. The Illustrator plugin remains a CEP development extension requiring manual loading.

### Demo

The complete 1.0.2 workflow demo is retained (61.7 seconds). The Community page shows it as three clips in their original order.

[Watch or download the complete demo](https://github.com/1iinii1/canvas-warp/releases/download/v1.0.2/Canvas-Warp-Demo.mp4)

# Canvas Warp 1.0.2

## 中文更新说明

新增 Photoshop ↔ Illustrator 双向传输，改进 Figma 与 Adobe 软件之间的背景、渐变、文字、画板和蒙版还原。中转程序与 Adobe 插件版本统一为 1.0.2。

## 更新与修复

- Photoshop ↔ Illustrator 支持发送选中元素、当前画板或整个文档，尽量保留可编辑文字、矢量和编组。
- Figma → Photoshop 保留画板、组件和实例的背景填充、描边与圆角，修复背景遗漏问题。
- 改进文字行高、混排字号和自动高度文本框，减少多行文字间距变化及末行裁切，文字继续保持可编辑。
- 修复 Figma 与 Photoshop 之间的线性渐变缩放，改善颜色过渡还原。
- Photoshop 画板导入 Figma 时保留尺寸、裁切范围和内容位置；支持的编组蒙版保留内部文字与矢量的可编辑性。
- 改进 Photoshop ↔ Illustrator 的智能对象定位、文字对齐、行距和复杂路径转换。
- Figma → Photoshop 分别显示等待接收、导入中、成功或失败，依据目标软件的实际导入结果反馈状态。

## 演示

完整演示时长 61.7 秒，社区页面按原顺序分为 3 段展示。

[观看或下载完整演示视频](https://github.com/1iinii1/canvas-warp/releases/download/v1.0.2/Canvas-Warp-Demo.mp4)

## 下载与更新

- [全部下载与最新版本](https://github.com/1iinii1/canvas-warp/releases/latest)
- macOS：`Canvas-Warp-mac-universal.dmg`，Intel 与 Apple Silicon 通用，macOS 12+。
- Windows：`Canvas-Warp-win-x64.exe`，Windows 10/11 x64。
- Photoshop：`Canvas-Warp-Photoshop.ccx`，Photoshop 2024+，与中转程序分别安装。
- Illustrator：`Canvas-Warp-Illustrator.zip`，Illustrator 2023+，解压后目录为 `CanvasWarp-AI/`。

Figma 插件从 [Figma Community](https://www.figma.com/community/plugin/1689327694454521056/canvas-warp) 安装。请同时更新中转程序与 Adobe 插件，保存文档并重启 Adobe 软件，关闭重开 Figma 插件，再重新发送内容以应用修复。[安装说明](https://github.com/1iinii1/canvas-warp#安装)。

## 验证与兼容性

**807 项自动测试全部通过，0 失败、0 跳过。** macOS 通用版与 Windows x64 安装包构建成功，Photoshop 和 Illustrator 插件包已重新生成。下载校验值见 `SHA256SUMS.txt`。

不同软件的字体、混合模式和复杂外观可能存在兼容差异。支持的内容尽量保持可编辑，无法转换的效果可能近似处理或使用图片保底；请按实际文档核验结果。

macOS 中转程序尚未配置 Apple Developer ID 公证，Windows 尚未配置 Authenticode 签名；Illustrator 插件为未签名 CEP 开发扩展，需要手动加载。

---

## English release notes

Adds bidirectional Photoshop ↔ Illustrator transfers and improves backgrounds, gradients, text, artboards, and masks across Figma and Adobe apps. The companion and Adobe plugins are version 1.0.2.

## Changes and fixes

- Send selections, the current artboard, or entire documents between Photoshop and Illustrator, preserving editable text, vectors, and groups where supported.
- Figma → Photoshop preserves frame, component, and instance fills, strokes, and corner radii, fixing missing backgrounds.
- Improves line height, mixed font sizes, and auto-height text boxes to reduce spacing differences and clipped final lines while keeping text editable.
- Fixes linear gradient scaling between Figma and Photoshop for more consistent color transitions.
- Photoshop artboards retain their dimensions, clipping, and content positions in Figma. Supported group masks keep their text and vectors editable.
- Improves smart object positioning, text alignment, leading, and complex path conversion between Photoshop and Illustrator.
- Figma → Photoshop shows waiting, importing, succeeded, or failed based on the destination app’s actual import result.

## Demo

The complete demo is 61.7 seconds long. The Community page shows it as three clips in their original order.

[Watch or download the complete demo](https://github.com/1iinii1/canvas-warp/releases/download/v1.0.2/Canvas-Warp-Demo.mp4)

## Downloads and updating

- [All downloads and latest release](https://github.com/1iinii1/canvas-warp/releases/latest)
- macOS: `Canvas-Warp-mac-universal.dmg`. Universal companion for Intel and Apple Silicon; requires macOS 12+.
- Windows: `Canvas-Warp-win-x64.exe`. Companion installer for Windows 10/11 x64.
- Photoshop: `Canvas-Warp-Photoshop.ccx`. Requires Photoshop 2024+; install separately from the companion.
- Illustrator: `Canvas-Warp-Illustrator.zip`. Requires Illustrator 2023+; extracts to `CanvasWarp-AI/`.

Install the Figma plugin from [Figma Community](https://www.figma.com/community/plugin/1689327694454521056/canvas-warp). Also update the companion and Adobe plugins, save your documents, restart Adobe apps, reopen the Figma plugin, and resend your content to apply these fixes. [Installation guide](https://github.com/1iinii1/canvas-warp#安装).

## Validation and compatibility

**All 807 automated tests passed, with 0 failures and 0 skipped.** The macOS universal and Windows x64 installers built successfully, and the Photoshop and Illustrator plugin packages were regenerated. Download checksums are provided in `SHA256SUMS.txt`.

Fonts, blend modes, and complex appearances can differ between apps. Supported content remains editable where possible; unsupported effects may be approximated or use image fallbacks. Check the results with your own documents.

The macOS companion is not Apple Developer ID notarized, and the Windows installer is not Authenticode signed. The Illustrator plugin is an unsigned CEP development extension that requires manual loading.

# Canvas Warp 1.0.1

修复 Figma → Illustrator 中嵌套编组连续使用 PNG 保底时的导入失败和重复对象，保留原有的可编辑文字、原生透明度、描边及投影处理。

## 修复

- 删除旧编组前解析层级引用，清除全部后代的失效引用，保留外部对象顺序。
- 新 PNG 放置或旧编组删除失败时清理新对象与临时任务，避免重复对象；保留仍有效的原编组及子图片任务。
- 面板与 Illustrator 接收脚本版本同步为 2026.10.06.1。
- 更新 20 项过时测试并补强字距、独立透明度、内阴影轮廓、字符区间、原生描边动作和嵌套恢复验证。

## 下载

- macOS：Canvas-Warp-mac-universal.dmg，Intel 和 Apple Silicon 通用，最低 macOS 12。
- Windows：Canvas-Warp-win-x64.exe，Windows 10/11 x64。
- Photoshop：Canvas-Warp-Photoshop.ccx，与中转程序分别安装。
- Illustrator：Canvas-Warp-Illustrator.zip，未签名 CEP 开发扩展，解压后目录为 CanvasWarp-AI/。

Figma 插件从 Figma Community 安装，项目源码保存在私有仓库，不公开提供 Figma 开发包。[安装说明](https://github.com/1iinii1/canvas-warp#安装)。已安装 1.0.0 的用户应更新 Illustrator 扩展文件后重启 Illustrator。

## 验证

完整自动测试 570 项全部通过，0 失败、0 跳过；源码语法检查通过。新增的两项嵌套恢复回归在修复前均失败，在修复后通过。附件校验值见 SHA256SUMS.txt。

本次验证覆盖自动测试与构建，未进行 Adobe/Figma 宿主实机回归。macOS 中转程序尚未配置 Apple Developer ID 公证，Windows 尚未配置 Authenticode 签名；Illustrator 插件需手动加载 CEP 开发扩展。
