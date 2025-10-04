---
project: template-web
stars: 82
description: |-
    个人网站模板，使用Nextjs(React)开发
url: https://github.com/996wuxian/template-web
---

<p align="center"><img src="/public/images/work1.jpg" /></p>

<h1 align="center">template-web</h1>

This template should help get you started developing with React in Next.js.
<br>
这个模板应该有助于你开始在 Next.js 中使用 React 进行开发。

> [!NOTE]
> If you think `TemplateWeb` is helpful to you, or you like my project, please give my project a ⭐️ on GitHub. Your support is the driving force for me to continue to improve! Thank you for your support! If there are any areas that are not good enough, please raise an issue and I will improve it!
> <br>
> 如果你认为 TemplateWeb 对你有帮助，或者你喜欢我的项目，请给我的项目一个 ⭐️ 在 GitHub 上。您的支持是我不断改进的动力！感谢您的支持！如果有什么地方不够好，请提出 issue，我会改进的！

## Introduction

该模板使用 Next.js + React + Prisma + Pusher 搭建，配置了请求封装、Prisma 连接、Pusher 连接、主题切换、移动端适配、封装了对应的 svg-icon 组件、可以通过使用`svgIcon name="..."`引入对应的 svg 图标，对应[Svg 图标预设](https://yesicon.app/logos/?lang=zh-hans)，希望这个可以作为您的初始化项目模板，供您拓展和自定义属于您的项目。

## Node Version

node 版本: v20.10.0
pnpm 版本: 8.8.0

## 运行方式

1. 下载这个项目
2. run `pnpm i`
3. run `pnpm dev`

## 目录说明

- `prisma/schema.prisma`

  - Prisma 的配置文件，用于定义数据库模型。

- `public`

  - 静态资源目录，用于存放静态资源。

- `scripts`

  - 脚本目录，用于存放脚本。

- `service`

  - 请求方法，接口方法。

- `src/blogs`

  - 存放 md 文件，项目会读取这个目录作为文章列表显示。

- `src/components`

  - 存放组件，包含弹窗、热力图等。

- `src/contexts/ThemeContext.tsx`

  - 主题上下文，用于切换主题。

- `src/lib/prisma.ts`

  - Prisma 的声明文件。

- `src/lib/pusher.ts`

  - Pusher 的声明文件。

- `src/pages_app.tsx`

  - Next.js 的入口文件。

- `src\components\LoadingAnimation.tsx`

  - 加载动画组件。

- `src/pages/index.tsx`

  - 首页代码。

- `src/pages/works.tsx`

  - 作品页面代码。

- `src/pages/blog.tsx`

  - 文章集页面代码。

- `src/pages/chat.tsx`

  - 聊天室页面代码。

- `src/pages/api/comments.ts`

  - 获取评论接口代码。

- `src/pages/api/reactions.ts`

  - 获取文章点赞数接口代码。

- `src/pages/api/chat`

  - 聊天室接口代码。

- `src/data/works.ts`

  - 作品数据。

- `src/data/tagConfigs.ts`

  - 标签配置数据。

- `src/data/experience.ts`

  - 经历数据。

- GitHubHeatmap 使用说明：
  - `GitHubHeatmap username="996wuxian" year={2025}`
  - 热力图只需要在这替换你的 username 即可

## vercel 部署说明

1. 创建一个 vercel 账号(vercel 官网:https://vercel.com/)
2. 连接你的 github 仓库
3. vercel 创建一个 neon 数据库(neon 官网:https://neon.com/)
4. neon 数据库和项目连接
5. 部署
6. 配置数据库连接字符串到 vercel 的环境变量中(一般将数据库跟项目进行连接后，重新部署就可以有环境变量了)
7. 将 DIRECT_URL(即 neon 数据库的连接字符串) 也补充到环境变量中
8. 配置域名说明文档:https://vercel.com/docs/domains/working-with-domains/add-a-domain#ip-diff-alerts

## Prisma 连接说明

1. 在项目根目录的.env 文件中将 vercel 创建的 neon 数据库连接字符串配置如下 neon 的连接字段:
   DATABASE_URL="your-connection-string"
   DIRECT_URL="your-connection-string"

2. 运行 `pnpm run push-db` 命令，将数据库结构推送到 neon 上
3. 运行 `pnpm run generate` 命令，生成新的客户端代码

## Pusher 连接说明

1. 创建一个 pusher 账号(pusher 官网:https://pusher.com/)
2. 创建一个 pusher 应用
3. 配置 pusher 应用的连接字段填入.env 文件中
4. 将项目根目录的.env 文件的字段添加到 vercel 的环境变量中

## 注意

1. 如果修改表结构，则需要重新运行 `pnpm run push-db` 命令，将数据库结构推送到 neon 上
2. 上传到您的 github 仓库时，请将.env 文件添加到.gitignore 文件中
3. 这个只是基础模板，各位发挥自己的想象创造力打造吧！
4. 如果遇到不懂的，请在 qq 群内联系我: 916088073

