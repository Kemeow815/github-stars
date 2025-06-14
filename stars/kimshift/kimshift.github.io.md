---
project: kimshift.github.io
stars: 3
description: |-
    个人博客集成自定义主题-vitepress
url: https://github.com/kimshift/kimshift.github.io
---

### 项目介绍

- 使用 vitepress 搭建的个人博客网站

### KimShift 博客

- 记得要奔走在自己的热爱里 🌹

### `Kimshift 空间`博客预览

> github 预览地址：[https://kimshift.github.io](https://kimshift.github.io)

**白嫖有罪，如有帮助，点赞收藏！**

### 项目介绍

- 知识点复习和经验总结（不断完善中，欢迎加入！）
- 技术栈知识点笔记总结（知识小结）
- 个人牢骚发布点（生活随笔）
- 其它...

### 项目运行

- node 环境：`v20.12.2`
- 在项目文件夹下执行命令，安装依赖：`pnpm i`
- 在项目文件夹下执行命令，运行项目：`pnpm start`
- 编译完成访问：`http://localhost:5173`

### 项目架构

```lua
##需要自己写主题样式的话，在.vuepress/ 下新建theme文件夹并按如下目录布局

notebook
├─── .vitepress    配置目录
│      ├── cache       开发运行时缓存文件
│      ├── dist        打包后的静态资源
│      └── config      配置文件目录
│      │    ├── giscus     giscus评论配置
│      │    ├── head       网站头部配置
│      │    ├── nav        导航栏配置
│      │    └── theme      主题配置
│      ├── theme       自定义主题目录
│      │    ├── components 组件
│      │    ├── constants  常量
│      │    ├── directives 指令
│      │    ├── hooks      钩子
│      │    ├── layout     布局
│      │    ├── stores     pinia状态管理
│      │    ├── styles     样式
│      │    ├── utils      工具类
│      │    ├── App        入口界面
│      │    ├── index      入口配置
│      │    └── style      主题样式修改
│      └── config.mjs      站点配置文件
├─── docs       内容模块
│    ├── about      关于博客文档
│    ├── new file   需要新增博客->在docs目录下新增.md文件即可
│    ├── new cate   相关推荐文档会跟当前文档目录关联
│    ├── public     静态资源目录
│    │   ├── img            图片资源
│    │   ├── js             js资源
│    │   └── favicon.ico    网站图标
│    └── index.md   首页
├─── .gitignore     git忽略配置
├─── package.json   项目依赖包
├─── pnpm-lock.sh   pnpm 依赖包锁定文件
└──  README.md      项目说明
```

### 约定路由模式

| 文件的相对路径    | 页面路由地址 |
| ----------------- | ------------ |
| `/index.md`       | `/`          |
| `/config.md`      | `/config`    |
| `/about/index.md` | `/about/`    |

### 如何使用

对准备发布的文章（Markdown 格式），放置在项目`docs/`目录下，并在 Markdown 文件头部添加以下元素，
项目发布后会自动识别发布时间、标签、分类、是否开启评论、是否置顶、是否精选、是否发布等一系列状态。

下面是关键字说明及参考示例：

### 开始编写 markdown

- 参考示例：

```yaml
---
date: 发布时间
tags:
 - 标签名
categories:
 - 分类名
---
# 文章标题

[[toc]]

- 这里可以写`摘要`等其它

## 正式开始你的markdown

- 正文内容...
```

