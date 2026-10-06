# Canvas Warp 下载与安装

Canvas Warp 在 Figma、Photoshop、Illustrator 和兼容的 FlowGPT Canvas 之间传递图层与图片。传输通过本机 `localhost:43119` 完成。

此仓库仅提供安装说明、问题反馈与成品下载，项目源码保存在私有仓库。安装包包含运行插件所需的文件。

## 下载

[全部下载与最新版本](https://github.com/1iinii1/canvas-warp/releases/latest)

| 下载项 | 链接 | 系统要求 |
| --- | --- | --- |
| macOS 中转程序 | [通用 DMG](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-mac-universal.dmg) | macOS 12+，Intel 或 Apple Silicon |
| Windows 中转程序 | [x64 安装程序](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-win-x64.exe) | Windows 10/11 x64 |
| Photoshop 插件 | [CCX](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-Photoshop.ccx) | Photoshop 2024+ |
| Illustrator 插件 | [CEP 开发版 ZIP](https://github.com/1iinii1/canvas-warp/releases/latest/download/Canvas-Warp-Illustrator.zip) | Illustrator 2023+，需手动加载 |

Figma 插件从 Figma Community 安装。首次使用需分别安装中转程序与目标 Adobe 插件。每个 Release 提供固定文件名的安装包和 `SHA256SUMS.txt`，版本由 Release 标签标识。

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

在 Figma Community 安装并运行 Canvas Warp，保持插件面板打开。选择 Figma 内容后，点击 Photoshop 或 Illustrator 发送；在 Adobe 插件中选择内容并发送到 Figma，即可由 Figma 面板自动接收。

## 兼容性与反馈

文字、矢量、编组和蒙版尽量保持可编辑。缺少字体、复杂外观或不同软件的 API 限制可能导致近似处理或图片保底；请先用文档副本核验结果。

当前版本为 **1.0.1**，修复了 Illustrator 嵌套编组 PNG 保底的失效引用和重复对象。源码语法检查通过，完整自动测试 **570 项全部通过，0 失败、0 跳过**。本次验证覆盖自动测试与构建，宿主实机回归仍需继续验证。

[报告问题或提出建议](https://github.com/1iinii1/canvas-warp/issues)时，请提供操作系统、软件版本、传输方向和错误提示。
