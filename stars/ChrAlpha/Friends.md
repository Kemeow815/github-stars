---
project: Friends
stars: 2
description: |-
    你这是要和 ChrAlpha 交换友链吗？
url: https://github.com/ChrAlpha/Friends
---

# [ChrAlpha 的好伙伴](https://ichr.me/links/)

你这是要和 ChrAlpha 交换友链嘛？

## 交换原则

为不使 ChrAlpha 的友链页沦为引流的工具，还是得有些规矩的。

友链友链，先友后链。最好先混个脸熟再来交换呢！除非你的内容真的让我一眼爱上，否则可别怪我直接挂掉初次见面的人的请求哈。

网站的域名是很重要的，免费域名可以绕路了哦。

> 任何包含于 Public Suffix List 的免费子域名服务，如 `github.io`，`gitlab.io`，`now.sh` 等，均不属于「免费域名」之列。

内容有触犯中国大陆及港澳台地区法律法规、违背普世价值观的还是不要了吧。充斥着采集、洗稿的网站也是很讨厌的。原创、实质性内容占比一定不能低，宁可长草，不滥竽充数。

**不接受**纯技术博客，通篇题解、代码这些的也实在很难让人特地打开来看下去。相比之下，你的思考、思维方式或许更能吸引到他人，当然也包括我。

> 至于「纯技术」的界定其实很模糊。即便是技术文章，只要包含了「你」的东西——你探索的过程也好、你对其看法展望之类的也罢，或许都不该称之为纯技术文章。因为那融入了你的灵魂，而非仅仅是枯燥的技术本身。

如果你自认为符合这些要求，那就继续往下看看如何和 ChrAlpha 交换友链吧！

## 如何交换

既然是「交换」，那也还请先将 ChrAlpha 先添加到你的友链中：

- 名称：`ChrAlpha's Blog` 或者 `ChrAlpha's Nerverland`
- URL：`https://ichr.me` 或者 `https://blog.ichr.me` 亦或 `https://chralpha.com`
- Slogan：`你必须拼尽全力，才能显得毫不费力` （非强制，也可以按你认为的来填）
- 头像：[链接](https://friends.ichr.me/img/ichr.me.jpg) （如果无需头像就不用管它啦）

然后，也要让我知道你的信息——Fork 本仓库并修改 `links.yml`：

- 将一张中心对称、不大于 512KB 的头像提交至 `src/img/` 下，命名格式为 `[domain].[format]`，如 `blog.ichr.me.png`
- 按照以下格式将你的信息添加到 `links.yml` 文件中

  ```yaml
  - name: "站点名称"  # 请使用双引号包裹
    url: https://example.com  # 你的网站的 URL
    avatar: example.com.png  # 头像的文件名
    desc: "Hello, World"  # Slogan，请使用双引号包裹
  ```

- 确保你所提供的所有网站信息（头像、描述等）适合展示给任何年龄段的任何人
- 完成后请新建一个 Pull Request

可别交换完友链就不管了，记得要经常互访互动的呀。

---

想法参考自 [SukkaW/Friends](https://github.com/SukkaW/Friends)，ChrAlpha 本人保留一切最终解释权。

