# Canvas Warp

## 中文

Canvas Warp 在 Figma、Photoshop、Illustrator 和兼容的 FlowGPT Canvas 之间传递图层与图片。传输通过本机 `localhost:43119` 完成。

此仓库仅提供安装说明、问题反馈与成品下载，项目源码保存在私有仓库。安装包包含运行插件所需的文件。

当前版本 **1.0.3**：支持 Figma ↔ Photoshop、Figma ↔ Illustrator 和 Photoshop ↔ Illustrator 双向传输，也可向兼容的 FlowGPT Canvas 发送透明 PNG。[查看更新内容](release-notes.md)。

1.0.3 将 Figma → Photoshop 的单批上限提高到 2000 个图层。请同时更新 Figma 社区插件、本地中转程序和 Photoshop 插件；其他方向的原有限制及 256 MB 请求体上限保持不变。

## 演示

完整演示时长 61.7 秒，社区页面按原顺序分为 3 段展示。

[观看或下载完整演示视频](https://github.com/1iinii1/canvas-warp/releases/download/v1.0.2/Canvas-Warp-Demo.mp4)

## 下载

[全部下载与最新版本](https://github.com/1iinii1/canvas-warp/releases/latest)

| 下载项 | 链接 | 系统要求 |
| --- | --- | --- |
| macOS 中转程序 | [通用 DMG](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-mac-universal.dmg) | macOS 12+，Intel 或 Apple Silicon |
| Windows 中转程序 | [x64 安装程序](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-win-x64.exe) | Windows 10/11 x64 |
| Photoshop 插件 | [CCX 安装包](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-Photoshop.ccx) | Photoshop 2024+ |
| Illustrator 插件 | [CEP 开发版 ZIP](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-Illustrator.zip) | Illustrator 2023+，需手动加载 |

Figma 插件从 [Figma Community](https://www.figma.com/community/plugin/1689327694454521056/canvas-warp) 安装。首次使用需分别安装中转程序与目标 Adobe 插件。每个 Release 提供固定文件名的安装包和 `SHA256SUMS.txt`，版本由 Release 标签标识。

## 安装

### 中转程序

Windows 运行 EXE 安装程序。macOS 打开 DMG，将 Canvas Warp 拖入“应用程序”。安装后至少手动启动一次，以注册 `canvas-warp://` 启动协议。

如果旧版 PS to Figma Bridge 仍在运行，请先退出它，避免占用相同端口。中转程序不会自动安装或卸载 Adobe 插件。

安装包目前未配置 Apple Developer ID 公证或 Windows Authenticode 签名，系统可能显示安全提示。

### Photoshop 插件

下载 CCX，双击并按 Creative Cloud 提示安装，然后重启 Photoshop，打开 Canvas Warp 面板。[Adobe CCX 安装说明](https://developer.adobe.com/uxp/guides/how-to/distribution/install/)。如果安装失败，可点击 Creative Cloud 的 Details 查看错误日志，并在 Issues 中报告具体提示。

### Illustrator 插件

目前提供未签名的 CEP 开发扩展，需要手动加载。解压后，将整个 `CanvasWarp-AI/` 文件夹复制到：

- macOS：`~/Library/Application Support/Adobe/CEP/extensions/`
- Windows：`%APPDATA%\Adobe\CEP\extensions\`

开发扩展需要为所用 Illustrator 的对应 CSXS 版本开启 `PlayerDebugMode`，步骤见 [Adobe CEP 开发扩展指南](https://github.com/Adobe-CEP/CEP-Resources/blob/master/CEP_12.x/Documentation/CEP%2012%20HTML%20Extension%20Cookbook.md#debugging-unsigned-extensions)。指南以 CSXS 12 为例，旧版宿主需替换成对应版本。重启 Illustrator 后，在“窗口 → 扩展”中打开 CanvasWarp-AI。此开发包尚未提供签名的一键安装器。

### Figma 插件

在 [Figma Community](https://www.figma.com/community/plugin/1689327694454521056/canvas-warp) 安装并运行 Canvas Warp，保持插件面板打开。选择 Figma 内容后，点击 Photoshop 或 Illustrator 发送；在 Adobe 插件中选择内容并发送到 Figma，即可由 Figma 面板自动接收。

### Photoshop ↔ Illustrator

在两端打开 Canvas Warp 面板并启动新版中转程序。源软件选择“选中元素”“当前画板”或“整个文档”，再点击目标软件卡片。选中元素导入目标软件当前文档；当前画板和整个文档会新建目标文档。发送选中元素前，请先打开目标文档。

## 兼容性与反馈

文字、矢量、编组和蒙版尽量保持可编辑。缺少字体、复杂外观或不同软件的 API 限制可能导致近似处理或图片保底；请先用文档副本核验结果。

1.0.3 将 Figma → Photoshop 的单批上限提高到 2000 个图层。请同时更新 Figma 社区插件、本地中转程序和 Photoshop 插件；其他方向的原有限制及 256 MB 请求体上限保持不变。完整自动测试 **812 项全部通过，0 失败、0 跳过**，源码语法检查通过；尚未进行 2000 层文档的宿主实际收发验证。

[报告问题或提出建议](https://github.com/1iinii1/canvas-warp/issues)时，请提供操作系统、软件版本、传输方向和错误提示。

---

## English

Canvas Warp transfers layers and images between Figma, Photoshop, Illustrator, and a compatible FlowGPT Canvas. Transfers run locally through `localhost:43119`.

This repository provides installation instructions, issue tracking, and release downloads. Source code is kept in a private repository. Installers include the files needed to run the plugins.

Current version: **1.0.3**. Transfer in both directions between Figma and Photoshop, Figma and Illustrator, and Photoshop and Illustrator. Transparent PNGs can also be sent to a compatible FlowGPT Canvas. [Read the release notes](release-notes.md).

Version 1.0.3 increases Figma → Photoshop transfers to 2,000 layers per batch. Update the Figma Community plugin, desktop companion, and Photoshop plugin together. Other directions retain their existing limits, and the request-size limit remains 256 MB.

## Demo

The complete demo is 61.7 seconds long. The Community page shows it as three clips in their original order.

[Watch or download the complete demo](https://github.com/1iinii1/canvas-warp/releases/download/v1.0.2/Canvas-Warp-Demo.mp4)

## Downloads

[All downloads and latest release](https://github.com/1iinii1/canvas-warp/releases/latest)

| Download | Link | Requirements |
| --- | --- | --- |
| macOS companion | [Universal DMG](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-mac-universal.dmg) | macOS 12+, Intel or Apple Silicon |
| Windows companion | [x64 installer](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-win-x64.exe) | Windows 10/11 x64 |
| Photoshop plugin | [CCX installer](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-Photoshop.ccx) | Photoshop 2024+ |
| Illustrator plugin | [CEP development ZIP](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-Illustrator.zip) | Illustrator 2023+, manual setup |

Install the Figma plugin from [Figma Community](https://www.figma.com/community/plugin/1689327694454521056/canvas-warp). Install the desktop companion and the required Adobe plugins separately. Each release uses stable installer filenames and includes `SHA256SUMS.txt`; the release tag identifies the version.

## Installation

### Desktop companion

On Windows, run the EXE installer. On macOS, open the DMG and drag Canvas Warp into Applications. Launch it manually at least once to register the `canvas-warp://` launch protocol.

Quit any older PS to Figma Bridge instance first to free the shared port. The companion does not automatically install or remove Adobe plugins.

Installers are not currently Apple Developer ID notarized or Windows Authenticode signed, so the operating system may display a security prompt.

### Plugin

Download and double-click the CCX file, then follow the Creative Cloud prompts. Restart Photoshop and open the Canvas Warp panel. See [Adobe’s CCX installation guide](https://developer.adobe.com/uxp/guides/how-to/distribution/install/). If installation fails, open Details in Creative Cloud and report the exact error in Issues.

### Plugin

The Illustrator plugin is an unsigned CEP development extension that requires manual loading. Extract the ZIP and copy the entire `CanvasWarp-AI/` folder into:

- macOS: `~/Library/Application Support/Adobe/CEP/extensions/`
- Windows: `%APPDATA%\Adobe\CEP\extensions\`

Enable `PlayerDebugMode` for the CSXS version used by your Illustrator installation, following the [Adobe CEP development extension guide](https://github.com/Adobe-CEP/CEP-Resources/blob/master/CEP_12.x/Documentation/CEP%2012%20HTML%20Extension%20Cookbook.md#debugging-unsigned-extensions). The guide uses CSXS 12; use the matching version for an older host. Restart Illustrator and open CanvasWarp-AI from Window → Extensions. A signed one-click installer is not yet available.

### Plugin

Install and run Canvas Warp from [Figma Community](https://www.figma.com/community/plugin/1689327694454521056/canvas-warp), and keep its panel open. Select content in Figma, then click Photoshop or Illustrator to send it. To receive from Adobe apps, select content in the Adobe plugin and send it to Figma.

### Photoshop ↔ Illustrator

Open the Canvas Warp panel in both apps and launch the updated companion. In the source app, choose Selection, Current artboard, or Entire document, then click the destination app card. Selections go into the destination’s current document; artboards and entire documents create a new document. Open a destination document before sending a selection.

## Compatibility and feedback

Text, vectors, groups, and masks remain editable where supported. Missing fonts, complex appearances, and app API limitations can lead to approximations or image fallbacks. Check the result using a document copy first.

Version 1.0.3 increases Figma → Photoshop transfers to 2,000 layers per batch. Update the Figma Community plugin, desktop companion, and Photoshop plugin together. Other directions retain their existing limits, and the request-size limit remains 256 MB. **All 812 automated tests passed, with 0 failures and 0 skipped**, and runtime syntax checks passed. A 2,000-layer transfer has not yet been tested in the actual hosts.

When [reporting an issue or suggesting an improvement](https://github.com/1iinii1/canvas-warp/issues), include your operating system, app versions, transfer direction, and any error message.
