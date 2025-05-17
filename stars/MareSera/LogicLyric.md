---
project: LogicLyric
stars: 6
description: |-
    一个基于Astro的简洁好看好用的博客模板
url: https://github.com/MareSera/LogicLyric
---

# LogicLyric

> 一个高中生自主开发的博客模板

[预览](https://LogicLyric.maresera.top/)
![预览](https://LogicLyric.maresera.top/)

## ✨特性

· ✅ 白天 / 黑夜 模式可用

· ✅🛠️ 博客易上手

· ✅📚 支持Markdown

## ✒️ 文章信息

|    名称     |   含义   | 是否必要 |
| :---------: | :------: | :------: |
|    title    | 文章标题 |    是    |
| description | 文章简介 |    是    |
|   pubDate   | 文章日期 |    是    |
|    image    | 文章封面 |    否    |
| categories  | 文章分类 |    否    |
|    tags     | 文章标签 |    否    |
|    badge    | 文章徽标 |    否    |
|    draft    | 草稿状态 |    否    |


## 🔭使用：

### 下载

直接克隆本项目后，使用终端运行`npm run dev`然后访问`http://localhost:4321/`即可直接预览本项目

### 部署

使用vercel部署本项目，记得要在vercel的环境变量中添加`GITHUB_TOKEN`

_具体教程请自行搜索_

### 首页

在pages/index.astro中修改首页内容

### 项目页

在pages/projects/index.astro中修改项目页内容

### 友链页

在pages/friends.astro中修改友链页内容


### 关于页

在pages/about.astro中修改关于页内容

### 导航栏

在components/Nav.astro中修改导航栏内容

### 文章

在content/posts中编写文章

> 注意！本博客暂时无法使用公式，使用公式会导致无法渲染文章

### 说说

在content/posts中编写说说，一条说说为一篇md文档

```md
---

mood: 😎   #emoji
date: 2025-05-01   #日期
tags: [demo]   #标签

---
```

### Github足迹

在根目录下的`.env`文件中填写Github token

在部署至vercel时需要添加Github token的环境变量
