---
project: VitePress_butterfly
stars: 4
description: |-
    butterfly theme of VitePress
url: https://github.com/57Darling02/VitePress_butterfly
---

# VitePress-Butterfly 主题

基于VitePress和Element Plus的卡片式仿butterfly主题。

##  特性

- 基于 VitePress 1.6.3 + Vue 3 构建
- 集成 Element Plus 组件库
- 响应式布局和动态导航栏
- 自定义主题样式系统
- 内置文章卡片、标签云等组件
- SEO 友好配置
- 静态资源自动优化

##  快速开始

### 安装依赖
```bash
npm install
```
开发模式

```bash
npm run dev
```
构建生产版本
> 这将生成构建到docs目录，可以直接部署到GitHub Pages


```bash
npm run build:docs
```
## 配置指南
修改 site_config.ts进行主题配置：


```javascript
export default {
    // VitePress 站点基本配置,必填，允许留空
    site_name: "My Awesome Site",
    site_description: "这是一个使用 VitePress 构建的文档站点。",
    site_url: "/",
    author: '57Darling02',
    
    // 首页配置
    home:{
        mainTitle:"My Awesome Site",
        subTitles:['世界上只有一种英雄主义','那就是在认清生活的真相后','依然热爱生活'],//打字机效果的副标题，使用字符串列表
    },
    
    // 侧边简介卡
    avatar: "https://resource-un4.pages.dev/article/yjtp.webp",
    name: '57Darling02',
    position: '全栈开发、优化算法爱好者',
    bio: '红红火火恍恍惚惚',
    socialLinks: [
      {
        name: 'GitHub',
        icon: 'fa-brands fa-github',
        url: 'https://github.com/57Darling02/'
      }
    ],
    footer: {
        message: 'Released under the MIT License.',
        copyright: 'Copyright © 2025-present My Awesome Site'
    }
}

```
### 目录结构

```plainText
Blog/                   # 项目根目录
├── .vitepress/         # 主题组件 不会为这部分提供文档 (一般不用动)
│   ├── theme/          
│   ├── config.mjs   
│   ├── index.js
│   └── ...   
├── site_config.ts     # 站点配置 **自定义的配置，主要修改这个文件来配置站点信息**
├── posts/             # Markdown文章 **文章放这里**
├── public/            # 静态资源
└── package.json       # 依赖配置 (一般不用动)
```
### 文章规范

```markdown
---
title: 文章标题
date: 2024-03-20
author: 作者
layout: doc # 可选布局
---
```
贡献
欢迎贡献代码和反馈问题。

### 部署

- 在public文件夹中的CNAME写好域名
- 配置好自己域名的DNS为github Page域名（自行搜索）

##### 工作流构建（推荐）

1. 打开.github workflow 复制deploy.yml内容
	![image-20250310101611742](https://resource-un4.pages.dev/article/image-20250310101611742.png)
1. 在github page 创建工作流粘贴使用即可。

优点：只需要修改posts文件夹内容，上传即可。


##### 本地构建

1. 构建生产版本

```bash
npm run build:docs
```

2. 上传到github
3. 配置GitHub Page

![1741082221235](https://resource-un4.pages.dev/article/1741082221235.png)

##### 



