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
