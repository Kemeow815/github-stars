---
project: TG-RUbot
stars: 34
description: |-
    null
url: https://github.com/Russellgogogogo/TG-RUbot
---

简体中文 | [English](README_EN.md)
# TG-RUbot: 最好的tg私信传话筒，无存储！零成本！消息隔离、emoji回应、拉黑、编辑、撤回
#TG 聊天机器人 #TG 私聊机器人 #TG 私信机器人

这是一个基于 Cloudflare Worker / Vercel 的 Telegram 双向私聊机器人，无需服务器、无需数据库、无需自己的域名即可轻松部署。

* TG 双向聊天机器人
   * 别人发消息给它，它把消息转发给你
   * 你发消息给它，它把消息复制给对应的人

## ✨ 特色功能

- 🔄 **双向通信** - 轻松接收和回复来自用户的消息
- 💾 **无需数据库** - 完全无状态设计，零存储成本
- 🌐 **无需自己的域名** - 使用 Cloudflare Worker 提供的免费域名
- 🚀 **轻量级部署** - 几分钟内即可完成设置
- 💰 **零成本运行** - 在 Cloudflare 免费计划范围内使用
- 🔒 **安全可靠** - 使用 Telegram 官方 API 和安全令牌
- 🔌 **多机器人支持** - 一个部署可注册多个私聊机器人
- 🛠️ **多种部署方式** - 支持 GitHub 一键部署、Vercel 一键部署、Wrangler CLI 和 Dashboard 部署
- 🤖 **更强的RUbot模式** - 消息分离、对话拉黑、消息编辑、消息删除、emoji回应、备注、消息引用

## 为什么需要它？

* 据说直接私聊会被 tg 重点关注，容易封号，是不是这样我也不知道，但好玩的东西就玩一玩呗
* 可以隐藏自己的本体账号，不被他人骚扰。
* 机器人玩法更多样有趣，比如我就在我的机器人里塞了个月亮

## 该怎么使用它？

* 根据下文项目部署指南，自部署使用，推荐使用免费的 CF worker
* 如果你是**LinuxDo 二级佬友**，[那么我提供完全免费且完全隐私安全的服务](https://linux.do/t/topic/620515)
   * 基于 CF worker，免费额度，没有运行成本的公益服务
   * 为什么要二级才行？
      * 免费额度有限，10W 每天 (?)，虽然够很多人用，但我怕坏人捣乱
      * 稍微给 L 站的账号增加一丢丢丢丢含金量🤏(?)
     

## 它和其他私聊机器人有什么异同？

* 它是基于并在部署和使用上完全兼容 [open-wegram-bot](https://github.com/wozulong/open-wegram-bot)（蹭蹭始皇~~的项目~~）
* 它保持了极高的易用性，小白亦可操作部署使用
* 可以零运行成本使用
   * 基于 cf worker 或 Vercel
   * **无任何数据存储在 tg 之外**，完全无隐私担忧
   * 你所需要的，只有一个 worker，即便是要多人使用子母模式，也只需要在加一个免费的 worker
* 它提供了使用更友好的 **RUbot 模式**

## RUbot 模式是什么？

* 消息分离，与多个人私聊时，不会再像各说各话的群一样混乱了
* 回复他人私信不再需要手动选择消息 replay，像原本私信一样，直接发送就好
* 消息被机器人转发后，有 emoji 提示，再也不用担心对方因为转发失败收不到了
* `/start` 呼出介绍信息
   * 对来访者，只有功能介绍
   * 对所属用户，在不同位置有不同的可用命令列表
      * 与机器人的私聊中
      * 私聊群组的 general topic 中
      * 私聊群组的私聊 topic 中
* 支持单向拉黑！（给对方上个沉默
   * 对方发送的消息和点击的表情，不会转发到topic中
   * 但自己在topic中发送的消息和点击的表情，会转发给对方
* 支持双向 emoji reaction！就是给消息点表情！
* 消息编辑
   * 直接使用原生 tg 的编辑功能即可
* 消息删除
   * replay 需要删除的消息，并发送内容 `#del`，即可删除之前已被机器人转发过去对面的消息
* 消息引用
   * 只需要像原生 tg 一样引用即可，可以引用自己的消息也可以引用对方的消息，转发时都会去引用在对应聊天中的对应消息
* 备注名称
    * 直接在 tg 修改 topic 的名称即可
    * 格式为 `备注 | name (id)`，以英文竖杆分割 `|`
    * 只有这种格式的备注会被保留，其他的会在收到新消息后被更新成 `name (id)` 的样式

## 看看效果？

惨，我只有一个 tg 号，没法展示那么全面。但它很简单，你可以直接部署或介入我提供的服务使用体验。

## 那么，如何使用 RUbot 模式 ？

先这样，再这样，然后那样，吧嗒！就行了！

* 创建机器人
* 机器人关联上服务
* 创建与机器人的个人聊天
* 创建一个群组作为私信群组并开启群组的 topic 功能
* 把机器人加入群组并设置成管理员
* 在群组 general Topic 输入命令 `.!pm_RUbot_doInit!.` 完成开启

手把手视频版，我自己使用了folder，又多了一步“把群组加入folder”：
https://www.youtube.com/embed/0WmkWLVDLRo?si=WzaxMwnkaa8BO9wg

## 可用命令

* 在**私聊群组的 general Topic** 中：
   * `.!pm_RUbot_checkInit!.`：检查初始化情况，结果回复在**与机器人的个人聊天**中
   * `.!pm_RUbot_doInit!.`：进行初始化设置，结果回复在**与机器人的个人聊天**中
   * `.!pm_RUbot_doReset!.`：重制初始化设置，结果回复在**与机器人的个人聊天**中
* 在**与机器人的个人聊天**中：
   * `.!pm_RUbot_doReset!.`：重制初始化设置
   * 拉黑是单向的（给对方上个沉默），即拉黑后
* 在**私聊对应的 Topic** 中：
   * `.!pm_RUbot_ban!.` ：拉黑发送命令所在的 topic ，不再转发对应聊天过来的消息，并且发消息告诉对方被 ban
   * `.!pm_RUbot_unban!.`：取消拉黑发送命令所在的 topic ，并且发消息告诉对方被 unban
   * `.!pm_RUbot_silent_ban!.`：与 `.!pm_RUbot_ban!.` 相同，但不给对方发消息提醒
   * `.!pm_RUbot_silent_unban!.`：与 `.!pm_RUbot_unban!.` 相同，但不给对方发消息提醒

## 注意！（FAQ）

* 开启 RUbot 模式时的**命令**发送在**群组的 general Topic**，而机器人在**个人聊天**中回复结果
* 使用 **原生个人号** 而不是频道 (channel) 在私信群组中发送消息和命令
* 在 RUbot 模式下，你会看到在群组的 General Topic 和你自己和机器人的聊天有一个 `Pinned message`
  不要随意修改它，**也不要新 pin 任何消息**，除非你清晰明白你在做什么有什么后果
  它是**无存储**实现的关键！
* 先给群组开启 topic 功能，开启完成后，再设置机器人为管理员，否则可能需要单独再设置一次 `Manage topics` 权限
* 他人首次私信时，被私信人会收到来自机器人的通知，因为新建 topic 后发的第一条信息，tg 原生的通知不够友好醒目

### 如果使用过程中发生了失效
用了一段时间，发现tg的 pinned message 对机器人的接口来说似乎有时效，我这边情况是消息14天消息没变更，机器人的接口就查不到了，做了下修复。
* 对于已经遇到这个问题的朋友
    * 找到那条存关系的 pinned message 消息或者自己发一条内容一样的，回复文本 `#fixpin`
    * 这个方法也可以用来修改关联信息，属于进阶用法，小白慎用，不要手动更改这条消息的内容，否则会出问题
* 对于还没遇到这个问题的朋友
    * 在有消息来临时会检查 pinned message 是否仍然有效，如果仍有效但已超过7天，则会重新pin一条以使后续可用
    * 检查和更新不是定时的，而是有使用才会触发，所以如果长时间没有使用发生了失效问题，可以使用上面的 `#fixpin` 来进行修复

## todo list

* ✅ 支持消息删除，回复需要删除的消息并发送 `#del`
* ✅ 支持消息编辑
* ✅ 支持 emoji 回应
* ✅ 拉黑指定用户，不转发其私信
* ✅ `/start` 呼出介绍
* 新消息通知汇总（避免消息混乱，操作跳转和已读，可配置开启，比较复杂）

## can't list
* ~~支持已读通知~~（好像做不成，没通知，我也有点不太喜欢这个功能其实）
* ~~通过 bot 主动私信他人~~（好像做不成，没法创建新的聊天）

# 部署指南

## 🛠️ 前置要求

- Cloudflare 账号
- Telegram 账号
- 一个科学工具（仅设置阶段需要，用于访问 Worker 默认域名，自绑域名无视）

## 📝 设置步骤

### 1. 获取 Telegram UID

> [!NOTE]
> 您需要知道自己的 Telegram 用户 ID (UID)，这是一串数字，用于将消息转发给您。

您可以通过以下方式获取：

- 向 [@userinfobot](https://t.me/userinfobot) 发送任意消息，它会告诉您自己的 UID

请记下您的数字 ID（例如：`123456789`）。

### 2. 创建 Telegram Bot

1. 在 Telegram 中搜索并打开 [@BotFather](https://t.me/BotFather)
2. 发送 `/newbot` 命令
3. 按照提示设置您的机器人名称和用户名（用户名必须以 `bot` 结尾）
4. 成功后，BotFather 会发给您一个 Bot API Token（格式类似：`000000000:ABCDEFGhijklmnopqrstuvwxyz`）
5. 请安全保存这个 Bot API Token

### 3. 选择部署方式

#### 方法一：GitHub 一键部署（推荐 ⭐）

这是最简单的部署方式，无需本地开发环境，直接通过 GitHub 仓库部署。

1. **Fork** 本仓库到您的 GitHub 账户
2. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)
3. 导航到 **Workers & Pages** 部分
4. 点击 **Create**
5. 选择 **Import a repository**
6. 授权 Cloudflare 访问您的 GitHub，并选择您 fork 的仓库
7. 配置部署设置：
   - **Project name**：设置您的项目名称（例如 `tg-rubot`）
   - **Production branch**：选择主分支（通常是 `master`）
   - 其他设置保持默认
8. 点击 **Save and Deploy** 按钮完成部署
9. 配置**运行时**环境变量：
   - 进入到 worker 的 **Settings** 标签页
   - 导航到 **Variables and Secrets**
   - 添加类型为**Plaintext**的 `PREFIX`（例如：`public`）
   - 添加类型为**Secret**的 `SECRET_TOKEN`（必须且只能包含大写和小写字母和数字，长度至少16位）

这种方式的优点是：当您更新 GitHub 仓库时，Cloudflare 会自动重新部署您的 Worker。

#### 方法二：Vercel 一键部署

Vercel 提供了另一种简单的部署方式，也支持从 GitHub 仓库自动部署。

1. 点击下方的"Deploy with Vercel"按钮：

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fwozulong%2Fopen-wegram-bot&env=SECRET_TOKEN,PREFIX&envDescription=配置您的机器人参数&project-name=open-wegram-bot&repository-name=open-wegram-bot)

2. 按照 Vercel 的提示完成部署流程
3. 配置环境变量：
   - `PREFIX`：设置为您想要的 URL 前缀（例如 `public`）
   - `SECRET_TOKEN`：设置一个安全的令牌（必须包含大小写字母和数字，长度至少16位）
4. 完成部署后，Vercel 会提供一个域名，如 `your-project.vercel.app`

Vercel 部署的优点是简单快速，支持自动更新，并且默认提供 HTTPS。

#### 方法三：使用 Wrangler CLI

如果您熟悉命令行工具，可以使用 Wrangler CLI 进行部署。

1. 确保安装了 Node.js 和 npm
2. 克隆本仓库：
   ```bash
   git clone https://github.com/wozulong/open-wegram-bot.git
   cd open-wegram-bot
   ```
3. 安装依赖：
   ```bash
   npm install
   ```
4. 部署 Worker：
   ```bash
   npx wrangler deploy
   ```
5. 设置您的安全令牌：
   ```bash
   npx wrangler secret put SECRET_TOKEN
   ```

#### 方法四：通过 Cloudflare Dashboard 手动部署

如果您不想使用 GitHub 或命令行，也可以直接在 Cloudflare Dashboard 中创建。

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 导航到 **Workers & Pages** 页面
3. 点击 **Create Worker**
4. 删除默认代码，粘贴本项目的 `src/worker.js` 和 `src/core.js` 代码
5. 点击 **Save and Deploy**
6. 在 Worker 设置中添加环境变量：
   - `PREFIX`（例如：`public`）
   - `SECRET_TOKEN`（必须包含大小写字母和数字，长度至少16位）

### 3.1 (可选) 绑定自定义域名 🌐

> [!TIP]
> 为您的 Worker 绑定自定义域名可以避免使用科学工具访问，更加便捷！

Cloudflare 允许您将自己的域名绑定到 Worker 上，这样您就可以通过自己的域名访问 Worker，而不需要使用被和谐的默认域名。

1. 在 Cloudflare 仪表板中添加您的域名
2. 在 Workers & Pages 部分，选择您的 worker
3. 点击 **Triggers**，然后点击 **Add Custom Domain**
4. 按照说明将您的域名绑定到 Worker

绑定后，您可以使用类似 `https://your-domain.com/YOUR_PREFIX/install/...` 的地址来注册/卸载机器人，无需科学工具。

### 4. 注册您的 Telegram Bot

部署 Worker 后，您将获得一个 URL，形如：
- GitHub 集成：`https://your-project-name.username.workers.dev`
- Vercel 部署：`https://your-project.vercel.app`
- Wrangler/Dashboard：`https://your-worker-name.your-subdomain.workers.dev`

现在您需要注册您的 Bot：

> [!WARNING]
> 由于 Cloudflare Workers 默认域名被和谐，此步骤需要科学。如果您已绑定自定义域名，可以直接使用您的域名进行访问，无需科学工具。

1. 在浏览器中访问以下 URL 来注册您的 Bot（替换相应参数）：

```
https://your-worker-url/YOUR_PREFIX/install/YOUR_TELEGRAM_UID/BOT_API_TOKEN
```

例如：
```
https://open-wegram-bot.username.workers.dev/public/install/123456789/000000000:ABCDEFGhijklmnopqrstuvwxyz
```

2. 如果看到成功消息，说明您的 Bot 已经注册成功

> [!NOTE]
> 一个 Worker 实例可以注册多个不同的 Bot！只需重复上述注册步骤，使用不同的 Bot API Token 即可。



### 卸载 Bot ❌

如果您想卸载 Bot，请访问以下 URL（替换相应参数）：

```
https://your-worker-url/YOUR_PREFIX/uninstall/BOT_API_TOKEN
```

## 🔒 安全说明

> [!IMPORTANT]
> 请妥善保管您的 Bot API Token 和安全令牌（Secret Token），这些信息关系到您服务的安全性。

> [!WARNING]
> **请勿随意更改已设置的 Secret Token！** 更改后，所有已注册的机器人将无法正常工作，因为无法匹配原来的令牌。如需更改，所有机器人都需要重新注册。

- 在初始设置时选择一个安全且便于记忆的 Secret Token
- 避免使用简单或常见的前缀名称
- 不要将敏感信息分享给他人

## ⚠️ 使用限制

> [!NOTE]
> Cloudflare Worker 免费套餐有每日 10 万请求的限制。

对于个人使用的私聊机器人来说，这个限制通常足够宽松。即使您注册了多个机器人，除非您的机器人极其活跃，否则不太可能达到这个限制。

如果您预计使用量较大，可以考虑升级到 Cloudflare 的付费计划。

## 🔍 故障排除

- **消息未转发**: 确保 Bot 已正确注册，并检查 Worker 日志
- **无法访问注册 URL**: 确认您是否相信科学，或者考虑绑定自定义域名解决访问问题
- **回复消息失败**: 检查您是否正确使用 Telegram 的回复功能
- **注册失败**: 确保您的 `SECRET_TOKEN` 符合要求（包含大小写字母和数字，长度至少16位）
- **GitHub 部署失败**: 检查环境变量是否正确设置，仓库权限是否正确
- **Worker 部署失败**: 检查 Wrangler 配置并确保您已登录到 Cloudflare

## 🤝 贡献与联系

如果您有任何问题、建议或想贡献代码，请提 Issue/PR 或通过以下方式联系我：

- [RUbot：最好的tg私信传话筒，无存储！零成本！消息隔离、emoji回应、拉黑、编辑、撤回 | 小打小闹](https://linux.do/t/topic/620510)

## 📄 许可证

- GPL v3，希望你能完善并继续开源，而不是改头换面闭源，谢谢。

---

希望这个工具能让您的 Telegram 私聊体验更加便捷！🎉 如果你只想直接使用，并且是LinuxDo二级佬友，请访问 [我提供的服务相关介绍](https://linux.do/t/topic/620515)
