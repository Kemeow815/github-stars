---
project: LibreDomains
stars: 65
description: |-
    免费公益二级域名，点点star~
url: https://github.com/LibreSpark/LibreDomains
---

# LibreDomains - 自由域名分发服务

LibreDomains 是一个开源的二级域名分发服务，允许用户通过 GitHub Pull Request 来申请和管理二级域名。

## 快速导航

- 🚀 [开始申请域名](#申请域名) - 立即申请你的免费二级域名
- 📖 [完整指南](GUIDE.md) - 用户和管理员的详细教程
- 🤖 [技术文档](CLAUDE.md) - 给开发者和 AI 的项目架构说明

## 可用域名

目前，本项目提供以下域名：

| 域名 | 状态 | 描述 |
|------|------|------|
| ciao.su | ✅ 可用 | 主要域名 |
| ciallo.de | ⏸️ 暂停开放 | 备用域名 |

## 申请域名

### 申请步骤

1. Fork 本仓库
2. 在 `domains/[域名]/` 目录下创建一个以你想要申请的子域名命名的 JSON 文件
   - 例如: `domains/ciao.su/mysubdomain.json`
3. 按照下面的格式填写 JSON 文件
4. 提交 Pull Request
5. 等待自动检查和审核
6. Pull Request 被合并后，你的域名记录将在几分钟内生效

### JSON 格式

在 `domains/[域名]/[子域名].json` 创建配置文件。详细格式和示例请参见[完整指南](GUIDE.md#2-创建配置文件)。

### 支持的 DNS 记录类型

- `A` - IPv4 地址
- `AAAA` - IPv6 地址
- `CNAME` - 别名
- `TXT` - 文本记录
- `MX` - 邮件交换记录

### 规则

1. 子域名必须由小写字母、数字和连字符组成
2. 子域名长度在 3-63 个字符之间
3. 子域名不能以连字符开头或结尾
4. 一个 GitHub 用户最多可以申请 3 个子域名
5. 每个子域名最多可以有 10 个 DNS 记录
6. **不允许申请保留的子域名**（如 `www`, `api`, `admin` 等系统关键子域名，详见[完整指南 - 保留子域名说明](GUIDE.md#保留子域名说明)）

## 管理域名

编辑你的 JSON 文件并提交新的 Pull Request 即可更新。详见[完整指南](GUIDE.md#更新域名记录)。

## 贡献代码

欢迎提交 Pull Request 来改进本项目！技术架构和实现细节请参见 [CLAUDE.md](CLAUDE.md)。

## 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件

