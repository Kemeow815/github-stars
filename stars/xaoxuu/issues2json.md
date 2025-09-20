---
project: issues2json
stars: 1
description: |-
    CI项目：自动获取issue中第一段json保存为文件，支持多种排序和过滤
url: https://github.com/xaoxuu/issues2json
---

# Issues to Json

Generate JSON from GitHub issues

把每个 issue 中第一个 json 提取出来合并导出为一个 json 文件。

## Inputs

| Name | Description | Required | Default |
|---|---|---|---|
| `data_path` | 数据文件存储路径 | `false` | `/v2/data.json` |
| `sort` | Issue排序方式和方向 (例如: created-desc, updated-asc, version-desc) | `false` | `posts-desc` |
| `exclude_issue_with_labels` | 具有哪些标签的Issue需要排除 (逗号分隔) | `false` | `审核中` |
| `hide_labels` | 生成的json中去除哪些标签 (逗号分隔) | `false` | `白名单` |


## Usage

To use this action, add the following step to your GitHub Workflow:

```yaml
name: Generate Issues JSON
on:
  schedule:
    - cron: '0 0 * * *' # Runs daily at midnight UTC
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Generate JSON from Issues
        uses: xaoxuu/issues2json@main
        with: # 全部可选
          sort: 'posts-desc'
          exclude_issue_with_labels: '审核中'
          hide_labels: '白名单'

      - name: Commit files
        run: |
          git config --local user.email "action@github.com"
          git config --local user.name "GitHub Action"
          git add .
          git commit -m "Update issues data"
          git push
```
