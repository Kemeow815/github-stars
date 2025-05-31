---
project: prologue.dev
stars: 41
description: |-
    Next.js 14 + Tailwindcss + Contentlayer + Markdown Blog
url: https://github.com/hxlog/prologue.dev
---

# Prologue Blog

Next.js 14 + Tailwindcss + Contentlayer + Markdown Blog

这是一个由Next.js生态拼凑而生的博客（笔者没有任何技术）。

## Features

- Content Focused, Contentlayer +MD/MDX
- Adaptive dark mode
- Full SEO, Opengraph + JSON-LD + RSS
- Lightweight search engine, powered by Fuse.js

- 专注于内容创作，支持markdown/mdx
- 自适应黑暗模式
- 完整的SEO支持，支持Opengraph、JSON-LD和RSS
- 轻量级的搜索引擎，Fuse.js实现全文搜索和模糊搜索

![Index Screenshot](/public/static/images/Index-Screenshot.jpg)

![Post Screenshot](/public/static/images/Post-Screenshot.jpg)

## Get Started

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fhxlog%2Fprologue.dev)

```
npm install
```

You can easily customize this site, all configurations are in `/data`,static files are in `/public`

你可以很容易自定义网站，所有配置文件都在`/data`目录，静态文件存放在`/public`

## Configuration

Post Frontmatter

```yaml
---
title: title
description: description
publishDate: 2022-11-13
(required)

lastmod: 2023-07-02
featured: true
tags: ["tag1",tag2]
image: /static/photos/06.jpg
imageDesc: This is a static file
(optional)
---
```

Page Frontmatter

```yaml
title: title
description: description
(required)
```

