---
project: SubsTracker
stars: 249
description: |-
    基于Cloudflare Workers的轻量级订阅管理系统，帮助您轻松跟踪各类订阅服务的到期时间，并通过Telegram发送及时提醒。
url: https://github.com/wangwangit/SubsTracker
---

# SubsTracker - 订阅管理与提醒系统

基于Cloudflare Workers的轻量级订阅管理系统，帮助您轻松跟踪各类订阅服务的到期时间，并通过Telegram,微信等发送及时提醒。

![image](https://github.com/user-attachments/assets/22ff1592-7836-4f73-aa13-24e9d43d7064)


## ✨ 特性

- 🔔 **自动提醒**: 在订阅到期前自动发送Telegram通知
- 📊 **订阅管理**: 直观的Web界面管理所有订阅
- 🔄 **周期计算**: 智能计算循环订阅的下一个周期
- 📱 **响应式设计**: 完美适配移动端和桌面设备
- ☁️ **免服务器**: 基于Cloudflare Workers，无需自建服务器
- 🔒 **安全可靠**: 数据存储在Cloudflare KV中，安全且高效

## 版本更新
V0: TG通知 

v1: TG通知+NotifyX通知 

V2: 

✅ 订阅列表按到期日期升序排序 

✅ 修复了提醒天数逻辑（reminderDays: 0 只在到期日提醒） 

✅ 添加了自动续费切换功能（autoRenew 字段） 

✅ 增强了测试通知功能（在配置页面独立测试按钮） 

✅ 实现了Toast通知系统 

✅ 表单验证和错误处理 

✅ 安全配置（不返回敏感信息） 

## 🚀 部署指南

### 前提条件

- Cloudflare账户
- Telegram Bot (用于发送通知)
- 可以直接将代码丢给AI,帮助查漏补缺

### 部署步骤

1.登陆cloudflare,创建worker,粘贴本项目中的js代码,点击部署

![image](https://github.com/user-attachments/assets/ff4ac794-01e1-4916-b226-1f4f604dcbd3)


2.创建KV键值 **SUBSCRIPTIONS_KV**

![image](https://github.com/user-attachments/assets/c9ebaf3e-6015-4400-bb0a-1a55fd5e14d2)


3.给worker绑定上键值对,以及设置定时执行时间!

![image](https://github.com/user-attachments/assets/25b663b3-8e8e-4386-a499-9b6bf12ead76)


4.打开worker提供的域名地址,输入默认账号密码: admin  password (或者admin admin123),可以在代码中查看默认账号密码!

![image](https://github.com/user-attachments/assets/5dac1ce0-43a3-4642-925c-d9cf21076454)


5.前往系统配置,修改账号密码,以及配置tg通知的信息

![image](https://github.com/user-attachments/assets/f6db2089-28a1-439d-9de0-412ee4b2807f)


6.配置完成可以点击测试通知,查看是否能够正常通知,然后就可以正常添加订阅使用了!

![image](https://github.com/user-attachments/assets/af530379-332c-4482-9e6e-229a9e24775e)


## 赞助
本项目的 CDN 加速和安全保护由腾讯 EdgeOne 赞助。
[Best Asian CDN, Edge, and Secure Solutions - Tencent EdgeOne](https://edgeone.ai/?from=github)
![image](https://edgeone.ai/media/34fe3a45-492d-4ea4-ae5d-ea1087ca7b4b.png)

## 🤝 贡献

欢迎贡献代码、报告问题或提出新功能建议!

## 📜 许可证

MIT License


