<img src="screenshots/app-icon.png" width="84" alt="AIUsage App 图标">

# AIUsage（Codex / Gemini 余量）

一个轻量的 macOS 菜单栏工具，抬眼就能看到 **Gemini（Antigravity）** 与 **Codex** 还剩多少额度，支持在弹窗顶部一键切换服务。

**[下载 macOS App · v0.1.2 预览版](https://github.com/kale2222/CodexUsage/releases/download/v0.1.2/CodexUsage-0.1.2-macOS-arm64.zip)**

[所有版本](https://github.com/kale2222/CodexUsage/releases) · [问题反馈](https://github.com/kale2222/CodexUsage/issues)

- **Gemini（Antigravity）**：显示五小时与一周余量（如 `5h 75% · 22:29`）及独立额度组（如 Claude 与 GPT 模型）；默认每 15 分钟自动刷新，打开弹窗时按需更新。
- **Codex**：支持五小时限额（`5h 72% · 22:29`）与仅周限额（`7d 86%`）；默认约每 5 分钟自动刷新，支持手动刷新与脱敏账号核验。
- **Claude**：弹窗顶部预留切换入口，当前尚未接入，不会发起后台读取。
- 仅对当前选中的服务执行刷新与唤醒，支持登录时启动。

百分比表示**剩余额度**，时间表示本地重置时刻。无需 Xcode 或自行编译。

## 界面预览

<img src="screenshots/menu.png" width="180" alt="实际菜单栏中的余量项">

<p><img src="screenshots/gemini.png" width="310" alt="Gemini 五小时、一周与独立额度组"><img src="screenshots/dual.png" width="310" alt="Codex 五小时与一周额度详情"></p>

<p><img src="screenshots/weekly.png" width="310" alt="Codex 仅周限额、版本与脱敏账号"></p>

以上是运行中的原生 App 视图截图，使用离线演示身份与额度；截图采用纯色底方便阅读，实际浮层使用系统材质，不是 HTML 原型。

## 使用要求

- Apple Silicon Mac，macOS 26 或更新版本。
- **使用 Gemini（Antigravity）**：本机已安装并登录 `agy` CLI（要求 `1.1.11` 或更新版本，本机已验证 `1.5.16`）。
- **使用 Codex**：安装官方 ChatGPT / Codex 桌面应用或 Codex CLI，并使用具有 Codex 权限的 **ChatGPT 账号登录**（不是 API Key 登录）。

本机已验证 macOS 26.5.2、官方内附 Codex `0.154.0-alpha.6.2` 与 `agy 1.5.16`。其他机器、组件版本及套餐仍需试用反馈；是否有可显示的窗口以官方实际返回为准。

## 安装与首次连接

1. 下载附件 **`CodexUsage-0.1.2-macOS-arm64.zip`**，解压后将 `CodexUsage.app` 拖入“应用程序”。
2. 打开本 App，点击菜单栏图标，在弹窗顶部切换 **Codex / Gemini / Claude**：
   - **Gemini**：首次启动默认选中 Gemini。若终端已登录 `agy`，会自动读取余量；若尚未登录或刚完成登录，请在终端登录 `agy` 后点击“重新检查”。
   - **Codex**：已有可用登录时会直接显示额度；否则点击“连接 Codex”，在官方浏览器流程中登录。点击眼睛按钮可显示完整邮箱，与官方应用的个人资料菜单核对。

请下载 Release 的 **App ZIP 附件**。`Source code (zip)` 和“Code → Download ZIP”仅包含本仓库的说明与截图，不是安装包。

<details>
<summary><strong>还没有安装官方 Codex 组件？</strong></summary>

**推荐桌面方式：**打开 [OpenAI 官方快速入门](https://developers.openai.com/codex/quickstart/)，选择 Desktop／桌面应用，下载 macOS 版本，安装到“应用程序”，启动后选择 ChatGPT 账号登录。只在浏览器登录 ChatGPT，并不代表本机已有 Codex 组件。

**已有 Homebrew 的用户也可以安装 CLI：**

```sh
brew install --cask codex
codex login
```

按浏览器提示使用 ChatGPT 账号登录，再打开本 App。这里不需要让 Codex 执行编程任务。

如果提示“未找到官方 Codex 程序”，点击“选择 Codex 程序…”，选择已安装的官方 `.app`，或官方 `codex` 可执行文件。若组件版本较旧，先更新官方应用／CLI 再重试。只选择来自官方的程序。

[官方 CLI 安装说明](https://github.com/openai/codex) · [官方登录说明](https://developers.openai.com/codex/auth/)

</details>

## 重要：按住 Command（⌘）拖动菜单栏图标

> **按住 Command（⌘），再用鼠标拖动菜单栏中的余量图标，就可以调整位置。**

拖到靠近时钟、容易看到的位置后松开鼠标，再松开 Command，应用会记住位置。

**使用 Hidden Bar？** 先点击箭头展开隐藏图标，再按住 **Command（⌘）**，将余量项移到**分隔线右侧的常显区**。找不到入口时，再次打开 App 也能找回详情窗口。

## 首次打开被 macOS 拦截？

当前为本地签名预览版，**尚未完成 Apple 公证**。若提示“无法验证开发者”或“Apple 无法检查此 App 是否包含恶意软件”，确认下载来自本仓库 Releases 后：

1. 尝试打开 App，然后关闭拦截提示。
2. 打开 **系统设置 → 隐私与安全性 → 安全性**。
3. 找到与 CodexUsage / AIUsage 相关的拦截记录，点击 **“仍要打开”**。
4. 按提示验证身份，并确认“打开”。

若没有相应按钮，或提示“App 已损坏”“将损坏你的电脑”，不要一概当作普通未公证提示；请重新下载并反馈具体错误。[Apple 官方说明](https://support.apple.com/zh-cn/102445)

## 账号与隐私

- **Gemini 数据路径**：**本 App → 本机 `agy` → 官方服务**。仅通过 `agy` 只读报告获取额度，不读取、复制或刷新凭据；报告不包含账号邮箱，因此 Gemini 视图不显示账号行。
- **Codex 数据路径**：**本 App → 本机官方 Codex 组件 → 官方服务**。读取的是 Codex 的 ChatGPT 账号限额，不是 API 余额或通用消息额度；详情默认对邮箱脱敏，点击眼睛按钮才显示完整邮箱，关闭详情、切到其他应用、重新连接或读取失败后会恢复脱敏。
- 本 App 没有开发者后端，也没有内置遥测或自动上报；不主动将邮箱或额度写入磁盘，只保存菜单栏位置、当前所选服务及程序路径等偏好。
- 密码和 token 均由各自官方组件管理。退出或卸载本 App 不会退出官方组件的共享账号。

<details>
<summary><strong>登录失败、账号不符或额度不一致怎么办？</strong></summary>

**Gemini：**
- 提示未登录或未找到 `agy` 时，请在终端确认已安装 `agy`（≥ 1.1.11）并完成登录，然后点击弹窗中的“重新检查”。
- 仅在菜单栏切换到 Gemini 时才会刷新 Gemini 额度；切到其他服务不会在后台启动 `agy`。

**Codex：**
- 登录取消、超时或失效时，可以重新点击“连接 Codex”。取消连接只停止本次等待，不是注销官方账号。
- 如果显示的邮箱不符，桌面用户可在对应官方应用的个人资料菜单退出并登录正确账号；CLI 用户可使用 `codex logout` 后再运行 `codex login`。完成外部登录后，退出并重新打开本 App。不要删除或上传 `auth.json` 来排障。

断网时保留上次成功数据并显示异常标记，恢复后可手动刷新。截图分享前请保持账号脱敏。

</details>

## 更新与卸载

**更新：**在旧版弹窗中选择退出应用，下载新版 App 并替换“应用程序”中的旧副本，再打开。详情右上角可核对版本与构建号，例如 `v0.1.2 (3)`。保留原安装路径可沿用菜单栏位置与偏好；更新后请检查“登录时启动”，预览版可能再次出现系统拦截提示。

**回退：**退出当前版本，从 Releases 下载旧版，在同一位置替换后打开。不同版本的偏好兼容性尚未全面验证。

**卸载：**先关闭“登录时启动”（若设置失败，到系统设置的登录项中确认），然后退出 App，将 App 移到废纸篓。关闭详情窗口本身不会退出后台。卸载本工具不需要删除官方 Codex 组件、`agy` 或它们的登录凭据。

## 反馈问题

在 [Issues](https://github.com/kale2222/CodexUsage/issues) 中提供：App 版本、macOS／芯片、官方组件名称与版本、首次使用还是更新后发生、操作步骤、错误提示及脱敏截图。

**不要提交密码、token、`auth.json` 或完整授权 URL。** 本版仍为预览版，另一台全新 Mac 的首次安装和登录、长期睡眠／自启行为尚待进一步验证。

---

本仓库仅提供 App、使用说明和截图，不公开应用源码。非 OpenAI / Google / Anthropic 官方项目；相关图形标识归各自版权方所有。
