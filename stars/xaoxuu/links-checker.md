---
project: links-checker
stars: 2
description: |-
    CI项目：自动检查issue中填写的链接是否有效，可用于动态友链、示例博客
url: https://github.com/xaoxuu/links-checker
---

# 链接检查器

一个用于检查仓库中失效链接的 GitHub Action。

## 使用方法

将以下内容添加到你的工作流文件（例如：`.github/workflows/reachability-checker.yml`）中：

```yaml
name: Reachability Checker

# Controls when the workflow will run
on:
  issues:
    # 新增（打开）/编辑/关闭/重新打开/设置标签/移除标签
    types: [opened, edited, closed, reopened, labeled, unlabeled]
  # 手动触发
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  # This workflow contains a single job called "build"
  reachability-checker:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest
    permissions:
      contents: write
      issues: write
    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4
      # 检查链接状态
      - name: Check Reachability
        uses: xaoxuu/links-checker@main
        with: # 全部可选
          checker: 'reachability' # theme: 主题检查， reachability: 链接可访问性检查
          exclude_issue_with_labels: '审核中, 白名单, 缺少互动, 缺少文章' # 具有哪些标签的issue不进行检查
          retry_times: 3 # 重试几次
          accepted_codes: '200,201,202,203,204,205,206,300,301,302,303,304,307,308' # 哪些状态码可以接受（认为可访问）
          unreachable_label: '无法访问' # 不能访问时，会贴上什么标签
     
      ... 接下来调用 issues2json 再生成一次数据
```

## 配置

你可以通过以下输入项配置此 Action：

### 通用配置

- `exclude_issue_with_labels`: (可选) 排除标签，带有这些标签的 issue 将跳过不进行检查。默认值: `'审核中, 白名单'`
- `retry_times`: (可选) 重试次数。默认值: `'3'`
- `accepted_codes`: (可选) 可接受的状态码，这些状态码不会被认为网站异常。默认值: `'200,201,202,203,204,205,206,300,301,302,303,304,307,308'`
- `unreachable_label`: (可选) 无效标签：无法访问。默认值: `'无法访问'`
- `github_token`: (可选) GitHub Token。默认值: `${{ github.token }}`

### 检查器类型

- `checker`: (可选) 检查器类型。可选值: `reachability` (检查目标网站是否可访问，状态码在 `accepted_codes` 中), `theme` (检查目标网站是否是对应主题)。默认值: `'reachability'`

### 友链检查器配置

- `friend_checker_invalid_label`: (可选) 无效标签：友链无效。默认值: `'未添加友链'`

### 主题检查器配置

- `theme_checker_meta_tag`: (可选) 主题检查器：meta 标签选择器。默认值: `'meta[theme-name="Stellar"]'`
- `theme_checker_content_attr`: (可选) 主题检查器：内容属性。默认值: `'content'`
- `theme_checker_version_attr`: (可选) 主题检查器：主题版本属性名。默认值: `'theme-version'`
- `theme_checker_invalid_label`: (可选) 无效标签：主题无效。默认值: `'主题无效'`


## 许可证

本项目采用 MIT 许可证 - 详情请参阅 [LICENSE](LICENSE) 文件。
