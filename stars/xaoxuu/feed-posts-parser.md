---
project: feed-posts-parser
stars: 1
description: |-
    CI项目：解析issue中的友链RSS地址，获取最新发布的文章并更新到issue中
url: https://github.com/xaoxuu/feed-posts-parser
---

# feed-post-parser

解析友链 RSS 地址，获取最新发布的文章，并将其转换为统一的格式，方便聚合和展示。

## 项目简介

`feed-post-parser` 是一个用于从 Issue 中解析 RSS/Atom/JSON Feed 地址并填充数据回 Issue 的工具，旨在从友链或博客订阅中提取最新的文章信息。它可以帮助您：

- 自动抓取指定 Feed 源的最新内容。
- 统一不同 Feed 格式的数据结构。
- 方便地集成到其他应用或服务中，用于内容聚合、数据分析等。

## 如何使用

该项目作为一个 GitHub Action 运行，或者作为独立的 Node.js 脚本运行。具体使用方式请参考 `action.yml` 或 `src/main.js` 文件。

例如，作为 GitHub Action 使用时，您可以在工作流中配置：

```yaml
name: Feed Posts Parser

on:
  workflow_dispatch: # Allows manual triggering
  schedule:
    - cron: '0 21 * * *' # Runs daily at 21:00 UTC

jobs:
  feed-parser:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - name: Checkout code
        uses: actions/checkout@v4
        with:
          ref: output
      - name: Run Feed Post Parser Action
        uses: xaoxuu/feed-posts-parser@main
        with:
          posts_count: '2'
          date_format: 'YYYY-MM-DD HH:mm'
      ...
```

### 3. 配置

根据您的需求，可能需要修改 `src/main.js` 或 `action.yml` 中的配置。

## 贡献

欢迎提交 Issue 或 Pull Request。

## 许可证

本项目采用 [MIT License](LICENSE) 许可。

