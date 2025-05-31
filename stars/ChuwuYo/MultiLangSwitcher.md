---
project: MultiLangSwitcher
stars: 61
description: |-
    MultiLangSwitcher 是一个 Chromium 内核浏览器扩展，帮助用户快速切换浏览器发送的 Accept-Language HTTP 请求头。
url: https://github.com/ChuwuYo/MultiLangSwitcher
---

<div align="center">
    <img src="images/icon128.png" alt="MultiLangSwitcher Icon" width="150" height="150"> <h1>MultiLangSwitcher</h1>
    <a href="https://github.com/ChuwuYo/MultiLangSwitcher/blob/main/README.md">简体中文</a> | <a href="https://github.com/ChuwuYo/MultiLangSwitcher/blob/main/README_EN.md">English</a> </div>

---

<div align="center">
项目概述

 <a href="https://deepwiki.com/ChuwuYo/MultiLangSwitcher"><img src="https://deepwiki.com/badge.svg" alt="Ask DeepWiki"></a>

</div>

---


MultiLangSwitcher 是一个 Chromium 内核浏览器扩展，帮助用户快速切换浏览器发送的 `Accept-Language` HTTP 请求头。用户也可以在调试工具页面自定义完整的 `Accept - Language` 字符串。

扩展利用高效的 `chrome.declarativeNetRequest` API 来修改请求头，确保性能和隐私。

页面样式采用Bootstrap框架。

如果拓展自带的请求头检测报错或不返回结果，可以自行跳转到 [浏览器检测](https://webcha.cn/) 、 [BrowserScan](https://www.browserscan.net/zh) 、 [header-echo](https://header-echo.addr.tools/) 进行查看。

如果需要切换浏览器UA可以看一下这个项目：[User-Agent Switcher and Manager](https://github.com/ray-lothian/UserAgent-Switcher)

<div align="center">
    <img src="https://github.com/user-attachments/assets/e44b6d72-b66c-4be5-a80d-a2de07fb86c6" alt="MultiLangSwitcher Home">


</div>

---

同时建议在浏览器语言设置如图设置,这样做可以混淆一些简单的 `navigator.languages` 检测。

<div align="center">
    <img src="https://github.com/user-attachments/assets/c056e5ee-6c65-4786-98d4-ee33f4beef47" alt="Suggestion">
</div>

这是自定义 `Accept - Language` 字符串的演示。

<div align="center">
    <img src="https://github.com/user-attachments/assets/4136c601-5f02-467e-9f42-12eefb5a65dc" alt="Custom Accept-Language">
</div>

***

<div align="center">
功能特性
</div>

***

* **快速语言切换**: 通过浏览器工具栏弹出的界面，提供丰富的语言列表供您选择并应用。
* **按域名自动切换语言**: 根据访问的域名自动切换语言，支持顶级域名（如 `.com`, `.cn`）和二级域名（如 `com.cn`, `co.jp`）。扩展会自动应用对应域名的语言设置，当没有匹配规则时使用英语（`en`）。
* **设置持久化**: 您上次选择的语言偏好以及按域名自动切换的状态会自动保存，并在每次浏览器启动时自动加载和应用。
* **高效请求头修改**: 利用 `declarativeNetRequest` API，直接修改请求头，相比 WebRequest API 更加高效且不影响性能。
* **后台自动应用**: 扩展在浏览器启动和安装/更新时，会自动读取并应用保存的语言设置和自动切换状态。
* **全面的测试页面**: 提供一个 `/test-headers.html` 页面，用于直观地验证 `Accept-Language` 头是否已成功更改，并检测浏览器暴露的 JavaScript 语言偏好 (`navigator.language`, `navigator.languages`)、国际化 API (Intl) 等信息。同时，还包含 WebRTC 本地 IP 泄露以及 Canvas、WebGL、AudioContext 等可能的浏览器指纹信息检测，帮助您了解和控制浏览器暴露的信息。
* **调试工具**: 提供一个独立的 `/debug.html` 页面，包含以下诊断和修复工具：
    * **规则信息**: 查看扩展当前通过 `declarativeNetRequest` 设置的动态规则详情，包括规则 ID、优先级、操作、条件，以及最近匹配到的规则信息（匹配的 URL、资源类型等）。
    * **请求头测试**: 手动选择语言并向测试服务发送请求，直接查看浏览器实际发送的请求头。
    * **自定义 `Accept - Language` 字符串**：自定义语言偏好,输入完整的 `Accept - Language` 字符串并保存。
    * **实时日志**: 接收并显示扩展（包括弹出页和后台服务）在运行时发送的日志消息，帮助追踪代码执行和问题。
    * **常见问题修复**: 提供一键操作，例如提高规则优先级以解决可能与浏览器或其他扩展的规则冲突，或清除并重新应用规则。
    * **扩展诊断信息**: 显示扩展ID、版本、Manifest配置、权限状态以及本地存储中保存的语言设置和自动切换状态，提供全面的扩展运行时信息。

***

<div align="center">
安装指南
</div>

***

### 从 Chrome Web Store / Microsoft Edge Extensions Home 安装 (未发布)

目前仅支持从源代码安装。

为什么？因为谷歌开发者需要一张国际支付信用卡和5美元。

### 从源代码安装

1.  **下载或克隆代码**: 将本项目仓库克隆到您的本地计算机。(或者从release下载ZIP解压)
    ```bash
    git clone https://github.com/ChuwuYo/MultiLangSwitcher.git
    ```
2.  **打开浏览器扩展管理**: 在 Chrome 浏览器地址栏输入 `chrome://extensions/` / `edge://extensions/` 并回车，进入扩展程序管理页面。
3.  **开启开发者模式**: 打开页面右上角的“开发者模式”开关。
4.  **加载已解压的扩展程序**: 点击页面左上角的“加载已解压的扩展程序”按钮，选择您下载的 MultiLangSwitcher 项目文件夹。
5.  **完成**: 扩展程序将成功添加到浏览器中，您可以开始使用了。

***

<div align="center">
使用方法
</div>

***

1.  **打开扩展弹出页**: 点击浏览器工具栏上的 MultiLangSwitcher 扩展图标。
2.  **选择偏好语言**: 在弹出的下拉菜单中选择您希望浏览器模拟的语言。
3.  **应用设置**: 点击界面底部的“应用更改”按钮。您的设置将被保存，并立即应用于新的网络请求。
4.  **验证和调试**: 点击弹出页中提供的“检测页面”或“调试工具”链接，以验证语言设置是否生效，或在遇到问题时进行诊断。

***

<div align="center">
文件结构
</div>

***

* `manifest.json`: 定义扩展的基本信息、权限（包括 `storage` 用于存储设置，`declarativeNetRequest` 用于修改请求头，`tabs` 用于检测页面URL以实现按域名自动切换语言）和配置。
* `popup.html` / `popup.js`: 实现扩展弹出界面和交互逻辑，包括手动语言切换和按域名自动切换的开关控制。
* `background.js`: 作为 Service Worker 在后台运行，处理扩展生命周期事件（如安装、启动）、规则的初始化与应用、监听存储变化以及实现按域名自动切换语言的核心逻辑（包括解析域名、匹配规则、更新请求头）。包含 `domainLanguageRules` 对象用于定义域名与语言的映射关系。
* `rules.json`: 包含静态规则的文件，本项目主要通过动态规则管理语言设置。
* `test-headers.html` / `test-headers.js`: 用于测试浏览器语言和指纹信息的页面及其脚本。
* `debug.html` / `debug-ui.js` / `debug-headers.js`: 实现调试页面及其功能，帮助诊断问题和查看扩展状态。
* `images/`: 存放扩展图标文件。
* `typefaces/`: 存放项目使用的字体文件。
* `README.md`: 项目的中文说明文档。
* `README_EN.md`: 项目的英文说明文档。

***

<div align="center">
感谢贡献者
</div>

<div align="center">
<a href="https://github.com/ChuwuYo/MultiLangSwitcher/graphs/contributors" target="_blank">
  <img src="https://contrib.rocks/image?repo=ChuwuYo/MultiLangSwitcher" alt="Contributors" />
</a>
</div>

