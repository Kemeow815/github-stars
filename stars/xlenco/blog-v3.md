---
project: blog-v3
stars: 3
description: |-
    🚧Beta Preview🚧 Zhilu's blog v3.
url: https://github.com/xlenco/blog-v3
---

# 纸鹿摸鱼处

![框架](https://img.shields.io/badge/框架-Nuxt-00DC82?logo=Nuxt.js)
![CMS](https://img.shields.io/badge/CMS-Nuxt%20Content-00DC82?logo=Nuxt.js)
![部署平台](https://img.shields.io/badge/部署平台-Vercel-000000?logo=Vercel)
![访问统计](https://img.shields.io/badge/访问统计-Umami-000000?logo=Umami)
![代码风格](https://img.shields.io/badge/代码风格-ESLint-4B32C3?logo=ESLint)
![代码风格](https://img.shields.io/badge/代码风格-Stylelint-263238?logo=Stylelint)

我的第三代个人博客，于 2024 年 8 月 11 日上线。

## 使用本主题的博客

- [纸鹿摸鱼处 @L33Z22L11](https://blog.zhilu.cyou/) · [开发经历](https://blog.zhilu.cyou/2024/blog-using-nuxt)
- [希乐博客 @Xlenco](https://blog.xlenco.top/)
- [SteinsNote @Labmem-00](https://blog.labmem.chat/) · [迁移经历](https://blog.labmem.chat/2024/beforeeverything)
- [月空人 @Whbbit1999](https://whbbit.cn/) · [迁移评价](https://whbbit.cn/posts/2025/why-migrate-to-nuxt)
- [地球驿站 @mugzx](https://blog.mugzx.top/) · [迁移记录](https://blog.mugzx.top/)
- [喵落阁 @Kemeow815](https://blog-v3.kemeow.top/)
- [梦爱吃鱼 @JLinmr](https://blog.ruom.top/)
- [Mikuの极光星 @PaloMiku](https://blog.sotkg.com/)
- [BiuXin-s Blog](https://zhilu.biuxin.com/)

## 特性

[主题特性](https://blog.zhilu.cyou/theme) · [组件示例](https://blog.zhilu.cyou/previews/example)

## 目录结构

项目使用 Nuxt 4 项目目录结构，可以参照 [Nuxt 3 目录结构（左侧栏有导航）](https://nuxt.com/docs/guide/directory-structure/app)。

```sh
.
├── app # 前端
│   ├── assets # 资源文件
│   ├── components # 组件
│   │   ├── content # MDC组件
│   │   ├── partial # 微型组件
│   │   ├── widget # 侧边栏组件
│   │   ├── zhilu # 个人标识组件
│   │   └── ... # 布局组件
│   ├── composables # Vue 组合式函数
│   ├── pages # 页面
│   │   ├── [...slug].vue # 正文、404页面
│   │   ├── page.vue # 首页
│   │   ├── page/[[id]].vue # 首页动态路由
│   │   ├── archive.vue # 归档
│   │   ├── link.vue # 友链
│   │   └── preview.vue # 预览的文章
│   ├── plugins # Nuxt / Vue 插件
│   ├── stores # Pinia 状态管理
│   ├── types # 类型定义
│   ├── utils # 工具函数
│   ├── app.config.ts # 前端响应式配置★
│   ├── app.vue # 基本布局
│   ├── error.vue # 意外错误页
│   ├── friends.ts # 友链★
│   └── subscriptions.ts # 单向订阅/推荐网站★
├── content # 文章
│   ├── posts # 文章
│   ├── previews # 预览文章，可被站内搜索
│   ├── link.md # 友链要求
│   └── theme.md # 主题介绍
├── patches # npm 包补丁
├── public # 静态资源，生成在站点根目录
│   └── fonts # 字体
├── server # 服务端
│   ├── api # 接口
│   │   └── stats.get.ts # 博客静态统计
│   ├── plugins # Nitro 插件
│   │   ├── anti-mirror.ts # 恶意反代跳转
│   │   └── fix-post.ts # 修复文章时区/链接
│   └── routes # 路由
│       └── atom.xml.get.ts # Atom 订阅源
├── blog.config.ts # 博客静态公共配置★
├── nuxt.config.ts # Nuxt 配置
└── redirects.json # 旧站点重定向配置
```

## 快速开始

### 安装依赖

```sh
pnpm i
```

### 运行开发环境

```sh
pnpm dev
```

### 初始配置

为避免误会，应当更改一些配置信息以和我的博客网站区分：

- 删除原有文章：`content/` 目录下仅保留 `link.md`，`app.config.ts` 中将 `footer.nav[2].items[1].url` 由 `/theme` 改为 `https://blog.zhilu.cyou/theme`（确保通过链接检测）。
- 更换服务配置：`blog.config.ts` 中的 Umami 站点统计、Cloudflare Insights 统计、Twikoo 评论服务源需要注释或更换。
- 个人信息：`blog.config.ts` 中的站点信息、`app.config.ts` 中的页脚导航、出生年份等。
- 其他应当被善意认为有必要修改的文件和配置字段（参阅“目录结构”一节）。

### 创建文章

```sh
pnpm new my-post-title
```

### 构建生产环境

```sh
pnpm generate
pnpm preview
```

### 部署指南

推荐使用 Vercel 进行部署，同时也支持 Netlify、Cloudflare Pages 等平台。建议采用静态（SSG）部署方式，我的部署配置如下：

- 构建命令: `pnpm generate`/`nuxt generate`
- 输出目录: `dist`（与Nuxt预设相同）
- 安装命令: `pnpm i`（一般会自动检测）

如果直接使用平台提供的“Nuxt”预设部署，那么会变成 SSR 模式，需要调整部署命令，请参阅 Nuxt 官方文档的 [部署](https://nuxt.com/docs/getting-started/deployment) 部分。

#### 疑难解答

- Vercel 先前创建的项目需要 [手动指定 pnpm 10](https://vercel.com/docs/builds/configure-a-build#corepack)。
- Cloudflare Pages 部署项目需要配置 `NODE_VERSION` 环境变量为较新的版本，如 `22.14.0`。

## 贡献

欢迎参与项目：如果有具体问题或功能建议，可以发起 Issue；如果愿意在已确定的方向上增加功能或修复问题，可以提交 Pull Request。

### 使用答疑

使用需要具备一定的前端**项目基础**。如果你不确定代码是否有问题，可以加入 QQ 群 `169994096` 讨论（也欢迎闲聊），我很乐意在空闲时解答问题。

## 许可证

- 项目本体：[MIT](LICENSE)
- 博客文章：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh-hans)
- 请完成必要的配置与修改后再部署项目，**不得以“纸鹿”或任何与我相关的名义发布“镜像”网站**，否则我将设法与你联系。
- 希望你在页脚保留此项目链接，助力开源传播。

