---
project: api
stars: 43
description: |-
    🔍为停更的NeteaseCloudMusicAPI（网易云音乐API）提供持续活跃的维护, 并且新增一些有趣的功能！
url: https://github.com/NeteaseCloudMusicApiReborn/api
---

# 网易云音乐 API Reborn

---

## 项目简介

本项目为网易云音乐第三方 Node.js API，基于社区停更的原版 API 持续维护和升级，支持丰富的音乐相关接口，适合自建服务、二次开发和多平台部署(如果原版诈尸, 我会及时同步 or 归档)。

## 快速开始

### 环境要求

- Node.js 14 及以上
- 推荐使用 pnpm 进行依赖管理

### 安装

```bash
git clone https://github.com/NeteaseCloudMusicApiReborn/api.git
cd api
pnpm i
```

### 启动服务

```bash
# 默认端口 3000
node app.js

# 指定端口（如 4000）
PORT=4000 node app.js  # Mac/Linux
set PORT=4000 && node app.js  # Windows
```

### 重要提示

- 调用前请务必阅读文档的“调用前须知”部分。
- 推荐将敏感信息（如 cookie）通过部署平台的环境变量进行配置。

## 在线体验与文档

- [在线文档](https://music-api.focalors.ltd/docs/#)
- [NPM 包地址](https://www.npmjs.com/package/@neteaseapireborn/api)

## 常见部署方式

### Vercel 一键部署

1. fork 本项目
2. 在 Vercel 官网新建项目，导入 fork 的仓库
3. 直接 Deploy

### 腾讯云 Serverless 部署

1. fork 本项目
2. 在腾讯云 serverless 控制台新建 Web 应用，选择 Express 框架
3. 代码仓库选择 fork 的项目，启动文件填写：
   ```bash
   #!/bin/bash
   export PORT=9000
   /var/lang/node16/bin/node app.js
   ```
4. 完成部署后，访问 API 网关的 URL 即可

## Node.js 方式调用

支持直接在 Node.js 项目中引入和调用，返回 Promise：

```js
const { login_cellphone, user_cloud } = require('@neteaseapireborn/api')
async function main() {
  const result = await login_cellphone({ phone: '手机号', password: '密码' })
  console.log(result)
  const result2 = await user_cloud({ cookie: result.body.cookie })
  console.log(result2.body)
}
main()
```

## TypeScript 支持

```ts
import { banner } from '@neteaseapireborn/api'
banner({ type: 0 }).then((res) => console.log(res))
```

## 单元测试

```bash
pnpm test
```

## 主要功能特性

- 登录/注册/验证码
- 用户信息、歌单、动态、播放记录
- 歌曲、专辑、歌手、MV、歌词、评论、排行榜
- 搜索、推荐、私人 FM、签到、云盘
- 歌曲解锁（解灰）、多音源支持（qq/kuwo/kugou/migu/pyncmd）
- 详细接口请见[在线文档](https://music-api.focalors.ltd/docs/#)

## 贡献与社区

- 欢迎提交 PR、Issue 参与维护

## SDK 生态

| 语言   | 作者                                        | 地址                                                                                     | 类型   |
| ------ | ------------------------------------------- | ---------------------------------------------------------------------------------------- | ------ |
| Java   | [JackuXL](https://github.com/JackuXL)       | [NeteaseCloudMusicApi-SDK](https://github.com/JackuXL/NeteaseCloudMusicApi-SDK)          | 第三方 |
| Java   | [1015770492](https://github.com/1015770492) | https://github.com/1015770492/yumbo-music-utils                                          | 第三方 |
| Python | [盧瞳](https://github.com/2061360308)       | [NeteaseCloudMusic_PythonSDK](https://github.com/2061360308/NeteaseCloudMusic_PythonSDK) | 第三方 |

## License

[MIT License](https://github.com/IamFurina/NeteaseCloudMusicApiReborn/blob/main/LICENSE)
console.log(error)

