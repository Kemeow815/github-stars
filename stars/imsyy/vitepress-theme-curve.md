---
project: vitepress-theme-curve
stars: 335
description: |-
    🎉 A Simple VitePress Theme | 一个极简的 VitePress 主题
url: https://github.com/imsyy/vitepress-theme-curve
---

<h1 align="center"> Curve </h1>
<p align="center">A Simple VitePress Theme</p>
<p align="center">
  <img src="https://github.com/imsyy/vitepress-theme-curve/assets/42232682/bed62689-cfd8-4d98-b946-24555d4ce1fb" alt="curve-logo" />
</p>

---

> [!TIP]
> 近期将通过 Nuxt 重构本项目前后端，敬请期待

Preview: 👻 [無名小栈](https://blog.imsyy.top/)

Docs: 📖 [主题文档](https://blog.imsyy.top/pages/categories/%E4%B8%BB%E9%A2%98%E6%96%87%E6%A1%A3)

> [!NOTE]
> 该主题本意为自用，所以部分配置可能并不完善，包括评论系统的支持，目前仅支持 Artalk，如有其他需求，可提交 pr

## Hello

🎉 你好啊，很高兴你选择了 [vitepress-theme-curve](https://github.com/imsyy/vitepress-theme-curve)，你可以查看 [主题文档](https://blog.imsyy.top/pages/categories/%E4%B8%BB%E9%A2%98%E6%96%87%E6%A1%A3) 以了解更多，如果你在使用本主题时遇到问题，你可以在 [GitHub](https://github.com/imsyy/vitepress-theme-curve) 中正确的提交 [issues](https://github.com/imsyy/vitepress-theme-curve/issues) 以获取社区的帮助。

## 快速开始

若您有修改主题的需求，请确保您拥有基础的前端知识，最好能掌握 [Vue.js](https://vuejs.org/) 框架的相关知识，并确保阅读了 `VitePress` 的 [官方文档](https://vitepress.dev/zh/guide/what-is-vitepress)

### 书写新的文章

你可以直接在站点根目录中的 `posts` 文件夹中直接新建 `markdown` 文件来书写，您的文件路径即为实际生成的网址路径。

### 添加新的页面

你可以直接在站点根目录中的 `pages` 文件夹中直接新建 `markdown` 文件来实现新建页面，您的文件路径即为实际生成的网址路径。

主题中已经内置了几个常用页面以供参考。

### 主题配置

本主题提供了一个 `themeConfig.mjs` 文件用来配置，它位于 `.vitepress\theme\assets\themeConfig.mjs`，你可以将它复制一份并移动至根目录中，在这里里面的修改将会覆盖初始配置，请注意，**请不要更改文件名或者删除原配置文件，否则它将会不起作用！**

### 静态文件

通常情况下，静态文件处于根目录下的 `public` 文件夹中，通常用于存放字体或图片等文件信息。

了解更多：[资源处理](https://vitepress.dev/zh/guide/asset-handling#asset-handling)

### 部署

如果你之前使用过类似于 [Hexo](https://hexo.io/zh-cn/) 一样的静态站点生成器的话，那么这二者是极为相似的，都是构建为静态文件后上传至服务器以实现访问，当然，你也可以借助 GitHub 的 Actions 以实现自动部署，具体细节请参考我的博客，此处不再细说。

```bash
# 安装依赖
npm run install
# 构建
npm run build
```

建议使用 `pnpm`，若未安装，可使用 `npm install pnpm -g` 来安装。

```bash
pnpm install
pnpm build
```

通常在未修改配置文件的情况下，打包后的文件会处于根目录下的 `.vitepress\dist` 目录中，您可以将其中的文件上传至任意服务器以访问。

## 更多

更多信息请参考：[主题文档](https://blog.imsyy.top/pages/categories/%E4%B8%BB%E9%A2%98%E6%96%87%E6%A1%A3)

> Powered by VitePress

[![Netlify Status](https://api.netlify.com/api/v1/badges/31ebe949-6ce7-46b7-a5fb-a73da20412d6/deploy-status)](https://app.netlify.com/sites/imsyy-blog/deploys)

