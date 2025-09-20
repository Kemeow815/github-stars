---
project: blog
stars: 3
description: |-
    一个基于 Next.js 的个人博客项目，不需要数据库，可以部署Vercel或者个人服务器
url: https://github.com/Zwanan-github/blog
---

# Blog

## 简介

一个基于 Next.js 的个人博客项目，不需要数据库，可以部署Vercel或者个人服务器

### 环境准备

在开始之前，请确保已经安装以下软件：

*   [Node.js](https://nodejs.org/) 
*   [pnpm](https://www.npmjs.com/)
*   [Git](https://git-scm.com/)

### 安装步骤

1.  **克隆仓库**

    ```bash
    git clone https://github.com/Zwanan-github/blog.git
    ```

2.  **进入项目目录**

    ```bash
    cd blog
    ```

3.  **安装依赖**

    ```bash
    pnpm i
    ```

4.  **创建 .env 文件, 并根据 .env.example 修改环境变量**
    ```bash
    touch .env
    ```

### 启动项目

```bash
pnpm dev
```

## 使用方法

以下是一些使用示例：

- 删除 content/mds 和 public/images 中的文件
- 在 content/mds 中创建 `[$name]-[$time].md` 格式的 Markdown 文件
- 创建的文件保存在 public/images 中
- 创建自己的 Mcp-server 实例, [例子](https://github.com/Zwanan-github/blog-mcp-server)

## 许可证

本项目使用 MIT 许可证，详情请见 [LICENSE](LICENSE) 文件。

