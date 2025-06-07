---
project: Iris
stars: 45
description: |-
    Capturing beautiful moments in life, documenting daily warmth and emotions through my lens.
url: https://github.com/Iris-Photo-Gallery/Iris
---

# Iris Photo Gallery

一个现代化的照片画廊网站，采用 React + TypeScript 构建，支持从多种存储源（S3、GitHub）自动同步照片，具有高性能 WebGL 渲染、瀑布流布局、EXIF 信息展示、缩略图生成等功能。

## 🌟 特性

### 核心功能

- 🖼️ **高性能 WebGL 图像渲染器** - 基于自研 WebGL 组件，支持流畅的缩放、平移操作
- 📱 **响应式瀑布流布局** - 采用 Masonic 实现，自适应不同屏幕尺寸
- 🎨 **现代化 UI 设计** - 基于 Tailwind CSS 和 Radix UI 组件库
- ⚡ **增量同步** - 智能检测文件变化，仅处理新增或修改的照片

### 图像处理

- 🔄 **HEIC/HEIF 格式支持** - 自动转换 Apple 设备的 HEIC 格式
- 🖼️ **智能缩略图生成** - 多尺寸缩略图，优化加载性能
- 📊 **EXIF 信息展示** - 完整的拍摄参数，包括相机型号、焦距、光圈等
- 🌈 **Blurhash 占位符** - 优雅的图片加载体验
- 📱 **Live Photo 支持** - 检测并展示 iPhone Live Photo

### 高级功能

- 🎛️ **富士胶片模拟** - 读取和展示富士相机的胶片模拟设置
- 🔍 **全屏查看器** - 支持手势操作的图片查看器
- 🏷️ **智能标签** - 基于 EXIF 数据自动生成标签
- ⚡ **并发处理** - 支持多进程/多线程并发处理
- 🗂️ **多存储支持** - S3、GitHub 等多种存储后端

## 🏗️ 技术架构

### 前端技术栈

- **React 19** - 使用最新的 React 版本和 Compiler
- **TypeScript** - 完整的类型安全
- **Vite** - 现代化构建工具
- **Tailwind CSS** - 原子化 CSS 框架
- **Radix UI** - 无障碍组件库
- **Jotai** - 状态管理
- **TanStack Query** - 数据获取和缓存
- **React Router 7** - 路由管理

### 构建系统

- **Node.js** - 服务端运行时
- **Sharp** - 高性能图像处理
- **AWS SDK** - S3 存储操作
- **Worker Threads/Cluster** - 并发处理
- **EXIF-Reader** - EXIF 数据提取

### 存储架构

采用适配器模式设计，支持多种存储后端：

- **S3 兼容存储** - AWS S3、MinIO、阿里云 OSS 等
- **GitHub 存储** - 使用 GitHub 仓库作为图片存储

## 📦 项目结构

```
photo-gallery-site/
├── apps/web/                    # 主应用
│   ├── src/
│   │   ├── components/          # React 组件
│   │   │   ├── ui/             # UI 组件库
│   │   │   └── common/         # 通用组件
│   │   ├── core/               # 核心构建系统
│   │   │   ├── builder/        # 主构建器
│   │   │   ├── storage/        # 存储适配器
│   │   │   ├── image/          # 图像处理
│   │   │   ├── photo/          # 照片处理
│   │   │   └── worker/         # 并发处理
│   │   ├── modules/            # 功能模块
│   │   ├── pages/              # 页面组件
│   │   └── data/               # 数据文件
│   ├── public/                 # 静态资源
│   └── scripts/                # 构建脚本
├── packages/webgl-viewer/       # WebGL 图像查看器
├── config/                     # 配置文件
└── docs/                       # 文档
```

## 🚀 快速开始

### 环境要求

- Node.js 18+
- 至少 4GB RAM（用于图像处理）

### 1. 克隆项目

```bash
git clone https://github.com/Iris-Photo-Gallery/Iris.git
cd photo-gallery-site
```

### 2. 安装依赖

```bash
pnpm install
```

### 3. 环境配置

创建 `.env` 文件：

```env
# S3 存储配置
S3_REGION=us-east-1
S3_ACCESS_KEY_ID=your_access_key_id
S3_SECRET_ACCESS_KEY=your_secret_access_key
S3_ENDPOINT=https://s3.amazonaws.com
S3_BUCKET_NAME=your_bucket_name
S3_PREFIX=photos/
S3_CUSTOM_DOMAIN=your_custom_domain.com
```

### 4. 站点配置

复制并编辑配置文件：

```bash
cp config.example.json config.json
```

编辑 `config.json`：

```json
{
  "name": "我的照片画廊",
  "title": "我的照片画廊",
  "description": "记录生活中的美好瞬间",
  "url": "https://gallery.example.com",
  "accentColor": "#007bff",
  "author": {
    "name": "Your Name",
    "url": "https://example.com"
  },
  "social": {
    "twitter": "@yourusername"
  }
}
```

### 5. 构建照片清单

```bash
# 首次构建
pnpm run build:manifest

# 增量更新
pnpm run build:manifest

# 强制全量更新
pnpm run build:manifest -- --force
```

### 6. 启动开发服务器

```bash
pnpm dev
```

## ⚙️ 配置选项

### 构建器配置

创建 `builder.config.json` 文件进行高级配置：

```json
{
  "repo": {
    "enable": false,
    "url": "https://github.com/username/gallery-assets"
  },
  "storage": {
    "provider": "s3",
    "bucket": "my-photos",
    "region": "us-east-1",
    "prefix": "photos/",
    "customDomain": "cdn.example.com"
  },
  "options": {
    "defaultConcurrency": 8,
    "maxPhotos": 5000,
    "enableLivePhotoDetection": true,
    "showProgress": true,
    "showDetailedStats": true
  },
  "logging": {
    "verbose": true,
    "level": "info",
    "outputToFile": false
  },
  "performance": {
    "worker": {
      "workerCount": 8,
      "timeout": 30000,
      "useClusterMode": true,
      "workerConcurrency": 2
    }
  }
}
```

### 配置选项说明

#### 存储配置 (`storage`)

- `provider`: 存储提供商 (`s3` | `github`)
- `bucket`: S3 存储桶名称
- `region`: S3 区域
- `endpoint`: S3 端点（可选）
- `prefix`: 文件前缀
- `customDomain`: 自定义域名

#### 构建选项 (`options`)

- `defaultConcurrency`: 默认并发数 (1-50)
- `maxPhotos`: 最大照片数量限制
- `enableLivePhotoDetection`: 启用 Live Photo 检测
- `showProgress`: 显示构建进度
- `showDetailedStats`: 显示详细统计信息

#### 性能配置 (`performance`)

- `worker.workerCount`: Worker 进程数
- `worker.timeout`: Worker 超时时间（毫秒）
- `worker.useClusterMode`: 启用集群模式

#### 日志配置 (`logging`)

- `verbose`: 详细日志
- `level`: 日志级别 (`info` | `warn` | `error` | `debug`)
- `outputToFile`: 输出到文件

### 远程资源库配置

如果你有独立的资源仓库存储缩略图和清单：

```json
{
  "repo": {
    "enable": true,
    "url": "https://github.com/username/gallery-assets"
  }
}
```

这将自动从远程仓库拉取资源，避免每次构建。

## 📋 CLI 命令

### 构建命令

```bash
# 查看帮助
pnpm run build:manifest -- --help

# 增量更新（默认）
pnpm run build:manifest

# 强制全量更新
pnpm run build:manifest -- --force

# 仅重新生成缩略图
pnpm run build:manifest -- --force-thumbnails

# 仅重新生成清单
pnpm run build:manifest -- --force-manifest
```

### 开发命令

```bash
# 启动开发服务器
pnpm dev

# 构建生产版本
pnpm build
```

## 🚀 部署指南

### Vercel 部署（推荐）

1. **Fork 项目**

   - 访问 [GitHub 仓库](https://github.com/Iris-Photo-Gallery/Iris)
   - 点击右上角的 "Fork" 按钮，将项目 fork 到你的 GitHub 账户

2. **在 Vercel 部署**
   - 访问 [Vercel](https://vercel.com/)
   - 使用 GitHub 账户登录
   - 点击 "New Project"，选择你刚才 fork 的仓库
   - 在项目设置中添加以下环境变量（如果你使用 S3 存储）：

```env
S3_REGION=us-east-1
S3_ACCESS_KEY_ID=你的 S3 访问密钥 ID
S3_SECRET_ACCESS_KEY=你的 S3 秘密访问密钥
S3_ENDPOINT=https://s3.amazonaws.com
S3_BUCKET_NAME=你的 S3 存储桶名称
S3_PREFIX=photos/
S3_CUSTOM_DOMAIN=你的自定义域名（可选）
```

3. **触发部署**
   - 配置完环境变量后，Vercel 会自动开始部署
   - 等待部署完成，你的照片画廊就上线了！

### 注意事项

- 确保你的 S3 存储桶已经包含照片文件
- 如果使用远程资源库，需要先配置 `builder.config.json`

## 🔧 高级用法

### 自定义存储提供商

实现 `StorageProvider` 接口以支持新的存储后端：

```typescript
import { StorageProvider } from './src/core/storage/interfaces'

class MyStorageProvider implements StorageProvider {
  async getFile(key: string): Promise<Buffer | null> {
    // 实现文件获取逻辑
  }

  async listImages(): Promise<StorageObject[]> {
    // 实现图片列表获取逻辑
  }

  // ... 其他方法
}
```

### 自定义图像处理

在 `src/core/image/` 目录下添加自定义处理器：

```typescript
export async function customImageProcessor(buffer: Buffer) {
  // 自定义图像处理逻辑
  return processedBuffer
}
```

## 📄 许可证

MIT License © 2025 Innei

## 🔗 相关链接

- [在线演示](https://gallery.innei.in)
- [个人网站](https://innei.in)
- [GitHub](https://github.com/innei)
- [问题反馈](https://github.com/Iris-Photo-Gallery/Iris/issues)

---

如果这个项目对你有帮助，请给个 ⭐️ Star 支持一下！

