---
project: moments
stars: 2
description: |-
    博客网站个人瞬间功能
url: https://github.com/lusyoe/moments
---

# moments - 个人瞬间分享平台

一个基于 Next.js 和 Notion API 构建的个人瞬间分享平台，支持静态部署和评论系统。

## ✨ 功能特性

- 📝 **瞬间分享** - 从 Notion 数据库获取瞬间内容并展示
- 🎨 **响应式设计** - 支持桌面端和移动端访问
- 🌙 **主题切换** - 支持明暗主题切换
- 💬 **评论系统** - 集成 Twikoo 评论系统
- 📱 **图片展示** - 支持多图片展示和放大查看
- 📊 **静态 JSON API** - 构建后自动生成纯 JSON 文件，供第三方调用
- 🚀 **静态部署** - 支持静态导出，可部署到 CDN
- 🐳 **Docker 支持** - 提供 Docker 容器化部署方案

## 🛠️ 技术栈

- **前端框架**: Next.js 15.4.3
- **开发语言**: TypeScript 5.8.3
- **UI 组件**: React 19.1.0
- **图标库**: FontAwesome
- **Markdown 渲染**: react-markdown
- **时间处理**: dayjs
- **数据源**: Notion API
- **评论系统**: Twikoo
- **部署**: 静态导出 + Nginx

## 📦 安装部署

### 环境要求

- Node.js 18+ 
- Yarn 或 npm
- Notion API Token
- Twikoo 环境 ID（可选）

### 0. 复制 Notion 模板
项目使用的 Notion 模板已公开，模板链接：https://lusyoe.notion.site/23b9161fd46b809e8e6adb032cf73dd4
可将该模板复制到自己的 Notion 空间中，然后进行后续的步骤。
完整说明可参看博客文章：[网站”日常瞬间”开源说明](https://blog.lusyoe.com/article/open-source-moments-activity)

### 1. 克隆项目

```bash
git clone <repository-url>
cd moments
```

### 2. 安装依赖

```bash
yarn install
# 或
npm install
```

### 3. 环境配置

创建 `.env.local` 文件并配置以下环境变量：

```env
# Notion API 配置
NOTION_TOKEN=your_notion_api_token
NOTION_DATABASE_ID=your_database_id

# Twikoo 评论系统配置（可选）
NEXT_PUBLIC_TWIKOO_URL=your_twikoo_env_id
NEXT_PUBLIC_BLOG_URL=https://your-blog-domain.com
```

### 4. 开发环境运行

```bash
yarn dev
# 或
npm run dev
```

访问 http://localhost:3000 查看效果。

### 5. 生产环境构建

```bash
# 构建静态文件
yarn build
# 或
npm run build
```

构建完成后，静态文件将生成在 `out/` 目录中。

### 6. 部署方式

#### 方式一：静态部署

构建完成后，将 `out/` 目录中的文件部署到任何静态托管服务：

- Vercel
- Netlify  
- GitHub Pages
- 阿里云 OSS
- 腾讯云 COS

#### 方式二：Docker 部署

```bash
# 构建 Docker 镜像
docker build -t moments .

# 运行容器
docker run -d -p 80:80 moments
```

#### 方式三：Nginx 部署

1. 将 `out/` 目录内容复制到 Nginx 的静态文件目录
2. 使用项目提供的 `nginx.conf` 配置文件
3. 重启 Nginx 服务

## 📡 静态 JSON API 说明

### 最近瞬间接口（静态文件）

**接口地址**: `GET /recent-moments.json`

> ⚠️ 说明：构建完成后，`out/recent-moments.json` 为真正的纯 JSON 文件，可直接被第三方系统或前端 fetch 读取，无需 Node 服务器支持。

**响应格式**:
```json
{
  "success": true,
  "data": [
    {
      "logo": "🎉",
      "title": "瞬间标题",
      "date": "2024-01-15",
      "mood": "开心 兴奋"
    }
  ],
  "count": 1,
  "generatedAt": "2024-01-15T10:30:00.000Z"
}
```

详细 API 文档请参考 [API_DOCUMENTATION.md](./API_DOCUMENTATION.md)

## 🔧 项目结构

```
moments/
├── pages/                 # Next.js 页面
│   ├── index.tsx         # 主页面
│   └── recent-moments.json.tsx  # 静态 JSON 生成页面
├── lib/                  # 工具库
│   └── notion.ts         # Notion API 集成
├── out/                  # 静态构建输出（含 recent-moments.json）
├── scripts/              # 构建后处理脚本
│   └── generate-json.js  # 生成纯 JSON 文件
├── Dockerfile            # Docker 配置
├── nginx.conf           # Nginx 配置
├── next.config.js       # Next.js 配置
├── package.json         # 项目依赖
└── tsconfig.json        # TypeScript 配置
```

## 🎯 主要功能

### 瞬间展示
- 从 Notion 数据库获取瞬间内容
- 支持 Markdown 格式渲染
- 显示瞬间标题、日期、心情等信息
- 支持多图片展示

### 评论系统
- 集成 Twikoo 评论系统
- 支持评论数量显示
- 动态加载评论内容

### 主题切换
- 支持明暗主题切换
- 主题状态本地持久化

### 图片查看
- 支持图片放大查看
- 多图片轮播展示
- 原图加载功能

## 🔍 配置说明

### Notion 数据库结构

项目需要以下 Notion 数据库字段：

- **标题** (Title): 瞬间标题
- **日期** (Date): 瞬间日期
- **心情** (Multi-select): 心情标签
- **图标** (Text): 瞬间图标
- **状态** (Select): 发布状态
- **内容** (Rich text): 瞬间详细内容

### 环境变量

| 变量名 | 说明 | 必需 |
|--------|------|------|
| `NOTION_TOKEN` | Notion API Token | ✅ |
| `NOTION_DATABASE_ID` | Notion 数据库 ID | ✅ |
| `NEXT_PUBLIC_TWIKOO_URL` | Twikoo 环境 ID | ❌ |
| `NEXT_PUBLIC_BLOG_URL` | 博客域名 | ❌ |
| `NOTION_DAY_RANGE` | 显示最近多少天瞬间 | ❌ |

## 🚀 开发指南

### 添加新功能

1. 在 `pages/` 目录添加新页面
2. 在 `lib/` 目录添加工具函数
3. 更新 TypeScript 类型定义
4. 测试功能并提交代码

### 自定义样式

项目使用 CSS 模块，可以在组件中直接编写样式。

### 部署更新

1. 修改代码并测试
2. 提交到 Git 仓库
3. 触发 CI/CD 构建
4. 自动部署到生产环境

## 📝 更新日志

### v1.0.0
- ✅ 基础瞬间展示功能
- ✅ Notion API 集成
- ✅ 评论系统集成
- ✅ 主题切换功能
- ✅ 静态部署支持
- ✅ Docker 容器化
- ✅ 静态 JSON API 文件生成

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建功能分支
3. 提交代码变更
4. 创建 Pull Request

## 📄 许可证

本项目采用 MIT 许可证，详见 [LICENSE](LICENSE) 文件。

## 📞 联系方式

如有问题或建议，请通过以下方式联系：

- 邮箱: [lusyoe@163.com]
- 博客: [https://blog.lusyoe.com]
- GitHub: [https://github.com/lusyoe]

---

⭐ 如果这个项目对您有帮助，请给个 Star 支持一下！ 

