# Canvas Warp 1.0.0

在 Figma、Photoshop、Illustrator 与兼容的 FlowGPT Canvas 之间，通过本机服务传递图层和图片。

## 下载

- macOS：`Canvas-Warp-mac-universal.dmg`，支持 Intel 和 Apple Silicon，最低 macOS 12。
- Windows：`Canvas-Warp-win-x64.exe`，支持 Windows 10/11 x64。
- Photoshop：`Canvas-Warp-Photoshop.ccx`，与中转程序分别安装。
- Illustrator：`Canvas-Warp-Illustrator.zip`，未签名 CEP 开发扩展，解压后目录为 `CanvasWarp-AI/`。
- Figma 插件从 Figma Community 安装，不提供公开的 Figma 开发源码包。

附件采用固定文件名，版本由 Release 标签标识，社区简介可持续使用最新版本的下载链接。文件校验值见 `SHA256SUMS.txt`。

## 安装与兼容性

先安装并启动中转程序，再加载对应 Adobe 插件，保持接收端面板打开。[完整安装说明](https://github.com/1iinii1/canvas-warp#安装)。

macOS 中转程序未配置 Apple Developer ID 公证，Windows 未配置 Authenticode 签名。Photoshop 本地 CCX 安装是否成功取决于 Creative Cloud 的开发包支持；安装失败时请在公开仓库 Issues 中报告提示。Illustrator 当前需要手动加载 CEP 开发扩展。

文字与矢量尽量保持可编辑；字体缺失或复杂外观无法等价映射时会近似处理或以图片保底。请先用文档副本核验转换结果。

## 验证状态

源码语法检查通过。发布前已有单元测试基线为 562 项，其中 542 项通过、20 项失败；失败涉及 Figma 和 Illustrator 的文字、外观及接收端测试，需继续核对测试 mock 与运行行为。平台安装及 Adobe/Figma 宿主中的完整收发仍需实际验证。
