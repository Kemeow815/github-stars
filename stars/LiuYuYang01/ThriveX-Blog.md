---
project: ThriveX-Blog
stars: 617
description: |-
    🎉 ThriveX 是一个年轻、高颜值、全开源、永不收费的现代化博客管理系统。它采用前后端分离开发模式，是一个 NextJS + Spring Boot 的产物
url: https://github.com/LiuYuYang01/ThriveX-Blog
---

<p align="center">
    <a href="https://liuyuyang.net" target="_blank">
        <img width="100" src="https://bu.dusays.com/2024/11/17/6739adf188f64.png" alt="ThriveX logo" style="width:100px" />
    </a>
</p>

<p align="center" style="font-size:20px; font-weight:700;">ThriveX</p>

<p align="center" style="margin-bottom:10px">年轻、高颜值、全开源、永不收费的现代化博客管理系统</p>

![](https://bu.dusays.com/2024/11/25/67445b7df3742.png)


项目预览：[https://liuyuyang.net/](https://liuyuyang.net/)

项目官网：[https://thrivex.liuyuyang.net/](https://thrivex.liuyuyang.net/)

项目文档：[https://docs.liuyuyang.net/](https://docs.liuyuyang.net/)



# 🎉 ThriveX 现代化博客管理系统

🎉 `ThriveX` 是一个年轻、高颜值、全开源、永不收费的现代化博客管理系统，它是一个基于 `NextJS` + `Spring Boot` 的产物，所有技术栈都是目前市面上最主流的

🛠️ **技术架构：**

前端：React **19**、**Next.js 15**、**TailwindCSS 4**、TypeScript、Zustand、Motion React、React Form Hooks、Echarts、Antd、Scss、Vercel、Docker


后端：**Spring Boot**、Mybatis Plus、MySQL、X File Storage、Swagger、Docker


❤️ **项目初衷：**

一直对网站开发领域很感兴趣，从小就希望有一个属于自己的网站，因此踏上了 `Web` 全栈开发的旅途，立志有朝一日也能开发一款属于自己的网站。如今历时 `2` 年有余，一个人从 `0` 到 `1` 独立完成整个项目的全栈开发，也算是完成了从小的一个心愿



## 项目演示

### 前端

这里只演示部分前端界面，具体大家可以自行查看 **->** [https://liuyuyang.net](https://liuyuyang.net)
![首页](https://bu.dusays.com/2024/10/28/671f7a44631d7.png)
![足迹](https://bu.dusays.com/2024/09/17/66e97036dddcb.png)



### 控制端

![数据分析](https://bu.dusays.com/2024/09/17/66e97035726ae.png)
![文件系统](https://bu.dusays.com/2024/09/17/66e97031cd456.png)



## 项目部署

前端：[https://docs.liuyuyang.net/docs/项目部署/前端.html](https://docs.liuyuyang.net/docs/项目部署/前端.html)
控制端：[https://docs.liuyuyang.net/docs/项目部署/控制端.html](https://docs.liuyuyang.net/docs/项目部署/控制端.html)
后端：[https://docs.liuyuyang.net/docs/项目部署/后端.html](https://docs.liuyuyang.net/docs/项目部署/后端.html)



## 项目结构

```
├── public // 存放公共资源
├── src // 核心源码
│   ├── api // 所有API接口
│   ├── app
│   │   ├── error.tsx // 自定义错误页
│   │   ├── favicon.ico // 项目图标
│   │   ├── layout.tsx // 网站布局
│   │   ├── loading.tsx // 自定义加载页
│   │   ├── not-found.tsx // 自定义404页
│   │   ├── page.tsx // 首页
│   ├── assets // 存放项目所有资源
│   │   ├── font
│   │   ├── image
│   │   └── svg
│   ├── components // 公共组件
│   ├── stores // 数据全局共享
│   ├── styles // 全局样式
│   ├── types // 全局类型
│   └── utils // 通用方法
├── package-lock.json
├── package.json
├── postcss.config.mjs
├── tailwind.config.ts
└── tsconfig.json
```




## 开源地址

### 2.0 最新版（Nextjs + Spring Boot）

前端：[LiuYuYang01/ThriveX-Blog (github.com)](https://github.com/LiuYuYang01/ThriveX-Blog)

控制端：[LiuYuYang01/ThriveX-Admin (github.com)](https://github.com/LiuYuYang01/ThriveX-Admin)

后端：[LiuYuYang01/ThriveX-Server (github.com)](https://github.com/LiuYuYang01/ThriveX-Server)



### 1.0 旧版（Vue3 + Python Flask）

前端：[LiuYuYang01/Thrive-Blog (github.com)](https://github.com/LiuYuYang01/Thrive-Blog)

控制端：[LiuYuYang01/Thrive-Admin (github.com)](https://github.com/LiuYuYang01/Thrive-Admin)

后端：[LiuYuYang01/Thrive-Server (github.com)](https://github.com/LiuYuYang01/Thrive-Server)

![后台](https://bu.dusays.com/2024/09/17/66e96ca781d49.png)



## 开源协议

为了项目的生态越来越强大，作者在这里恳请大家保留 `ThriveX` 博客系统版权

在项目 `Star` 突破 `2K` 后大家可自由选择删除 `or` 保留

如果对该项目进行二次开发，最终需将项目进行开源并保留版权 且 禁止任何商业行为

最后希望大家能够请遵守开源协议：**AGPL-3.0 license** 

弘扬开源精神，从你我做起！



## 关于项目

这个项目是我一个人从设计 -> 产品 -> 前端 -> 控制端 -> 后端以及数据库从 `0` 到 `1` 创造的，一个人的精力有限，项目可能会存在一些隐藏的 `BUG`，希望大家能够及时在 `GitHub` 提交 `Issue`，这样也好加以改正，不断改善，成为最佳！

当然我更希望大家能够提交 `PR` 成为 `ThriveX` 的贡献者，大家一起参与进来，构建一个强大的博客管理系统！


## 特别鸣谢

该项目的风格借鉴了很多优秀网站的灵感，下面我主要列举几个：

[https://blog.zwying.com/](https://blog.zwying.com/)

[https://www.blatr.cn/](https://www.blatr.cn/)

[https://poetize.cn/](https://poetize.cn/)



## ThriveX 交流群 🔥

加微信：`liuyuyang2023`   记得备注：拉群

![微信](https://bu.dusays.com/2025/06/03/683e96eb43ad8.jpg)


## 技术支持

项目部署 + `3` 天答疑服务 一口价 `200`，不议价哦。

不过我不太提倡，因为我时间比较忙。大家可以在上述找到我的微信进入官方交流群，在我或热心网友闲的时候也会免费帮忙解决问题的



# 常见疑惑

下面总结一些大家常问的疑惑


## 为什么会想到开发这个项目？

**问：** 为什么会想到开发这个项目？

**答：** 在开发这个项目之前我也使用了很多流行的博客系统，比如：`WordPress`（使用了两年）、`Emlog`、`Zblog`（一年）、`Typecho`（两年）

这些系统都有一个共同点，它们都是基于 `PHP` 开发的，如果不会 `PHP` 就不好自定义网站主题和功能插件，只能去找别人写好的，如果别人没有写，那么你就没办法用，这样就会有很大的局限性。

关键是 `PHP` 在国内几乎已经被淘汰了，所以没有必要再去刻意学习这门语言。

出于局限性我就萌生了开发一整个博客系统的想法，从 `22` 年正式落实并开发，目前已经持续完成三大版本，分别是：

1. Vue2 + Express（Nodejs）
2. Vue3 + Flask（Python）
3. NextJS + Spring Boot（Java）

样式借鉴了很多大佬的网站风格，但代码都是自己一行一行敲出来的，目前在 `Github` 已有近 `3000` 次代码提交记录

项目的所有技术栈都是目前最主流的，是一个非常年轻的现代化博客管理系统 🎉



## 为什么不采用纯 JavaScript 全栈开发？

有些网友提出了这个问题，目前 `Nextjs + Spring Boot` 实在太臃肿了，完全可以采用 `Nextjs + Prisma` 纯 `JavaScript` 技术栈实现全栈开发，这样部署也方便。

是的，没错。

但我的想法是把前端、控制端 以及 后端全部分离，任何地方都可以相互独立出来。比如你想自己写前端，不管你使用哪些技术栈，只需要调用后端接口就可以自己开发。

如果使用了 `Nextjs` 做全栈，那么前后端就会捆绑起来，这样的话前端就必须使用 `React` 而且如果不懂 `Nextjs` 还会额外增加开发及学习成本



## 项目后期是否会考虑收费？

有很多跟我一样从 `0` 到 `1` 写博客系统的同行，但他们大多数以盈利为目地而开发，而且更新频率并不高，大家不信可以对比一下做个参考

而我可以在此承诺，`ThriveX` 在现在乃至未来不会以任何方式收费，就连赞助二维码都不会有，这一波格局直接拉满 😁

这个项目纯纯为爱发电，这一点是所有博客系统当中比不了的



## 项目会保持长期维护吗？

大家可能会觉得我不以盈利为目的最终会丧失热情导致不再维护，其实我想说这个顾虑可以打消

在这两年期间内我已经累计提交了近 `3000` 次代码，只要工作之余有时间我都会不断的更新维护，有任何 `BUG` 我都会及时解决



# 后续研发计划

## 前端

1. ~~照片墙页面~~
2. ~~闪念集成 `WangEditor` 编辑器~~
3. ~~资源懒加载~~
4. 优化文章翻页（待完成）



## 控制端

1. ~~素材库~~
2. ~~集成 `DeepSeek` 文章优化~~
3. ~~文件列表懒加载~~
4. ~~优化 RBAC 权限~~
5. ~~批量通过 `Markdown` 文件导入文章~~
6. 文件上传多个导致偶尔无法复制
7. 修改前端 `ico` 图标没有效果



## 后端

1. 约束指定域名才能调用后端接口
2. 对外开放的 post 接口做个频率限制
