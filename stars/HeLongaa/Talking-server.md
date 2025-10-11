---
project: Talking-server
stars: 3
description: |-
    现代化的社交动态管理服务，基于 Cloudflare Workers，支持 Markdown、图片上传、标签管理。
url: https://github.com/HeLongaa/Talking-server
---

# Talking-server

![Cloudflare Workers](https://img.shields.io/badge/Cloudflare%20Workers-2025-orange.svg)
![JavaScript](https://img.shields.io/badge/JavaScript-ES2022-blue.svg)
![KV](https://img.shields.io/badge/Cloudflare%20KV-Storage-purple.svg)
![R2](https://img.shields.io/badge/Cloudflare%20R2-Storage-green.svg)
![Markdown](https://img.shields.io/badge/Markdown-Support-lightgrey.svg)
![License](https://img.shields.io/badge/License-MIT-red.svg)

> 现代化的社交动态管理服务，基于 Cloudflare Workers，支持 Markdown、图片上传、标签管理。

## 功能特性
- 管理员登录（GitHub OAuth）
- 发布、编辑、删除动态（支持 Markdown 内容、标签、图片上传）
- 动态内容存储于 Cloudflare KV，图片存储于 R2
- 响应式美观 UI，支持移动端
- Markdown 渲染，图片自动插入

## 目录结构
   ```
   wrangler.toml         # Cloudflare Workers 配置
   src/
     admin.js           # 管理后台主逻辑
     api.js             # API 路由
     auth.js            # 认证逻辑
     index.js           # 入口
     public.js          # 公共页面
     utils.js           # 工具函数
   ```

## 快速开始

1. 创建 `wrangler.toml`，设置 KV 和 R2 绑定

    创建Github Outh（回调为：/auth/callback）
   ```
   name = "social-moments"
   main = "src/index.js"
   compatibility_date = "2025-07-21"

   [[kv_namespaces]]
   binding = "POSTS_KV"
   id = "---"

   [[r2_buckets]]
   binding = "POST_BUCKET"
   bucket_name = "---"

   [vars]
   GITHUB_CLIENT_ID = "---"
   GITHUB_CLIENT_SECRET = "---"
   ADMIN_USERS = '["---"]'
   ```
2. 安装依赖

   ```
   pnpm install
   ```

3. 本地开发/预览：
   ```sh
   wrangler dev
   ```
4. 部署到 Cloudflare Workers：
   ```sh
   wrangler deploy
   ```

## 依赖环境
- Cloudflare Workers
- Cloudflare KV & R2
- Node.js 18+
- Wrangler CLI

## License
MIT

