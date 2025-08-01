---
project: UploadGithubForTypecho
stars: 72
description: |-
    Typecho文章附件上传Github仓库插件
url: https://github.com/AyagawaSeirin/UploadGithubForTypecho
---

# UploadGithubForTypecho
本插件用于将文章附件上传至Github，并使用jsDelivr进行文件访问加速。

## 插件说明
本插件适用于Tyoecho。
本插件用于将文章附件上传至Github的仓库中，在添加图片进入文章时会替换链接为jsDelivr的地址。<br>
jsDelivr为融合CDN，在全球分布750余节点（包括中国），并Github仓库文件提供免费的访问加速服务。<br>
本插件利用此服务来加速文章附件（图片等）访问速度。
关于jsDelivr运用于博客的优势本文不再赘述，具体请[访问这里](https://qwq.best/dev/113.html "访问这里")。<br>

## 最新版本
1.1.1 - 2021.09.26

更新内容：

```txt
修改API调用格式, 修复无法上传到GitHub的问题
```

## 安装插件
项目地址：<https://github.com/AyagawaSeirin/UploadGithubForTypecho><br>
[点击这里直接下载](https://github.com/AyagawaSeirin/UploadGithubForTypecho/archive/master.zip "点击这里直接下载")<br>
解压至插件目录并将文件夹重命名为“UploadGithubForTypecho”

## 注意事项
请先在Github创建一个**公开**的仓库。

## 配置插件
启用插件并进入设置页面。<br>
需要设置的内容：<br>
Github用户名：必填，您的Github用户名。<br>
Github仓库名：必填，您用于储存附件文件的仓库名称。<br>
Github账号token：必填，您的Github账号的token，不知道如何获取账号token请[点击这里](https://qwq.best/dev/151.html "点击这里")。<br>
Github仓库内的上传目录：必填，附件上传到的仓库内目录位置。如果您不知道如何填写，建议保持默认内容。<br>
文件链接访问方式：建议选择"访问最新版本"。若修改图片，直接访问方式不方便更新缓存。<br>
是否保存在本地：是否将文件保存到本地<br>
> 以下两个参数为选填，留空则为仓库所有者信息。若填写则必须两个都填写。如果您不知道该如何填写，默认即可，不需要修改。不建议留空，这样可以区分哪些文件是插件提交的。建议您保持默认内容。

提交文件者名称：选填，提交Commit的提交者名称，留空则为仓库所属者。<br>
提交文件者邮箱：选填，提交Commit的提交者邮箱，留空则为仓库所属者。<br>

## 使用说明
插件**不会验证配置的正确性**，请**自行确认配置信息正确**，否则不能正常使用。<br>
插件会**替换所有之前上传的文件的链接**，若启用插件前存在已上传的文件，**请自行将其上传至仓库相同目录中以保证正常显示**；同时，禁用插件也会导致链接恢复。<br>
**由于Linux权限问题，可能会由于无法创建目录导致文件保存到本地失败而报错异常，请给予本地上传目录777权限。**<br>
  **您也可以选择不保存到本地，但可能导致您的主题或其他插件的某些功能异常。**<br>
  **您也可以在每一月手动创建当月的目录，避免出现目录创建失败问题（推荐）。**<br>
由于CDN缓存问题，修改文件后访问链接可能仍然是旧文件，所以**建议删掉旧文件再上传新文件**，**不建议使用修改文件功能**。jsDelivr刷新缓存功能暂未推出，推出后本插件会及时更新。<br>
在插件设置页面会自动检查更新，若检查失败请手动前往项目地址检查更新。<br>
Github API限制每个IP每小时只能请求60次接口，请控制您操作图片(上传修改删除)的频率。<br>

