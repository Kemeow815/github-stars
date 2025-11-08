---
project: Cloudflare-Navihive
stars: 589
description: |-
    NaviHive 是一个精美的个人网站导航管理系统，帮助你整理和管理你收藏的网站链接。支持分组管理、拖拽排序、暗色模式等功能，让你的网站收藏更有条理、更易访问。
url: https://github.com/zqq-nuli/Cloudflare-Navihive
---

<div align="center">

<svg width="120" height="120" viewBox="0 0 120 120" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path d="M60 10L105 35V85L60 110L15 85V35L60 10Z" fill="url(#paint0_linear)" stroke="#2D6CDF" stroke-width="2"/>
  <path d="M60 30L80 40V75L60 85L40 75V40L60 30Z" fill="white" stroke="#2D6CDF" stroke-width="2"/>
  <circle cx="60" cy="57" r="10" fill="#2D6CDF"/>
  <path d="M60 43V57L68 65" stroke="white" stroke-width="3" stroke-linecap="round"/>
  <defs>
    <linearGradient id="paint0_linear" x1="15" y1="60" x2="105" y2="60" gradientUnits="userSpaceOnUse">
      <stop stop-color="#61DAFB"/>
      <stop offset="1" stop-color="#2D6CDF"/>
    </linearGradient>
  </defs>
</svg>

# NaviHive - 现代化个人导航站

![NaviHive 导航站](https://img.shields.io/badge/NaviHive-导航站-blue)
![React](https://img.shields.io/badge/React-19.0.0-61dafb)
![TypeScript](https://img.shields.io/badge/TypeScript-5.7-3178c6)
![Material UI](https://img.shields.io/badge/Material_UI-7.0-0081cb)
![Cloudflare](https://img.shields.io/badge/Cloudflare-Workers-f38020)
![License](https://img.shields.io/badge/License-MIT-green)

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/zqq-nuli/Cloudflare-Navihive)

</div>

> 🚀 一个优雅、现代化的网站导航管理系统，让你的书签收藏井然有序

## 🎯 功能清单

### 核心功能
| 功能 | 版本 | 描述 |
|------|------|------|
| 📚 **智能分组管理** | `v1.0.0` | 按类别组织网站，支持无限分组和嵌套管理 |
| 🔄 **拖拽排序** | `v1.0.0` | 可视化调整分组和网站顺序，所见即所得 |
| 🌓 **暗色模式** | `v1.0.0` | 深色/浅色主题自由切换，呵护双眼 |
| 📤 **数据导入导出** | `v1.0.0` | JSON 格式数据备份与迁移 |
| 🎨 **自定义样式** | `v1.0.0` | 自定义 CSS、标题、Logo，打造专属导航 |
| 🖼️ **背景图片设置** | `v1.0.3` | 支持背景图片和蒙版透明度调节 |
| 📁 **分组折叠** | `v1.0.2` | 支持展开/收起分组内容 |
| 🔀 **智能数据合并** | `v1.0.2` | 导入时自动去重，按 URL 智能匹配 |
| 💾 **记住我登录** | `v1.0.4` | 可选 30 天长效 Token，免频繁登录 |
| 🌍 **访客模式** | `v1.1.0` | 免登陆浏览公开内容，私密内容保护 |
| 📱 **完美响应式** | `v1.0.0` | 桌面、平板、移动端完美适配 |

### 安全功能
| 功能 | 版本 | 描述 |
|------|------|------|
| 🔐 **JWT 认证** | `v1.0.0` | Web Crypto API + HMAC-SHA256 签名 |
| 🔒 **bcrypt 加密** | `安全更新` | 10 轮盐值密码哈希，防暴力破解 |
| 🍪 **HttpOnly Cookie** | `安全更新` | 防 XSS Token 窃取 |
| 🛡️ **XSS 防护** | `安全更新` | CSS 代码沙箱化，移除危险模式 |
| 🚫 **SSRF 防护** | `安全更新` | 私有 IP 地址过滤 |
| 💉 **SQL 注入防护** | `安全更新` | 全参数化查询 |
| 🧱 **登录速率限制** | `v1.1.0` | 5 次/15 分钟，防暴力破解并记录 IP |
| 📦 **请求体限制** | `安全更新` | 最大 1MB，防内存溢出 |
| 🌐 **CORS 白名单** | `安全更新` | 精确访问控制 |
| ✅ **TypeScript 严格模式** | `安全更新` | 全栈类型安全，65+ 类型错误修复 |
| 🧪 **深度数据验证** | `安全更新` | 导入操作全面验证 |

### 部署与性能
| 特性 | 版本 | 描述 |
|------|------|------|
| ☁️ **Cloudflare Workers** | `v1.0.0` | 全球边缘计算，毫秒级响应 |
| 🗄️ **D1 数据库** | `v1.0.0` | 分布式 SQLite，免费 500MB |
| 💰 **零成本部署** | `v1.0.0` | 免费套餐足够个人使用 |
| ⚡ **极致性能** | `v1.0.0` | 全球 CDN 加速 |
| 🔧 **自定义域名** | `v1.0.0` | 支持绑定个人域名 |

> 💡 **当前版本**：v1.1.0 | 完整更新日志详见 [更新日志](#-更新日志)

---

## 🎯 快速开始

**三步部署，立即使用：**

1. **Fork 项目** → 点击右上角 Fork 按钮
2. **一键部署** → [![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/你的用户名/Cloudflare-Navihive)
3. **配置数据库** → 在 Cloudflare 控制台创建 D1 数据库并初始化

> 详细步骤见下方[部署指南](#-部署指南)

---

NaviHive 是基于 Cloudflare Workers 构建的轻量级导航站点，完美替代浏览器书签栏。它提供直观的可视化管理界面，支持分组分类、拖拽排序、暗色模式等实用功能，让你的常用网站触手可及。零成本部署，秒级访问，随时随地管理你的网络世界入口。

## 📑 目录

- [功能清单](#-功能清单)
- [在线演示](#-在线演示)
- [特性](#-特性)
- [演示截图](#-演示截图)
- [技术栈](#️-技术栈)
- [部署指南](#-部署指南)
  - [准备工作](#一准备工作)
  - [一键部署方法](#二一键部署方法推荐小白用户)
  - [手动部署方法](#三手动部署方法适合开发者)
  - [初始化与数据库设置](#四初始化与数据库设置)
- [免登陆访问部署与旧项目迁移](#-免登陆访问部署与旧项目迁移)
- [使用指南](#-使用指南)
  - [登录系统](#登录系统)
  - [访客模式与编辑模式](#-访客模式与编辑模式)
  - [配置您的导航站](#配置您的导航站)
  - [使用自定义域名](#使用自定义域名可选)
- [常见问题解答](#-常见问题解答)
- [项目结构](#️-项目结构)
- [贡献](#-贡献)
- [许可证](#-许可证)
- [鸣谢](#-鸣谢)
- [更新日志](#-更新日志)
- [支持一下作者](#-支持一下作者)
- [Star History](#star-history)

## 🌐 在线演示

立即体验 NaviHive 的所有功能：**[在线演示站点](https://navihive.chatbot.cab/)**

```
👤 演示账号：admin
🔑 演示密码：NaviHive2025!
```

> 💡 提示：演示站数据会定期重置，请勿保存重要信息

## ✨ 核心特性

### 🎯 管理功能
-   📚 **智能分组** - 按类别组织网站，支持无限分组和嵌套管理
-   🔄 **拖拽排序** - 可视化调整分组和网站顺序，所见即所得
-   🎨 **高度自定义** - 自定义标题、Logo、背景图、CSS 样式，打造专属导航站
-   📤 **数据导入导出** - 一键备份恢复，支持 JSON 格式数据迁移

### 🔐 安全保障
-   🔒 **企业级认证** - JWT + bcrypt 加密，HttpOnly Cookie 防 XSS
-   👤 **访问控制** - 内置用户认证系统，保护你的私密数据
-   🧱 **登录速率限制** - `/api/login` 默认限 5 次/15 分钟，超限返回 429 并记录 IP
-   🪪 **免登陆访客模式** - 可通过 `AUTH_REQUIRED_FOR_READ` 开关允许访客只读访问公开分组与站点
-   🛡️ **安全防护** - SQL 注入防护、SSRF 防护、请求体大小限制

### 🎨 用户体验
-   🌓 **主题切换** - 深色/浅色模式自由切换，呵护双眼
-   📱 **完美响应式** - 从桌面到移动端，各种屏幕完美适配
-   ⚡ **极致性能** - Cloudflare 全球 CDN 加速，毫秒级响应
-   🎯 **零成本部署** - 基于 Cloudflare Workers 免费套餐，永久免费使用

## 📸 演示截图

<details>
<summary><b>全局设置</b></summary>
<img src="https://img.zhengmi.org/file/1743801673107_1743801661335.jpg" alt="全局设置" width="100%">
</details>

<details>
<summary><b>网站设置</b></summary>
<img src="https://img.zhengmi.org/file/1743801939121_image.png" alt="网站设置" width="100%">
</details>

<details>
<summary><b>暗色模式</b></summary>
<img src="https://img.zhengmi.org/file/1743801684425_image.png" alt="暗色模式" width="100%">
</details>

<details>
<summary><b>拖拽排序（暗色）</b></summary>
<img src="https://img.zhengmi.org/file/1743801720324_image.png" alt="拖拽排序（暗色）" width="100%">
</details>

## 🛠️ 技术栈

### 前端技术
-   ⚛️ **React 19** - 最新版本，极致性能
-   📘 **TypeScript 5.7** - 类型安全，智能提示
-   🎨 **Material UI 7.0** - Google 设计语言，开箱即用
-   🎪 **DND Kit** - 流畅的拖拽交互体验
-   🌊 **Tailwind CSS 4.1** - 原子化 CSS，快速开发
-   ⚡ **Vite 6** - 极速构建工具，毫秒级 HMR

### 后端技术
-   ☁️ **Cloudflare Workers** - 边缘计算，全球部署
-   🗄️ **Cloudflare D1** - 分布式 SQLite 数据库
-   🔐 **JWT + bcrypt** - 工业级身份认证
-   🛡️ **TypeScript Strict Mode** - 全栈类型安全

### 开发工具
-   📦 **pnpm** - 高效的包管理器
-   🔨 **Wrangler CLI** - Cloudflare 官方开发工具
-   🎯 **ESLint + Prettier** - 代码质量保障

## 🚀 部署指南

NaviHive 提供两种部署方案，请根据您的技术背景选择合适的方式。

---

## 📦 方案一：小白用户部署（推荐新手）

> 适合不熟悉编程的用户，通过网页界面完成全部部署流程，无需安装任何开发工具。

### 准备工作

1. 注册一个免费的 [Cloudflare 账号](https://dash.cloudflare.com/sign-up)
2. 注册一个 [GitHub 账号](https://github.com/signup)（用于 fork 项目）

### 部署步骤

#### 第一步：Fork 项目

1. 访问本项目的 GitHub 页面
2. 点击右上角的 **Fork** 按钮，将项目复制到你的账号下

#### 第二步：一键部署到 Cloudflare

1. 在你 fork 的项目页面，点击顶部的 **Deploy to Cloudflare Workers** 按钮
2. 登录你的 Cloudflare 账号
3. 授权 GitHub 访问权限
4. 系统会自动开始部署流程

> 如果一键部署按钮无法使用，可以直接进入第三步手动创建。

#### 第三步：创建 D1 数据库

1. 登录 [Cloudflare 控制台](https://dash.cloudflare.com/)
2. 在左侧菜单选择 **Workers & Pages**
3. 点击右侧的 **D1 SQL Database** 标签
4. 点击 **Create database** 按钮
5. 输入数据库名称：`navigation-db`
6. 点击 **Create** 完成创建
7. **记下数据库 ID**（格式类似：`43ff28e1-42d6-4e53-9657-0702ae1353b6`）

![创建 D1 数据库](https://img.zhengmi.org/file/1743843332374_image.png)

#### 第四步：配置项目

1. 在 Cloudflare 控制台，进入 **Workers & Pages**
2. 如果已通过一键部署创建了 Worker，选择该项目；否则点击 **Create Application** > **Create Worker**
3. 进入项目后，点击 **Settings** > **Variables**
4. 添加以下环境变量：

| 变量名 | 值 | 说明 |
|--------|-----|------|
| `AUTH_ENABLED` | `true` | 启用登录认证 |
| `AUTH_REQUIRED_FOR_READ` | `false` | 是否要求访客认证。`false` 启用免登陆只读模式 |
| `AUTH_USERNAME` | `admin` | 管理员用户名（可自定义） |
| `AUTH_PASSWORD` | 见下方说明 | 管理员密码（bcrypt 哈希） |
| `AUTH_SECRET` | 见下方说明 | JWT 密钥（随机字符串） |

> 如果需要完全关闭访客访问，将 `AUTH_REQUIRED_FOR_READ` 设置为 `true` 并重新部署；保留默认的 `false` 即表示启用公开的只读模式。

**设置密码（重要）：**
- 访问 [bcrypt 在线生成器](https://bcrypt.online/) 或使用 [Bcrypt Generator](https://bcrypt-generator.com/)
- 输入你想要的密码，选择 **10 rounds**
- 复制生成的哈希值（格式类似：`$2b$10$abc123...`）
- 粘贴到 `AUTH_PASSWORD` 变量中

**设置 JWT 密钥：**
- 访问 [随机字符串生成器](https://www.random.org/strings/)
- 生成一个 32 位以上的随机字符串
- 粘贴到 `AUTH_SECRET` 变量中

5. 点击 **Settings** > **Bindings** > **Add binding**
6. 选择 **D1 database**，Variable name 填写 `DB`，选择刚才创建的 `navigation-db`

#### 第五步：初始化数据库

1. 在 Cloudflare 控制台，进入 **D1 Databases**
2. 点击 `navigation-db` 数据库
3. 选择 **Console** 标签
4. 复制以下 SQL 命令并执行（点击 **Execute**）：

```sql
-- 创建分组表
CREATE TABLE IF NOT EXISTS groups (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    order_num INTEGER NOT NULL,
    is_public INTEGER DEFAULT 1,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 创建站点表
CREATE TABLE IF NOT EXISTS sites (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    group_id INTEGER NOT NULL,
    name TEXT NOT NULL,
    url TEXT NOT NULL,
    icon TEXT,
    description TEXT,
    notes TEXT,
    order_num INTEGER NOT NULL,
    is_public INTEGER DEFAULT 1,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (group_id) REFERENCES groups(id) ON DELETE CASCADE
);

-- 创建配置表
CREATE TABLE IF NOT EXISTS configs (
    key TEXT PRIMARY KEY,
    value TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 标记数据库已初始化
INSERT INTO configs (key, value) VALUES ('DB_INITIALIZED', 'true');

-- 创建只读模式所需索引
CREATE INDEX IF NOT EXISTS idx_groups_is_public ON groups(is_public);
CREATE INDEX IF NOT EXISTS idx_sites_is_public ON sites(is_public);
```

![执行 SQL](https://img.zhengmi.org/file/1743843528319_image.png)

5. 确认每条命令都执行成功（显示 ✓ Success）

> 如果你已经运行过旧版本的 SQL，只需在数据库控制台执行 `migrations/002_add_is_public.sql` 中的语句，或在本地使用 `wrangler d1 execute navigation-db --file=migrations/002_add_is_public.sql` 即可完成字段升级。

#### 第六步：访问你的导航站

1. 返回 **Workers & Pages**，找到你的项目
2. 复制项目的访问地址（格式：`https://your-project.username.workers.dev`）
3. 在浏览器中打开该地址
4. 使用你设置的用户名和密码登录
5. 不登录直接访问同一个链接，可验证访客模式是否只展示公开分组（默认开启）

🎉 恭喜！你的 NaviHive 导航站已经部署成功！

---

## 💻 方案二：开发者部署（推荐有技术基础用户）

> 适合熟悉命令行和 Git 操作的开发者，可以本地开发调试后再部署。

### 环境要求

- Node.js 18+ 或 20+
- pnpm 9+（推荐）或 npm
- Git
- Cloudflare 账号

### 快速开始

#### 1. 克隆项目

```bash
git clone https://github.com/zqq-nuli/Cloudflare-Navihive.git
cd Cloudflare-Navihive
```

#### 2. 安装依赖

```bash
pnpm install
# 或
npm install
```

#### 3. 安装并配置 Wrangler CLI

```bash
# 安装 Wrangler（如果还没安装）
npm install -g wrangler

# 登录 Cloudflare
wrangler login
```

浏览器会自动打开，授权后返回终端。

#### 4. 创建 D1 数据库

```bash
wrangler d1 create navigation-db
```

执行后会返回数据库信息，记下 `database_id`：

```
✅ Successfully created DB 'navigation-db'!

[[d1_databases]]
binding = "DB"
database_name = "navigation-db"
database_id = "43ff28e1-42d6-4e53-9657-0702ae1353b6"  # 这是你的数据库 ID
```

#### 5. 配置 wrangler.jsonc

编辑项目根目录的 `wrangler.jsonc` 文件：

```jsonc
{
    "$schema": "node_modules/wrangler/config-schema.json",
    "name": "navihive",  // 可自定义项目名称
    "main": "worker/index.ts",
    "compatibility_date": "2025-04-05",
    "compatibility_flags": ["nodejs_compat"],  // 必须启用 Node.js 兼容
    "assets": {
        "not_found_handling": "single-page-application"
    },
    "observability": {
        "enabled": true
    },
    "d1_databases": [
        {
            "binding": "DB",
            "database_name": "navigation-db",
            "database_id": "你的数据库ID"  // 替换为第4步获得的 database_id
        }
    ],
    "vars": {
        "AUTH_ENABLED": "true",
        "AUTH_REQUIRED_FOR_READ": "false",  // 免登陆访问开关，true 表示必须登录
        "AUTH_USERNAME": "admin",  // 自定义管理员用户名
        "AUTH_PASSWORD": "见下方说明",  // bcrypt 哈希值
        "AUTH_SECRET": "见下方说明"  // 32位随机字符串
    }
}
```

#### 6. 生成安全密码

项目内置了密码哈希生成工具：

```bash
pnpm hash-password YourSecurePassword123
```

输出示例：

```
正在生成密码哈希...

生成的密码哈希:
$2b$10$awC3.nc/XrxkAf6BbEbf.O1YqFUFIUIsbmgQL3pstjjYZpXfFtSGi

请将此哈希值设置为 AUTH_PASSWORD 环境变量
```

将生成的哈希值复制到 `wrangler.jsonc` 的 `AUTH_PASSWORD` 字段。

#### 7. 生成 JWT 密钥

在终端执行以下命令生成随机密钥：

```bash
# macOS/Linux
openssl rand -hex 32

# Windows (PowerShell)
[System.Convert]::ToBase64String([System.Security.Cryptography.RandomNumberGenerator]::GetBytes(32))

# 或使用 Node.js
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

将生成的字符串复制到 `wrangler.jsonc` 的 `AUTH_SECRET` 字段。

#### 8. 初始化数据库

```bash
wrangler d1 execute navigation-db --file=init_table.sql
wrangler d1 execute navigation-db --file=migrations/002_add_is_public.sql
```

上述两步会创建基础表结构，并为分组/站点添加 `is_public` 字段与索引。如果你更习惯直接执行 SQL，也可以参考 `init_table.sql` 与 `migrations/002_add_is_public.sql` 内的语句手动执行。

#### 9. 本地开发测试（可选）

```bash
pnpm dev
```

访问 `http://localhost:5173` 进行本地测试。

> 注意：本地开发默认使用 Mock 数据，如需测试真实 API，设置环境变量 `VITE_USE_REAL_API=true`。

#### 10. 部署到 Cloudflare

```bash
pnpm run deploy
# 或
npm run deploy
```

部署成功后，终端会显示访问地址：

```
Deployed navihive triggers (0.37 sec)
  https://navihive.your-username.workers.dev
Current Version ID: fe495e75-cc21-4a02-81d2-f14a4850c134
```

### 开发常用命令

```bash
# 本地开发
pnpm dev

# 构建项目
pnpm build

# 部署到 Cloudflare
pnpm run deploy

# 生成密码哈希
pnpm hash-password <your-password>

# 查看 Cloudflare 日志
wrangler tail

# 导出数据库
wrangler d1 export navigation-db

# 查询数据库
wrangler d1 execute navigation-db --command="SELECT * FROM groups"

# 验证免登陆 API
curl https://<your-worker>.workers.dev/api/groups
```

> 将 `<your-worker>` 替换为你的 Workers 子域名。未登录即可看到公开分组则表示免登陆模式配置正确。

### 配置自定义域名

1. 在 Cloudflare 控制台，进入 **Workers & Pages**
2. 选择你的项目，点击 **Settings** > **Triggers**
3. 在 **Custom Domains** 部分点击 **Add Custom Domain**
4. 输入域名并完成 DNS 验证

---

## 🔄 数据库迁移与备份

### 导出数据

```bash
# 导出整个数据库
wrangler d1 export navigation-db

# 导出为 JSON（通过 Web 界面）
# 登录后点击"网站设置" > "导出数据"
```

### 导入数据

```bash
# 从 SQL 文件导入
wrangler d1 execute navigation-db --file=backup.sql

# 通过 Web 界面导入 JSON
# 登录后点击"网站设置" > "导入数据"
```

## 🧭 免登陆访问部署与旧项目迁移

### 新部署 Checklist
- 配置 `AUTH_REQUIRED_FOR_READ=false`（默认值）以允许访客访问公开分组，若希望完全私有可改为 `true`
- 初始化数据库后立即执行 `migrations/002_add_is_public.sql`，确保 `is_public` 字段和索引就绪
- 在 Cloudflare 控制台或 `wrangler tail` 中确认后台日志存在 `允许免认证访问` 字样
- 访问 `/api/groups`、`/api/sites` 测试无 Token 请求是否只返回公开数据

### 旧版本 (≤ v1.0.x) 升级到免登陆访问
1. **备份数据**：`wrangler d1 export navigation-db > backup.sql`
2. **拉取最新代码**：`git pull` 后重新安装依赖（如有必要）
3. **新增环境变量**：在 `wrangler.jsonc` 和 Cloudflare 控制台同时添加 `AUTH_REQUIRED_FOR_READ`，推荐设置为 `false`
4. **执行数据库迁移**：
   ```bash
   wrangler d1 execute navigation-db --file=migrations/002_add_is_public.sql
   # 生产环境可在 Cloudflare D1 控制台执行同样的 SQL
   ```
5. **重新部署**：`pnpm build && pnpm deploy`（或使用 GitHub Action/一键部署按钮）
6. **验证**：
   - 访客直接访问网页仅看到 `is_public=1` 的分组与站点
   - 管理员登录后可见全部内容，写操作仍需认证
   - `wrangler tail` 中无未经授权的写操作日志

> 如果需要暂时关闭访客访问，无需回滚数据库，只需将 `AUTH_REQUIRED_FOR_READ` 改为 `true` 并重新部署即可。

## 📝 使用指南

### 🚪 访客模式新功能！

NaviHive v1.1.0 引入了**访客模式**，允许未登录用户查看公开内容：

- 🌍 **公开访问**：无需登录即可浏览公开分组和站点
- 🔐 **隐私保护**：私密内容仅对管理员可见
- ⚡ **灵活配置**：通过 `AUTH_REQUIRED_FOR_READ` 开关控制
- 🎯 **精细权限**：每个分组和站点都可以独立设置公开/私密状态

> 💡 默认启用访客模式，如需完全私有化，将 `AUTH_REQUIRED_FOR_READ` 设为 `true`

---

### 🚪 登录系统

首次访问导航站时，使用部署时设置的管理员账号登录：

1. 在登录页面输入用户名和密码
2. 可选择"记住我"延长登录时效（30 天）
3. 登录成功后，系统会自动跳转到导航主页

### 👀 访客模式与编辑模式
- 未登录时默认运行在 **访客模式**，只展示 `is_public = 1` 的分组与站点，任何写操作入口均被隐藏
- 登录后自动切换到 **编辑模式**，可新增/排序/删除内容；登出会回到访客模式
- 访客模式开关由 `AUTH_REQUIRED_FOR_READ` 控制；改为 `true` 可恢复旧版“必须登录才能访问”体验
- 需要将某个分组或站点设为私密时，可在 Cloudflare D1 控制台执行 `UPDATE groups SET is_public = 0 WHERE id = ?;` / `UPDATE sites SET is_public = 0 WHERE id = ?;`（即将上线的 UI 开关会进一步简化该流程）

### ⚙️ 配置导航站

#### 添加分组
1. 点击页面顶部的 **"新增分组"** 按钮
2. 输入分组名称（如"常用工具"、"开发资源"等）
3. 点击确认完成创建

#### 添加网站
1. 在对应分组中点击 **"添加卡片"** 按钮
2. 填写网站信息：
   - **名称**：网站显示名称
   - **URL**：网站完整地址（必须包含 `https://`）
   - **图标**（可选）：网站 Logo 图片地址
   - **描述**（可选）：网站简介
   - **备注**（可选）：个人笔记
3. 点击 **"保存"** 完成添加

#### 全局设置
点击右上角的 **"网站设置"** 按钮，可以配置：
- **网站标题**：浏览器标签页显示的标题
- **网站名称**：导航站顶部显示的名称
- **背景图片**：设置页面背景（支持图片 URL）
- **蒙版透明度**：调整背景图片的可见度
- **自定义 CSS**：注入自定义样式代码

#### 排序调整
1. 点击 **"编辑排序"** 按钮进入排序模式
2. 拖拽分组或网站卡片调整位置
3. 点击 **"保存排序"** 应用更改

#### 数据管理
- **导出数据**：在"网站设置"中点击"导出数据"，下载 JSON 备份文件
- **导入数据**：点击"导入数据"选择 JSON 文件，系统会智能合并数据

### 🌐 使用自定义域名（可选）

想要使用自己的域名而非 `.workers.dev` 子域名？按照以下步骤配置：

1. 登录 [Cloudflare 控制台](https://dash.cloudflare.com/)
2. 导航至 **Workers & Pages** > 选择你的项目
3. 点击 **Settings** > **Triggers** 标签
4. 在 **Custom Domains** 区域点击 **Add Custom Domain**
5. 输入你的域名（如 `nav.yourdomain.com`）
6. Cloudflare 会自动配置 DNS 记录，无需手动操作
7. 等待 1-3 分钟，SSL 证书自动签发完成

✅ 完成后，你可以通过自定义域名访问导航站！

## 🔧 常见问题解答

### 部署相关

**Q: 我忘记了管理员密码，怎么办？**

A: 有两种方法重置密码：

**方法一：通过 Cloudflare 控制台**
1. 在本地生成新密码哈希（如果没有本地环境，使用 [bcrypt 在线生成器](https://bcrypt.online/)）
2. 登录 [Cloudflare 控制台](https://dash.cloudflare.com/)
3. 进入 **Workers & Pages** > 选择你的项目
4. 点击 **Settings** > **Variables**
5. 修改 `AUTH_PASSWORD` 变量为新的哈希值
6. 点击 **Save** 保存（系统会自动重新部署）

**方法二：通过命令行（开发者）**
```bash
# 生成新密码哈希
pnpm hash-password NewPassword123

# 编辑 wrangler.jsonc，更新 AUTH_PASSWORD 值

# 重新部署
pnpm run deploy
```

---

**Q: 我想关闭登录认证，可以吗？**

A: 可以。在环境变量中将 `AUTH_ENABLED` 设置为 `false` 即可。

⚠️ **警告**：关闭认证后，任何人都可以访问和修改你的导航站数据，请谨慎使用。

---

**Q: 登录时提示 “429 Too Many Requests” 怎么办？**

A: 系统内置登录速率限制，同一 IP 在 15 分钟内最多尝试 5 次。当超过阈值时会返回 429 并在日志记录 IP。请等待 15 分钟后再试，或在 `worker/index.ts` 内 `new SimpleRateLimiter(5, 15)` 处调整阈值并重新部署。

---

**Q: 部署后访问网站显示 "请先登录"，但我还没设置数据库？**

A: 这是正常现象。请按照部署指南完成数据库初始化步骤（执行 SQL 创建表结构），然后刷新页面即可登录。

---

**Q: 部署时提示 "No such module 'crypto'" 错误？**

A: 这是因为缺少 Node.js 兼容性标志。请在 `wrangler.jsonc` 中添加：

```jsonc
{
    "compatibility_flags": ["nodejs_compat"]
}
```

然后重新部署即可。

---

**Q: 如何更新到最新版本？**

**小白用户：**
1. 进入你 fork 的 GitHub 仓库
2. 点击 **Sync fork** > **Update branch**
3. 在 Cloudflare 控制台重新部署（如果使用了 GitHub 集成，会自动部署）

**开发者：**
```bash
# 拉取最新代码
git pull origin main

# 重新部署
pnpm run deploy
```

---

**Q: 一键部署按钮无法使用？**

A: 一键部署功能需要 Cloudflare Workers 和 GitHub 的集成支持。如果无法使用，建议：
- 小白用户：按照"方案一"的步骤 3-6 手动创建
- 开发者：直接使用"方案二"命令行部署

---

### 数据管理

**Q: 如何备份我的导航数据？**

**方法一：通过 Web 界面（推荐）**
1. 登录你的导航站
2. 点击右上角的"网站设置"按钮
3. 点击"导出数据"按钮
4. 保存下载的 JSON 文件

**方法二：通过命令行（开发者）**
```bash
wrangler d1 export navigation-db
```

---

**Q: 如何导入数据？**

1. 登录你的导航站
2. 点击"网站设置" > "导入数据"
3. 选择之前导出的 JSON 文件
4. 确认导入（会自动合并数据，不会覆盖现有数据）

---

**Q: 数据库结构是什么？如何直接操作数据？**

NaviHive 使用三个主要表：

```sql
-- 分组表
groups (id, name, order_num, created_at, updated_at)

-- 网站表
sites (id, group_id, name, url, icon, description, notes, order_num, created_at, updated_at)

-- 配置表
configs (key, value, created_at, updated_at)
```

通过 Cloudflare 控制台 > D1 Databases > Console 可以直接执行 SQL 查询。

---

**Q: 导入数据时提示 "无效的 JSON 格式" 怎么办？**

A: 请确保：
1. JSON 文件是通过本系统导出的（格式兼容）
2. 文件没有被修改或损坏
3. 文件编码为 UTF-8
4. 文件大小不超过 1MB

---

### 使用和配置

**Q: 如何使用自定义域名？**

1. 登录 [Cloudflare 控制台](https://dash.cloudflare.com/)
2. 进入 **Workers & Pages** > 选择你的项目
3. 点击 **Settings** > **Triggers**
4. 在 **Custom Domains** 部分点击 **Add Custom Domain**
5. 输入你的域名（例如：nav.example.com）
6. 按照提示完成 DNS 配置（Cloudflare 会自动添加 DNS 记录）
7. 等待几分钟生效

---

**Q: 如何自定义网站样式（CSS）？**

1. 登录你的导航站
2. 点击"网站设置"
3. 在"自定义 CSS"文本框中输入你的 CSS 代码
4. 点击"保存"

示例：
```css
/* 修改背景颜色 */
body {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

/* 修改卡片样式 */
.MuiCard-root {
    border-radius: 16px !important;
    box-shadow: 0 8px 32px rgba(0,0,0,0.1) !important;
}
```

---

**Q: 拖拽排序后没有保存成功？**

A: 请确保：
1. 点击了"保存排序"按钮
2. 等待保存成功提示（不要立即关闭页面）
3. 检查浏览器控制台是否有错误信息
4. 确认已登录且 Token 未过期

---

**Q: 网站图标 (icon) 不显示？**

A: 可能的原因：
1. **URL 格式错误**：确保 icon 字段填写的是完整的图片 URL（如 `https://example.com/logo.png`）
2. **CORS 限制**：某些网站不允许跨域访问图片
3. **使用相对路径**：如果图标在本地，需要上传到图床后使用绝对路径
4. **推荐方案**：使用网站的 favicon（如 `https://example.com/favicon.ico`）

---

**Q: 如何设置背景图片？**

1. 登录你的导航站
2. 点击"网站设置"
3. 在"背景图片 URL"中填入图片地址
4. 调整"蒙版透明度"以控制背景的可见度
5. 点击"保存"

---

### 安全相关

**Q: 密码安全吗？会被破解吗？**

A: NaviHive 使用了多层安全措施：
- 密码使用 bcrypt 哈希加密（10 轮盐值），几乎无法暴力破解
- JWT Token 有效期限制（7 天或 30 天）
- 所有 API 请求都需要身份验证
- Token 存储在 HttpOnly Cookie 中，防止 XSS 攻击

只要你的密码足够复杂（建议 12 位以上，包含大小写字母、数字和特殊字符），就非常安全。

---

**Q: 我可以禁用 HTTPS 吗？**

A: 不可以。Cloudflare Workers 强制使用 HTTPS，这是为了保证你的数据传输安全。

---

**Q: 其他人能访问我的导航站吗？**

A:
- `AUTH_REQUIRED_FOR_READ=false`（默认）：未登录用户可以访问公开分组/站点，但无法看到私密内容，也没有写权限
- `AUTH_REQUIRED_FOR_READ=true`：未登录用户会被要求先登录，行为与旧版本一致
- 已登录管理员仍然拥有全部增删改查权限
- 建议为敏感内容设置 `is_public = 0`，并仅分享公开链接给访客

**Q: 如何关闭（或重新开启）访客访问？**

A:
1. 在 `wrangler.jsonc` 及 Cloudflare 控制台把 `AUTH_REQUIRED_FOR_READ` 改为目标值（`true`=关闭访客，`false`=开启）
2. 重新部署 Worker（`pnpm deploy` 或通过 CI）
3. 刷新页面后即可生效，无需迁移数据库

---

### 性能和限制

**Q: Cloudflare Workers 免费版有什么限制？**

A: 免费版限制：
- 每天 100,000 次请求
- CPU 时间：10ms/请求
- D1 数据库：每天 100,000 次读取，1,000 次写入
- 存储空间：500MB

对于个人导航站来说，这些限制绰绰有余。

---

**Q: 我可以导入多少个网站？**

A: 理论上没有限制，但实际受限于：
- D1 数据库大小（免费版 500MB）
- 单个导入文件大小（1MB）
- 浏览器性能（过多网站可能导致页面卡顿）

建议每个分组不超过 20 个网站，总数不超过 500 个。

---

**Q: 如何查看部署日志和错误信息？**

**通过 Cloudflare 控制台：**
1. 进入 **Workers & Pages** > 选择你的项目
2. 点击 **Logs** 标签
3. 查看实时日志

**通过命令行（开发者）：**
```bash
wrangler tail
```

---

### 其他问题

**Q: 我能修改代码吗？可以商用吗？**

A: 可以！NaviHive 采用 MIT 开源许可证，你可以：
- ✅ 自由修改代码
- ✅ 商业使用
- ✅ 二次开发
- ✅ 分发和销售
- ⚠️ 但需保留原作者版权声明

---

**Q: 遇到其他问题怎么办？**

1. 查看项目的 [Issues 页面](https://github.com/zqq-nuli/Cloudflare-Navihive/issues)
2. 搜索是否有人遇到过类似问题
3. 如果没有，创建新 Issue 并详细描述问题（包括错误信息、操作步骤、浏览器版本等）

---

## 🗂️ 项目结构

```
Cloudflare-Navihive/
├── worker/                  # Cloudflare Workers 后端
│   └── index.ts             # Workers 入口文件，API 路由定义
├── src/                     # React 前端源码
│   ├── API/                 # API 客户端层
│   │   ├── client.ts        # 真实 HTTP 客户端
│   │   ├── mock.ts          # Mock 客户端（开发用）
│   │   └── http.ts          # 类型定义和服务端 API
│   ├── components/          # React 组件
│   │   ├── GroupCard.tsx    # 分组卡片组件
│   │   ├── SiteCard.tsx     # 网站卡片组件
│   │   ├── LoginForm.tsx    # 登录表单
│   │   ├── SortableGroupItem.tsx  # 可拖拽分组
│   │   ├── SiteSettingsModal.tsx  # 全局设置弹窗
│   │   └── ThemeToggle.tsx  # 主题切换按钮
│   ├── App.tsx              # 主应用组件
│   └── main.tsx             # 应用入口
├── public/                  # 静态资源
├── migrations/              # D1 数据库迁移脚本（含 is_public 字段）
│   └── 002_add_is_public.sql
├── scripts/                 # 工具脚本
│   └── hash-password.ts     # 密码哈希生成工具
├── wrangler.jsonc           # Cloudflare Workers 配置
├── vite.config.ts           # Vite 构建配置
├── tsconfig.json            # TypeScript 配置
├── tailwind.config.js       # Tailwind CSS 配置
└── package.json             # 项目依赖和脚本
```

### 关键文件说明

| 文件 | 作用 |
|------|------|
| `worker/index.ts` | 后端 API 路由，数据库操作，身份认证 |
| `src/App.tsx` | 前端主组件，状态管理，布局渲染 |
| `src/API/client.ts` | API 客户端，处理所有 HTTP 请求 |
| `wrangler.jsonc` | Workers 配置，环境变量，D1 绑定 |
| `vite.config.ts` | 前端构建配置，开发服务器设置 |
| `migrations/002_add_is_public.sql` | 为免登陆模式添加 `is_public` 字段和索引 |

## 🤝 贡献指南

欢迎所有形式的贡献！无论是报告 Bug、提出新功能建议，还是提交代码改进。

### 如何贡献

1. **Fork 本仓库** 到你的 GitHub 账号
2. **克隆到本地**：`git clone https://github.com/your-username/Cloudflare-Navihive.git`
3. **创建特性分支**：`git checkout -b feature/amazing-feature`
4. **提交更改**：`git commit -m 'feat: 添加某个很棒的功能'`
5. **推送到分支**：`git push origin feature/amazing-feature`
6. **提交 Pull Request**，描述你的更改内容

### 提交规范

请遵循 [Conventional Commits](https://www.conventionalcommits.org/) 规范：

- `feat:` 新功能
- `fix:` Bug 修复
- `docs:` 文档更新
- `style:` 代码格式调整（不影响功能）
- `refactor:` 代码重构
- `perf:` 性能优化
- `test:` 测试相关
- `chore:` 构建工具或辅助工具的变动

### 开发前准备

```bash
# 安装依赖
pnpm install

# 启动开发服务器
pnpm dev

# 运行代码检查
pnpm lint

# 格式化代码
pnpm format
```

### 寻求帮助

- 📖 查看 [CLAUDE.md](CLAUDE.md) 了解项目详细架构
- 💬 在 [Issues](https://github.com/zqq-nuli/Cloudflare-Navihive/issues) 中提问
- 🐛 报告 Bug 时请包含：错误信息、复现步骤、浏览器版本

## 📄 许可证

本项目基于 [MIT License](LICENSE) 开源协议发布。

这意味着你可以：
- ✅ 自由使用、修改和分发本项目
- ✅ 用于商业用途
- ✅ 私有化部署
- ⚠️ 但需保留原作者版权声明

详见 [LICENSE](LICENSE) 文件。

## 🙏 致谢

感谢以下开源项目和服务，让 NaviHive 成为可能：

### 技术框架
-   [React](https://reactjs.org/) - 用户界面构建库
-   [TypeScript](https://www.typescriptlang.org/) - JavaScript 超集
-   [Vite](https://vitejs.dev/) - 下一代前端构建工具

### UI 组件
-   [Material UI](https://mui.com/) - React 组件库
-   [DND Kit](https://dndkit.com/) - 拖拽交互工具
-   [Tailwind CSS](https://tailwindcss.com/) - 原子化 CSS 框架

### 云服务
-   [Cloudflare Workers](https://workers.cloudflare.com/) - 边缘计算平台
-   [Cloudflare D1](https://developers.cloudflare.com/d1/) - 分布式数据库

### 开发工具
-   [Claude Code](https://claude.ai/code) - AI 辅助开发
-   [Cursor](https://www.cursor.com) - AI 代码编辑器

### 社区支持
感谢所有提交 Issue、PR 和 Star 的开发者们！🌟

## 📅 更新日志

### v1.1.0 (2025-01-08) - 免登陆访客模式
- ✨ 新增 `AUTH_REQUIRED_FOR_READ` 开关，支持公开只读访问
- 🗃️ 数据库新增 `is_public` 字段及索引，私密/公开内容可精细控制
- 🧭 前端添加访客/编辑双模式，未登录时仅渲染公开内容
- 📘 文档与部署流程更新，提供旧项目迁移指南
- 🧱 登录端点内置速率限制（5 次尝试 / 15 分钟），阻断暴力破解

### 🔒 安全更新版本 (2025-01-08)
- 🔐 **[CR-001]** 实现 JWT 签名（Web Crypto API + HMAC-SHA256）
- 🛡️ **[CR-003]** XSS 防护（CSS 代码沙箱化，移除危险模式）
- 🚫 **[CR-004]** SSRF 防护（私有 IP 地址过滤）
- 💉 **[CR-002]** SQL 注入防护（参数化查询）
- 🍪 **[HS-001]** HttpOnly Cookie（防止 XSS 窃取 Token）
- 🔒 **[HS-003]** bcrypt 密码哈希（10 轮盐值加密）
- 🌐 **[HS-004]** CORS 白名单配置
- 🆔 **[HS-005]** 结构化错误日志（唯一错误 ID）
- 🧱 登录端点速率限制（超出 5 次 / 15 分钟即返回 429 并记录 IP）
- ✅ **[MS-001]** TypeScript 严格模式（修复 65+ 类型错误）
- 📦 **[MS-005]** 请求体大小限制（最大 1MB）
- 🧪 **[MS-007]** 深度数据验证（导入操作）

> 📝 共计 10 次安全提交，全面提升系统安全性

---

### v1.0.4 (2025-04-22)
- ✨ 新增"记住我"登录功能，可选 30 天长效 Token
- 🐛 修复 URL 正则表达式转义字符问题
- 🔐 优化 Token 过期时间管理机制

### v1.0.3 (2025-04-14)
- 🖼️ 增加背景图片设置功能
- 🎨 新增蒙版透明度调节功能

### v1.0.2 (2025-04-09)
- 🐛 修复导入数据时自定义样式为空的报错问题
- 🐛 修复导入数据产生重复数据的 Bug
- 🐛 修复无卡片时排序无法保存的问题
- ✨ 新增导入数据智能合并功能（按 URL 匹配）
- ✨ 新增分组折叠展开功能

### v1.0.1 (2025-04-06)
- 🔄 更新 Chrome 浏览器标签数据转换工具

### v1.0.0 (2025-04-05) 🎉
- 🚀 首次正式发布
- ✨ 完整的导航站功能实现
- 📚 分组管理与拖拽排序
- 🔐 JWT 用户认证系统
- 🌓 深色/浅色主题切换
- 📱 完全响应式设计
- 🎨 自定义 CSS 样式支持

---

## ⭐ 支持项目

如果 NaviHive 对你有帮助，欢迎通过以下方式支持：

### 💝 给项目点赞
- 点击右上角的 ⭐ **Star** 按钮，这是对开发者最大的鼓励
- **Fork** 项目，参与改进和定制
- 分享给你的朋友和同事

### 💰 赞赏支持
你的赞赏将用于项目的持续开发和维护：

<div align="center">
  <img src="https://img.zhengmi.org/file/1743956440128_4b965550184c06d8164f8077fa42b5d.jpg" alt="微信赞赏码" width="300">
  <p><em>微信扫码赞赏</em></p>
</div>

### 🤝 其他支持方式
- 💬 提交有价值的 Issue 和 Feature Request
- 📝 改进文档和教程
- 🐛 报告 Bug 并提供复现步骤
- 💻 贡献代码（欢迎提交 PR）

---
## 📈 Star History

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=zqq-nuli/Cloudflare-Navihive&type=Date&theme=dark" />
  <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=zqq-nuli/Cloudflare-Navihive&type=Date" />
  <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=zqq-nuli/Cloudflare-Navihive&type=Date" />
</picture>

---

<div align="center">

## 🎉 让导航管理更简单

**NaviHive** - 你的专属网络导航中心

[立即部署](https://deploy.workers.cloudflare.com/?url=https://github.com/zqq-nuli/Cloudflare-Navihive) · [在线演示](https://navihive.chatbot.cab/) · [提交问题](https://github.com/zqq-nuli/Cloudflare-Navihive/issues) · [参与贡献](https://github.com/zqq-nuli/Cloudflare-Navihive/pulls)

Made with ❤️ by [zqq-nuli](https://github.com/zqq-nuli)

⭐ 如果觉得有用，别忘了点个 Star 哦 ⭐

</div>

