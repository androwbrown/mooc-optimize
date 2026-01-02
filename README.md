# 解除中国大学 MOOC网站各种限制

[![许可证](https://img.shields.io/github/license/mashape/apistatus.svg)](https://opensource.org/licenses/MIT)
[![最新发行版](img.shields.io)](https://github.com/androwbrown/mooc-optimize/releases)
[![问题](img.shields.io)](https://github.com/androwbrown/mooc-optimize/issues)

优化中国大学MOOC网站体验，解除复制粘贴限制、允许右键、禁止弹窗警告、去除水印、禁止切屏检测、禁止检测页面非活动状态。

---

## 🚀 功能特性

- **✅ 移除复制粘贴限制**：在考试或评论区中允许复制问题和答案。
- **✅ 允许浏览器右键**：解除右键菜单限制，方便搜索、翻译等操作。
- **✅ 禁止切屏检测**：无需担心因切换窗口而导致考试中断或弹出警告。
- **✅ 屏蔽弹窗警告**：自动拦截干扰性弹窗，屏蔽警告通知。
- **✅ 去除页面水印**：移除覆盖在视频和文档上的水印。

## 🔧 工作原理

本脚本核心原理如下：

1.  **事件监听与重写**:
    -   将 `oncopy`, `onpaste`, `oncut`, `oncontextmenu` 等事件的处理器重置为 `null`，有效解除中国大学MOOC通过JavaScript施加的复制和右键限制。
    -   针对切屏检测，拦截并覆盖 `window` 或 `document` 对象上的 `blur` 和 `visibilitychange` 事件监听器，从而阻止页面检测到用户是否离开了当前标签页。

2.  **DOM 操作**:
    -   **去除水印**：识别水印DOM元素，并将其从页面中移除或隐藏。
    -   **屏蔽弹窗**：重写 `window.alert` 和 `window.confirm` 等原生函数，捕获并阻止弹出窗口的显示，避免中断用户操作。

3.  **MutationObserver**:
    -   应对异步加载的视频或文档，利用 `MutationObserver` API来监视DOM树的变化。一旦检测到新的限制性元素被添加到页面中，立即将其移除。

## 📦 安装

要使用此脚本，您的浏览器需要安装一个用户脚本管理器，推荐使用以下任意一款：

-   [**Tampermonkey**](https://www.tampermonkey.net/) (适用于 Chrome, Firefox, Safari, Edge)
-   [**Violentmonkey**](https://violentmonkey.github.io/) (适用于 Chrome, Firefox, Edge)

安装好管理器后，点击下方的链接进行安装：

➡️ **[点击此处安装脚本](https://greasyfork.org/en/scripts/561120-%E8%A7%A3%E9%99%A4%E4%B8%AD%E5%9B%BD%E5%A4%A7%E5%AD%A6-mooc%E7%BD%91%E7%AB%99%E5%90%84%E7%A7%8D%E9%99%90%E5%88%B6/code)** ⬅️


## 🤝 贡献

欢迎通过以下方式为本项目做出贡献：

-   **提交问题**：如果您发现任何bug或有功能建议，请在 [Issues](https://github.com/Naist/mooc.usr.js/issues) 页面提交。
-   **发起拉取请求**：如果您修复了bug或实现了新功能，欢迎发起 [Pull Request](https://github.com/Naist/mooc.usr.js/pulls)。

## 📄 许可证

本项目采用 [MIT 许可证](https://opensource.org/licenses/MIT)授权。
