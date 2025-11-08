---
project: pansou-web
stars: 128
description: |-
    一个PanSou的简约版页面
url: https://github.com/fish2018/pansou-web
---

# PanSou Web

🚀 镜像集成Pansou前后端，开箱即用。

[![Multi-Arch](https://img.shields.io/badge/arch-amd64%20%7C%20arm64-blue)](https://github.com/fish2018/pansou-web)

## 快速开始

### 一键启动

```bash
docker run -d --name pansou -p 80:80 ghcr.io/fish2018/pansou-web
```

访问：http://localhost

### Docker Compose（推荐）

```bash
# 下载配置文件
curl -o docker-compose.yml https://raw.githubusercontent.com/fish2018/pansou-web/main/docker-compose.yml

# 启动服务
docker-compose up -d

# 查看日志
docker-compose logs -f
```

## 支持架构

镜像支持以下CPU架构：
- `linux/amd64` - Intel/AMD 64位处理器
- `linux/arm64` - ARM 64位处理器

Docker会自动选择适合您系统的架构版本。

## 环境变量

### 基础配置

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `DOMAIN` | `localhost` | 访问域名 |
| `ENABLED_PLUGINS` | `labi,zhizhen,shandian,duoduo,muou,wanou` | 启用的搜索插件（逗号分隔） |

> 🔌 **重要变更**: 从当前版本开始，必须通过 `ENABLED_PLUGINS` 显式指定要启用的插件，否则不会启用任何插件。

### Telegram频道配置

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `CHANNELS` | **已内置数十个频道，开箱即用，无需配置** | Telegram频道列表（逗号分隔） |

> 💡 **自定义频道**: 如需自定义，使用 `CHANNELS` 环境变量覆盖默认配置。

### 代理配置

| 变量名 | 默认值 | 说明 | 示例 |
|--------|--------|------|------|
| `PROXY` | 无 | 代理服务器地址 | `socks5://xxx.xxx.xxx.xxx:7897` |

**支持的代理类型：**
- SOCKS5代理: `socks5://xxx.xxx.xxx.xxx:7897`

**使用场景：**
- 访问被墙的Telegram频道
- 加速国外资源访问
- 企业内网代理

```bash
# 示例
-e PROXY=socks5://xxx.xxx.xxx.xxx:7897
```

### 性能配置

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `CACHE_ENABLED` | `true` | 是否启用缓存 |
| `CACHE_TTL` | `60` | 缓存过期时间（分） |
| `MAX_CONCURRENCY` | `200` | 最大并发数 |
| `MAX_PAGES` | `30` | 最大搜索页数 |

> ⚡ **性能优化**: 镜像已内置优化配置，通常无需调整。

### 认证配置（可选）

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `AUTH_ENABLED` | `false` | 是否启用认证功能 |
| `AUTH_USERS` | - | 用户账号配置，格式：`user1:pass1,user2:pass2` |
| `AUTH_TOKEN_EXPIRY` | `24` | Token有效期（小时） |
| `AUTH_JWT_SECRET` | 自动生成 | JWT签名密钥，建议手动设置 |

> 🔐 **安全认证**: 启用后，访问应用需要登录。适合需要访问控制的场景。

---

## 🎯 常见配置场景

### 场景1：个人使用（最小配置）

```bash
docker run -d \
  --name pansou \
  -p 80:80 \
  -v pansou-data:/app/data \
  --restart unless-stopped \
  ghcr.io/fish2018/pansou-web:latest
```

### 场景2：公网服务（带域名和SSL）

```bash
# 1. 准备SSL证书
mkdir -p /opt/pansou/ssl
# 将证书放到 /opt/pansou/ssl/fullchain.pem 和 privkey.pem

# 2. 启动容器
docker run -d \
  --name pansou \
  -p 80:80 \
  -p 443:443 \
  -e DOMAIN=pansou.example.com \
  -v pansou-data:/app/data \
  -v /opt/pansou/ssl:/app/data/ssl:ro \
  --restart unless-stopped \
  ghcr.io/fish2018/pansou-web:latest
```

### 场景3：需要代理访问Telegram

```bash
docker run -d \
  --name pansou \
  -p 80:80 \
  -e PROXY=socks5://xxx.xxx.xxx.xxx:7897 \
  -v pansou-data:/app/data \
  --restart unless-stopped \
  ghcr.io/fish2018/pansou-web:latest
```

**注意：**
- 使用 `--network host` 以访问宿主机代理
- 或者将代理服务也容器化并使用 docker 网络

### 场景4：启用访问认证

```bash
docker run -d \
  --name pansou \
  -p 80:80 \
  -e AUTH_ENABLED=true \
  -e AUTH_USERS=admin:MySecretPass123,viewer:ViewOnly456 \
  -e AUTH_TOKEN_EXPIRY=168 \
  -e AUTH_JWT_SECRET=$(openssl rand -base64 32) \
  -v pansou-data:/app/data \
  --restart unless-stopped \
  ghcr.io/fish2018/pansou-web:latest
```

---

## 📁 数据目录说明

### 卷挂载

**推荐：使用命名卷（Docker管理）**
```bash
-v pansou-data:/app/data
```

**或：使用绑定挂载（指定宿主机路径）**
```bash
-v /opt/pansou/data:/app/data
```

### 目录结构详解

```
/app/data/
│
├── cache/                          # 缓存目录（约100MB-1GB）
│   ├── disk/                       # 磁盘缓存
│   │   ├── [hash].cache           # 搜索结果缓存
│   │   └── metadata.db            # 缓存元数据
│   └── qqpd_users/                # QQPD插件数据
│       └── [hash].json            # 用户配置和频道
│
├── logs/                           # 日志目录（建议定期清理）
│   ├── backend/                    # 后端日志
│   │   └── pansou.log             # 主日志文件
│   └── nginx/                      # Nginx日志
│       ├── access.log             # 访问日志
│       └── error.log              # 错误日志
│
└── ssl/                            # SSL证书目录
    ├── fullchain.pem              # 完整证书链
    └── privkey.pem                # 私钥
```
