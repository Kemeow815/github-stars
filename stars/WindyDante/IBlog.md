---
project: IBlog
stars: 1
description: |-
    个人博客主页
url: https://github.com/WindyDante/IBlog
---

# Blog Home Page

## 项目简介

这是一个使用 Vue 3 + Vite + TailwindCSS 构建的个人主页。本项目采用现代前端技术栈，提供了一个简洁、响应式的个人主页模板。

### 技术栈

- Vue 3 - 渐进式 JavaScript 框架
- Vite - 下一代前端构建工具
- TailwindCSS - 实用优先的 CSS 框架
- Docker - 容器化部署方案

## 开发指南

### 环境要求

- Node.js >= 18.0.0
- npm >= 8.0.0

### 本地开发

1. 克隆项目并安装依赖：

```bash
npm install
```

2. 启动开发服务器：

```bash
npm run dev
```

3. 构建生产版本：

```bash
npm run build
```

## 方式一：Docker 部署

本项目支持多种 Docker 部署方式，您可以根据实际需求选择合适的部署方案。

### 一：本地构建镜像

```bash
docker build -t eastwind996/windhub:latest .
```

### 二：直接拉取镜像

```bash
docker pull eastwind996/windhub:latest
```

### 三：使用 Docker 命令运行

```bash
docker run -d -p 6556:80 --restart=always --name windhub eastwind996/windhub:latest
```

## 方式二：使用 Docker Compose 运行

1. 创建一个新目录并将 `docker-compose.yml` 文件放入其中
2. 在该目录下执行以下命令启动服务：

```bash
docker-compose up -d
```

服务启动后：
- 容器会在后台运行
- 自动从 Docker Hub 拉取镜像 `eastwind996/windhub:latest`
- 通过服务器的 6556 端口访问网站
- 使用 `docker-compose down` 命令停止服务

## 访问

部署完成后，可以通过以下地址访问网站：

- 本地开发环境：`http://localhost:5173`
- Docker 部署环境：`http://ip:6556`
