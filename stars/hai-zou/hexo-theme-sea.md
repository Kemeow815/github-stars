---
project: hexo-theme-sea
stars: 148
description: |-
    🐳 Hexo Theme | 博客主题
url: https://github.com/hai-zou/hexo-theme-sea
---

# Hexo Theme Sea
一款简约的 Hexo 博客主题！

![Hexo-Theme-Sea](https://github.com/user-attachments/assets/d337cf2c-4dcd-474e-a290-16746520de08)

## 在线预览
- Example: <https://hai-zou.github.io/hexo-theme-sea/>
- My Blog: <https://www.izou.top/>

## 特性
- 响应式，适配移动端
- 国际化，支持中英文
- 主题切换，支持暗黑主题模式
- SEO 友好
- 评论（Waline、Giscus）
- 搜索（Algolia）

## 评分
![score](https://github.com/user-attachments/assets/577df733-de8e-40c0-ab61-795b37c0274d)

## 应用

1、安装 npm 包

```bash
npm i hexo-theme-sea
```

2、应用主题

```yml
theme: sea
```

## 主题配置

> 创建 `_config.sea.yml` 主题配置文件

### 菜单栏

```yml
menu:
  - name: Posts # 名称
    url: /articles/ # 链接
```

### 首页配置

> 主页可配置展示 “推荐文章” 或者 “最近文章”。
> 注意：展示的推荐文章需要在文章的 `Front-matter` 中加上 `recommend: true`

```yml
home:
  hero:
    name: # 名称
    intro: # 个人简介
    avatar: # 头像
  posts: recent | recommend # recent: 最新文章 | recommend: 推荐文章
```

### 所有文章页

> 自定义一个文章页，可展示所有的文章，支持分页。
> 在菜单上配置 `/articles/` 路由即可，也可以自定义路径，注意切勿设置关键词 `posts` ，会出现问题。

```yml
articles:
  path: 'articles' # 路由
  per_page: 10 # 分页数
  order_by: -date # 文章排序
```

### 评论

```yml
comment:
  enable: # 是否启用
  type: # waline | giscus

# Waline https://waline.js.org/
waline:
  serverURL:
  options: # 配置项参考：https://waline.js.org/reference/client/props.html

# Giscus https://giscus.app/zh-CN
giscus:
  repo:
  repoid:
  category:
  categoryid:
  mapping:
  term:
  reactionsenabled:
  emitmetadata:
  inputposition:
  loading:
```

### 搜索

```yml
search:
  enable: # 是否启用
  type: # algolia

# Docsearch https://docsearch.algolia.com/apply/
algolia:
  appId: 
  apiKey: 
  indexName: 
```

### 友链

```yml
friends:
  - name: # 名称
    avatar: # 头像
    link: # 站点地址
    desc: # 描述
```

### 作品

```yml
works:
  - name: # 名称
    desc: # 描述
    tags: # 标签
      - tag1
      - tag2
      - tag3
    link: # 链接
    cover: # 预览图
```

### 社交链接

```yml
socialLink:
  - name: # 名称
    link: # 跳转链接
```

### Footer

```yml
footer:
  builtUpTime: # 建站时间 2020-05-20 13:14:00
```

### 主题色

```yml
primaryColor: '#10b981'
```

### 目录

```yml
tableOfContents:
  enable: true # 默认启用
```

## 基本配置

> 修改 `_config.yml` 配置文件  
> 参考 [Hexo 官方文档](https://hexo.io/zh-cn/docs/configuration)

### 代码高亮

移除原先的 `highlight`，改为使用 `prismjs`

v7.0.0以下：

```yml
# _config.yml
highlight:
  enable: false
prismjs:
  enable: true
  preprocess: true
  line_number: true
  line_threshold: 0
  tab_replace: ''
```

v7.0.0及以上：

```yml
# _config.yml
syntax_highlighter: prismjs
prismjs:
  preprocess: true
  line_number: true
  line_threshold: 0
  tab_replace: ''
```

## 文章配置

> 修改 `xxx.md` 文件

### Front-matter

```yml
title: # 文章标题
date: # 文章发布日期 2024-03-27 09:22:23
categories: # 文章分类
tags: # 文章标签
abstract: # 摘要
comments: # 是否展示评论，默认 true
sticky: # 置顶，按数值大小排序
```

### 友链模块

在页面中使用 `{% friends %}`，友链列表在 `_config.sea.yml` 中配置

### 自定义容器

```md
{% note info %}
This is an info box.
{% endnote %}

{% note warning %}
This is an info box.
{% endnote %}

{% note danger %}
This is an info box.
{% endnote %}
```

## 内置页面

- 归档页面：/archives/
- 分类页面：/categories/
- 标签页面：/tags/

## TodoList
- [ ] 本地搜索

