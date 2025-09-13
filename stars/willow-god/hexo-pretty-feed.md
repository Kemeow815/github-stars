---
project: hexo-pretty-feed
stars: 3
description: |-
    😛实现更加美观的Feed订阅文件！
url: https://github.com/willow-god/hexo-pretty-feed
---

# hexo-pretty-feed

[![NPM version](https://badge.fury.io/js/hexo-pretty-feed.svg)](https://www.npmjs.com/package/hexo-pretty-feed)

生成美观的 Atom 1.0 或 RSS 2.0 Feed，支持插入 XSL 样式美化输出。

本插件基于 [hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed) 修改，增加了 `pretty_atom_file` 与 `pretty_rss2_file` 配置，用于在 Feed 顶部插入 `<?xml-stylesheet ...?>`。

## 安装

```bash
npm install hexo-pretty-feed --save
```

- Hexo 4+：使用 2.x
- Hexo 3：使用 1.x
- Hexo 2：使用 0.x

## 使用

在你文章的 [Front-matter](https://hexo.io/zh-cn/docs/front-matter) 中，可以选择添加 `description`、`intro` 或 `excerpt` 字段来自定义摘要。若未设置，插件将使用摘要或前 140 字符作为摘要内容。

## 配置

你可以在 `_config.yml` 中添加如下配置：

```yaml
# RSS订阅源
# hexo-pretty-feed
feed:
  enable: true
  type: atom
  path: atom.xml
  limit: 25
  content: false
  content_limit: 40
  pretty_atom_file: /config/feed/atom.xsl
  pretty_rss2_file: /config/feed/rss2.xsl
```

### 可用配置项

- **enable** - 启用插件。默认为启用。
- **type** - Feed 类型。可为 `atom`、`rss2`，或同时输出多个类型（数组形式）。默认：`atom`
  ```yaml
  feed:
    type:
      - atom
      - rss2
    path:
      - atom.xml
      - rss2.xml
  ```
- **path** - 输出路径。若配置多个类型，则顺序需与 `type` 一一对应。
- **limit** - Feed 中最多包含的文章数。设为 `0` 或 `false` 表示不限制。
- **hub** - PubSubHubbub 的 hub 地址（可选）。
- **content** - 是否在 Feed 中包含完整文章内容。
- **content_limit** - 若未包含全文，此项设置摘要字符数。
- **content_limit_delim** - 设置字符截断的分隔符，只在启用 `content_limit` 时生效。
- **order_by** - 排序方式。默认：`-date`
- **icon** - Feed 图标。默认为使用邮箱对应的 gravatar。
- **autodiscovery** - 是否添加自动发现标签。默认启用。
- **template** - 自定义模板路径，可为字符串或数组（与 type 一一对应）。
  ```yaml
  feed:
    type:
      - atom
      - rss2
    template:
      - ./source/custom.xml
  ```
- **pretty_atom_file** - 插入 Atom Feed 顶部的样式文件路径（如：XSL 文件），建议使用相对路径。留空则不插入。
- **pretty_rss2_file** - 插入 RSS2 Feed 顶部的样式文件路径。留空则不插入。

## 示例模板输出（atom.xml 顶部）

```xml
<?xml version="1.0" encoding="utf-8"?>
<?xml-stylesheet type="text/xsl" href="/config/feed/atom.xsl"?>
<feed xmlns="http://www.w3.org/2005/Atom">
```

如需美化 RSS2，则使用 `pretty_rss2_file` 并在 `rss2.xml` 模板中插入。

---

欢迎在 [GitHub](https://github.com/你的用户名/hexo-pretty-feed) 提交反馈与 PR ❤️
