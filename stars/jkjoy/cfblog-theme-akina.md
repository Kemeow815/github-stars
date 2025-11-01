---
project: cfblog-theme-akina
stars: 1
description: |-
    null
url: https://github.com/jkjoy/cfblog-theme-akina
---

## 鸣谢

感谢以下项目和资源，它们为本项目提供了灵感和支持：

- [Akina]

## 使用方法

1. Fork 本仓库到您的 GitHub 账户。
2. 在Cloudflare Pages中创建一个新项目，选择刚刚 Fork 的仓库。
3. 在部署设置中，添加以下环境变量：

```
VITE_API_URL
``` 
- 该变量应设置为 后端 API 的 URL。(也可以使用Wordpress网站地址,兼容大部分Wordpress REST API)

后端项目地址：[cfBLOG 后端](https://github.com/jkjoy/cloudflare-blog-REST-API)

4. 保存并部署项目。
