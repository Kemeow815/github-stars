---
project: vitepress-blog-sample
stars: 1
description: |-
    使用VitePress构建的极简博客主题
url: https://github.com/tuyazuo/vitepress-blog-sample
---


```
.
├─ .vitepress
│  ├─ theme
│  │  ├─ components         #组件
│  │  │  ├─ Archive.vue     #归档
│  │  │  ├─ Category.vue    #目录
│  │  │  ├─ Tags.vue        #标签
│  │  │  ├─ Home.vue        #主页
│  │  │  ├─ Layout.vue      #页面布局
│  │  │  └─ Comment.vue     #评论
│  │  ├─ custom.css         #样式
│  │  ├─ index.ts           #主题入口
│  │  └─ posts.data.ts      #文档数据收集
│  └─ config.mts            #配置文件
├─ index.md                 #主页页面
├─ pages                    #组件对应页面
├─ posts                    #文档目录
└─ package.json
```

## 主题扩展
极简、实用原则，不修改原主题，尽可能少地扩展。
- packages.json中配置"type": "module"
- *.data.ts文件，VitePress提供的数据加载功能，收集文档数据，是后面功能实现的基础。
- Layout 页面的布局文件，可以将自定义组件注入到插槽中，实现页面扩展。
- Archive、Category、Tags属于同一类型，只有少许代码差异。  
  使用了vue的Teleport功能，将标签内容放入右侧导览VPDocOutlineItem元素里。
- Comment 依赖于Cloudflare pages和d1实现的简单留言功能，不使用时可直接注释掉Layout中组件。

## Cloudflare
#### 以下是相关依赖包，不使用cloudflare时可移除  
- wrangler：cloudflare提供的命令行工具，用于快捷部署页面和操作数据库等
- @cloudflare/workers-types：类型文件，发现不加这个d1数据操作时会报错

#### 使用[Functions和d1数据库](https://developers.cloudflare.com/pages/functions/advanced-mode/)实现了简单的留言功能。
- 在配置文件中使用buildEnd，自动拷贝_worker.js(数据库操作代码)文件到构建目录中
- 需要在Pages--项目名--设置--函数--D1数据库绑定 中配置，绑定相关数据库（变量为DB，对应_worker.js中env.DB字段）

#### 创建数据表  
可以提前写好sql文件（或使用数据库GUI工具设计并导出结构），执行以下语句创建  
npx wrangler d1 execute [database] --remote --file=./schema.sql

#### 自动上传发布页面
npx wrangler pages deploy ./.vitepress/dist --project-name blog --branch main  
注意：带--branch main才会发布到生成环境，否则会发布到测试环境
