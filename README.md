# Codex 余量

一个轻量的 macOS 菜单栏工具，抬眼就能看到 Codex 还剩多少额度。

**[下载 macOS App · v0.1.0 预览版](https://github.com/kale2222/CodexUsage/releases/download/v0.1.0/CodexUsage-0.1.0-macOS-arm64.zip)**

[版本说明与所有下载](https://github.com/kale2222/CodexUsage/releases) · [问题反馈](https://github.com/kale2222/CodexUsage/issues)

- 五小时限额：`5h 72% · 22:29`
- 仅周限额：`7d 86%`

百分比表示剩余额度。五小时模式显示本地重置时刻，点击图标可以查看完整额度和重置日期。

## 功能

- 自动切换五小时／仅周额度显示。
- 透明底 ChatGPT 图标，原生风格弹窗，适配深浅色。
- 默认约每 5 分钟刷新，也支持手动刷新。
- 优先复用本机 Codex 登录，无需手动填写 API Key。
- 支持登录时启动，可配合 Hidden Bar 使用。

## 使用要求

- Apple Silicon Mac，macOS 26 或更新版本。
- 已安装官方 ChatGPT / Codex 桌面应用或 Codex CLI。
- 可使用 Codex 的 ChatGPT 账号。

使用 App 不需要安装 Xcode 或自行编译。

## 下载与安装

从上方链接直接下载安装包，或在 [Releases](https://github.com/kale2222/CodexUsage/releases/tag/v0.1.0) 的附件中选择 **`CodexUsage-0.1.0-macOS-arm64.zip`**。

请不要下载 GitHub 自动生成的 `Source code (zip)` 或使用“Code → Download ZIP”；它们仅包含仓库中的说明文件，不包含 App。

1. 下载 macOS arm64 的 App 压缩包，解压得到 `CodexUsage.app`。
2. 将 App 拖入“应用程序”文件夹并打开。
3. 点击菜单栏中的 ChatGPT 图标查看额度。若提示未登录，点击“连接 Codex”，在浏览器完成登录。

## 重要：按住 Command（⌘）拖动菜单栏图标

> **按住键盘上的 Command（⌘）键，再用鼠标拖动菜单栏中的 ChatGPT 余量图标，就可以调整它的位置。**

1. 按住 **Command（⌘）** 不放。
2. 用鼠标按住余量图标，在菜单栏内向左或向右拖动。
3. 拖到喜欢的位置后松开鼠标，再松开 Command。应用会记住调整后的位置。

**建议放在靠近时钟、容易看到的位置。** 带刘海的 Mac 如果菜单栏图标较多，靠左的项目可能被遮挡。

**使用 Hidden Bar？** 先点击它的箭头展开隐藏图标，再按住 **Command（⌘）**，将余量项拖到 **Hidden Bar 分隔线右侧的常显区**，这样收起其他图标后仍能一眼看到额度。

## 首次打开被 macOS 拦截？

当前为本地签名预览版，尚未完成 Apple 公证。首次打开时，可能出现“无法验证开发者”或“Apple 无法检查此 App 是否包含恶意软件”等提示。

确认安装包下载自本仓库的 **Releases** 后，可按以下步骤操作：

1. 先尝试打开 `CodexUsage.app`，然后关闭拦截提示。
2. 打开 **系统设置 → 隐私与安全性**，向下找到“安全性”区域。
3. 找到与 `CodexUsage` 相关的拦截记录，点击 **“仍要打开”**。
4. 按系统提示验证身份，并再次确认 **“打开”**。

如果没有“仍要打开”按钮，或提示“App 已损坏”“将损坏你的电脑”，请不要一概当作普通未公证提示；可重新从 Releases 下载，并在 Issues 中附上提示截图以便排查。

详细说明：[Apple 官方：在 Mac 上安全地打开 App](https://support.apple.com/zh-cn/102445)。

## 常见问题

**为什么只有一周额度？**

当前账号仅提供周限额时，菜单栏会自动显示 `7d`，完整重置日期放在详情里。

**找不到菜单栏图标？**

再次打开 App 即可显示详情窗口。也可以按住 **Command（⌘）** 调整图标位置；使用 Hidden Bar 时，请将余量项放在分隔线右侧的常显区，具体步骤见上方说明。

**断网后数字还在，正常吗？**

读取失败时会保留上次成功数据并显示异常标记，可在详情中查看最后更新时间。

**关闭窗口后还会运行吗？**

会。关闭详情窗口不影响后台更新；需要停止时，在弹窗中选择“退出 Codex 余量”。

---

非 OpenAI 官方项目。ChatGPT 图形标识归 OpenAI 所有。
