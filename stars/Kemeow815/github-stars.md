---
project: github-stars
stars: 2
description: |-
    获取你所有的星标仓库，并将它们的 README 文件保存为 Markdown 格式。
url: https://github.com/Kemeow815/github-stars
---

# GitHub Stars

获取你所有的星标仓库，并将它们的 README 文件保存为 Markdown 格式。

## 功能特点

- 自动获取所有星标仓库信息
- 将 README 文件转换并保存为 Markdown 格式
- 保留仓库的基本信息（项目名、星标数、描述等）
- 每周自动运行备份（通过 GitHub Actions）
- 包含错误处理和重试机制

## 使用方法

1. [Fork](https://github.com/ccbikai/github-stars/fork) 此仓库
2. 创建不过期的 Fine-grained personal access tokens，需要的权限
   1. User permissions
      - Read access to starring
   2. Repository permissions
      - Read access to metadata
      - Read and Write access to code
3. 配置 GitHub Actions 密钥 `GH_TOKEN`
4. 运行 Actions

