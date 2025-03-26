---
project: VitePress_butterfly
stars: 4
description: |-
    butterfly theme of VitePress
url: https://github.com/57Darling02/VitePress_butterfly
---

# VitePress-Butterfly 主题

基于VitePress和Element Plus的卡片式仿butterfly主题。

**演示站点：**[Vitepress-Butterfly | VitePress-Butterfly (57d02.cn)](https://vitepress.57d02.cn/)
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
修改 .vitepress/config.mjs 进行主题配置：


```javascript
export default defineConfig({
  title: "站点标题",
  themeConfig: {
    // 导航菜单配置
    menuItems: [
      {
        label: '文档',
        icon: 'fa-regular fa-file',
        link: '/guide'
      }
    ],
    
    // 作者信息
    defaultauthor: '作者名称',
    
    // 社交链接
    socialLinks: [
      { 
        name: 'GitHub',
        icon: 'fa-brands fa-github',
        url: 'https://github.com/yourprofile'
      }
    ],
    
    // 页脚配置
    footer: {
      message: "备案信息",
      copyright: "Copyright ? 2024-present Your Name"
    }
  }
})
```
### 目录结构

```plainText
Blog/
├── .vitepress/
│   ├── theme/          # 主题组件
│   ├── config.mjs      # 站点配置
├── posts/             # Markdown文章
├── public/            # 静态资源
└── package.json       # 依赖配置
```
### 文章规范

在 posts 目录中创建 .md 文件：


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

> 这将生成构建到docs目录，可以直接部署到GitHub Pages
>


```bash
npm run build:docs
```

2. 上传到github
3. 配置GitHub Page

![1741082221235](https://resource-un4.pages.dev/article/1741082221235.png)


