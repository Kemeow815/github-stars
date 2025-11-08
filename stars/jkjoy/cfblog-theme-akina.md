---
project: cfblog-theme-akina
stars: 2
description: |-
    null
url: https://github.com/jkjoy/cfblog-theme-akina
---

## cfblog-theme-akina

![Vue 3](https://img.shields.io/badge/Vue-3.x-42b883?logo=vue.js)
![Vite 7](https://img.shields.io/badge/Vite-7.x-646cff?logo=vite)
![TypeScript 5](https://img.shields.io/badge/TypeScript-5.x-3178c6?logo=typescript)
![Node 20.19+](https://img.shields.io/badge/Node-20.19%2B-43853d?logo=node.js)
![Cloudflare Pages](https://img.shields.io/badge/Cloudflare%20Pages-ready-F38020?logo=cloudflare)

一个基于 Vue 3 + Vite 的 CFBlog 前端主题，样式参考 Akina。支持 Markdown 渲染、代码高亮、分类/标签/归档、友情链接、关于页、基础 SEO 与结构化数据等特性。

— 适配 Cloudflare Pages 一键部署，也可本地开发运行。

**在线预览**

- Demo: https://akina.zxd.im

**效果概览**

- Akina 风格、响应式布局
- Markdown 渲染（`markdown-it`）与代码高亮（`highlight.js`）
- 外链统一新标签页打开并附加安全属性（`noopener noreferrer`）
- 基础 SEO：标题、描述、OG/Twitter Card、Canonical（`useSEO`）
- 结构化数据（JSON-LD）：文章与面包屑（`useStructuredData`）
- 列表分页、分类/标签详情、归档列表、友情链接、关于页
- 站点设置动态注入（标题、描述、favicon 等）

**截图**

![首页示例](/screenshots/screenshots.webp)

后端项目地址：`cfBLOG` REST API（或兼容的 WordPress REST API）

- https://github.com/jkjoy/cfblog

---

**本地开发**

前置要求：`Node.js >= 20.19`（或 `>= 22.12`）

1. 克隆并安装依赖

- `npm install`

2. 配置环境变量

- 复制示例文件：`cp .env.example .env`
- 设置后端地址：在 `.env` 中填写 `VITE_API_URL`
  - 可指向 CFBlog 后端 API 或 WordPress 站点地址（兼容大部分 WordPress REST API）

3. 运行与构建

- 开发：`npm run dev`
- 类型检查：`npm run type-check`
- 构建：`npm run build`
- 本地预览产物：`npm run preview`

---

**部署（Cloudflare Pages）**

1. Fork 本仓库到你的 GitHub 账户
2. 在 Cloudflare Pages 新建项目，选择该仓库
3. 构建配置（保持默认即可）

- 构建命令：`npm run build`
- 构建产物目录：`dist`

4. 环境变量

- `VITE_API_URL`：后端 API 基地址（或 WordPress 站点根地址）

5. 保存并部署

可选：Vercel/Netlify 等平台部署流程类似，同样设置 `VITE_API_URL` 即可。

---

**常用脚本**

- `npm run dev`：本地开发（Vite）
- `npm run build`：生产构建
- `npm run preview`：本地预览构建产物
- `npm run type-check`：类型检查（`vue-tsc`）
- `npm run lint`：ESLint 自动修复
- `npm run format`：Prettier 格式化 `src/`

---

**目录结构（简要）**

- `src/views`：页面（首页、文章详情、分类/标签、归档、关于、友链等）
- `src/components`：通用组件（文章卡片、分页、评论等）
- `src/composables`：可复用逻辑（`useSEO`、`useMarkdown`、`useStructuredData` 等）
- `src/stores`：Pinia 状态（站点设置）
- `src/assets`：样式与静态资源

---

**配置说明**

- `VITE_API_URL`
  - 指向你的后端 API（示例：`https://your-api.example.com`）
  - 或直接填写 WordPress 站点地址（示例：`https://your-wp-site.com`）

---

**常见问题**

- 标题闪烁或被覆盖？
  - 项目内通过 `useSEO` 统一设置页面标题，避免被全局设置覆盖；如需自定义请在对应视图调用 `useSEO({ title: '...' })` 或 `updateMeta({ title: '...' })`。
- 外链是否新开标签？
  - 已在 `useMarkdown` 中为外链添加 `target="_blank" rel="noopener noreferrer"`。

---

## 鸣谢

感谢以下项目和资源，它们为本项目提供了灵感和支持：

- Akina 主题风格灵感
- Vue 生态与开源社区

