---
project: blog
stars: 2
description: |-
    个人博客项目
url: https://github.com/hhhh-wang/blog
---

<h2 align="center">
变量人生的个人博客
</h2>

## 👋 介绍

一名全栈开发的老登，前端后端一把抓，bug报错两手接。我的博客主要记录我在技术与工具间的翻滚和挣扎，力求用最不费脑的方式，讲清楚最烧脑的内容。

当然，这里不仅有代码，还有全栈老登侠表面跌宕起伏、波澜壮阔实则一事无成的传奇人生。

你可以把这当成是技术日记，也可以当成老登的人生反思录，反正我写得认真，你看得开心就行


## ✨ 特性

- 🦖 **Docusaurus** - 基于 Docusaurus，提供强大的文档生成和博客功能
- ✍️ **Markdown** - 写作方便，Markdown
- 🎨 **Beautiful** - 整洁，美观，阅读体验优先
- 🖥️ **PWA** - 支持 PWA，可安装，离线可用
- 🌐 **i18n** - 支持国际化
- 💯 **SEO** - 搜索引擎优化，易于收录
- 📊 **谷歌分析** - 支持 Google Analytics
- 🔎 **全文搜索** - 支持 [Algolia DocSearch](https://github.com/algolia/docsearch)
- 🚀 **持续集成** - 支持 CI/CD，自动部署更新内容
- 🏞️ **首页视图** - 显示最新博客文章、项目展示，个人特点，技术栈等
- 🗃️ **博文视图** - 不同的博文视图，列表、宫格
- 🌈 **资源导航** - 收集并分享有用、有意思的资源
- 📦 **项目展示** - 展示你的项目，可用作于作品集

## :wrench: 技术栈

- Docusaurus
- TailwindCSS
- Framer motion & magicui

## 📊 目录结构

```bash
├── blog                           # 博客
│   ├── first-blog.md
├── docs                           # 文档/笔记
│   └── doc.md
├── data
│   ├── feature.tsx                # 特点
│   ├── friends.tsx                # 友链
│   ├── projects.tsx               # 项目
│   ├── skills.tsx                 # 技术栈
│   ├── resources.tsx              # 资源
│   └── social.ts                  # 社交链接
├── i18n                           # 国际化
├── src
│   ├── components                 # 组件
│   ├── css                        # 自定义CSS
│   ├── pages                      # 自定义页面
│   ├── plugin                     # 自定义插件
│   └── theme                      # 自定义主题组件
├── static                         # 静态资源文件
│   └── img                        # 静态图片
├── docusaurus.config.ts           # 站点的配置信息
├── sidebars.ts                    # 文档的侧边栏
├── package.json
├── tsconfig.json
└── pnpm-lock.yaml
```

## 📥 运行

```bash
git clone https://github.com/hhhh-wang/blog.git
cd blog
pnpm install
pnpm start
```

构建

```bash
pnpm build
```

## 📷 截图

![首页](https://bianliangrensheng.cn/gImage/title/blog-index.png)

## 📝 许可证

[MIT](./LICENSE)

