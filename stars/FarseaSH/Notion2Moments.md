---
project: Notion2Moments
stars: 1
description: |-
    null
url: https://github.com/FarseaSH/Notion2Moments
---

# Notion2Moments

> **Warn: 该项目还在最后测试中！**
>
> **Warn: 该项目还在最后测试中！**
>
> **Warn: 该项目还在最后测试中！**

## 部署方法

## Notion 的准备

**1. 将所需使用的 Notion 模版 拷贝至自己的 Notion 下**

- 点击打开此 [Notion2Moments模版](https://sticky-cotton-ad9.notion.site/856c69b89f9b46c5aaba8f1e16915ed0?v=05d976ec4040453e90f7a13796b3b8ed&pvs=74) 链接 *（建议右键在新新标签页打开）* 
- 点击右上角重叠方块 `duplicate` 按钮

![Duplicate datebase template](https://github.com/FarseaSH/hugo-theme-moments/assets/86035589/bb2e9eb4-b7f8-4ec9-803d-1709f3798add)

**2. 创建一个Notion Integration**

- 进入 Notion官方 [My integrations](https://www.notion.so/my-integrations) 页面 *（建议右键在新新标签页打开）* 
- 点击正中间 `New integration`，输入一个便于记忆区分的名称 (e.g MyMoments)，`Associated workspace`项选择刚才拷贝 database 所在的 Notion workplace，`Type`项不用更改，保持选择Internal即可

![New integration](https://github.com/FarseaSH/hugo-theme-moments/assets/86035589/f6560ba7-25dd-4bd0-ab12-ff92a478c368)

![Integration details](https://github.com/FarseaSH/hugo-theme-moments/assets/86035589/caf2a87a-012d-4772-ba9f-7bfbb6c15a39)

- 进入该 Integration，点击 Capabilities，**只勾选** `Read content` 以及圈选 `No user Infomation`。此项目只需读取 database 的内容，因此这里给予最小权限来保障自己 Notion 的安全
- （完成后可以顺带将 Notion Secret 复制下来保存起来，后续步骤会用到。具体方法为：点击左边的 `Secrets` 菜单项，右侧点击 `Show` -> `Copy` 即可）

![Integration configuration](https://github.com/FarseaSH/hugo-theme-moments/assets/86035589/6d7c0efb-c7ec-4237-b6e7-db9f9d8a5bd5)

**3. 将模版与该Integration绑定**

- 在 Notion 里进入刚才拷贝的 Notion2Moments模版
- 点击又上角三个点`...`，弹出菜单
- 进入菜单最下方 `Connect to`，点击刚才创建的Integration名称，弹出提醒款，选择`Confirm`即可

![Integration connection](https://github.com/FarseaSH/hugo-theme-moments/assets/86035589/d06501c7-0b36-467d-a115-19311edc1f2a)



## Github 的准备

Github 侧的配置

**1. fork这个repo: 在页面上方点击 `Fork` 即可**

**2. 设置环境变量**
- 进入 fork 后的 repo，点击上方 `Setting`
- 左侧 `Security` 小标题下方 `Securities and variables` 点击展开后选中 `Action`

![image](https://github.com/FarseaSH/hugo-theme-moments/assets/86035589/c829e8e5-582e-4826-9c9f-91a4c20ee837)

- 添加 Notion Integration Secret `NOTION_SECRET`: 点击右侧绿色的 `New repository secret` 按钮，`Name` 输入框下填写 `NOTION_SECRET`，`Secret` 下方输入框填写之前创建的 Notion Integration 里的 Secret 
    - Screte 形如 `secret_Sjrb9wHo2MS6EB3gjpMbRb6g7h35qIx8uVnve7izuIdV`

- 添加 Notion页面ID `NOTION_DATABASE_ID`: 再次点击右侧绿色的 `New repository secret` 按钮，`Name` 输入框下填写 `NOTION_DATABASE_ID`，`Secret` 下方输入框填写之前拷贝模版所对应的 Notion ID。获取方式如下
    - 在你的 Notion 中，进入该模版 database 所在的页面，复制该页面链接
    - 粘贴该链接，链接为这样的格式 `https://www.notion.so/8l6c69b89f9b46c5ceb38f1e96915ed0?v=05d976ec4640453e90f7a13796e3b8e2`，其中 `notion.so`斜杠`\`后至问号`?`部分为所需的 Notion ID，即这个例子中的 `8l6c69b89f9b46c5ceb38f1e96915ed0` 

![copy notion database link](https://github.com/FarseaSH/hugo-theme-moments/assets/86035589/0221e302-e54a-4b70-a996-a560eff971f4)


**3. 设置 Github Page 部署源为 Github Action**

- 依然在这个repo的设置页面中，左侧 `Code and automation` 小标题下方，点击 `Pages`
- 点击右侧 `Source` 下面的菜单展开，选择 `Github Actions`

![Set Github Page source to Github Action](https://github.com/user-attachments/assets/8cbd795d-b885-4e54-a944-b1ea366868d3)

**4. 修改 Github Action 配置，开始进行自动更新：**

- 在 Github 页面上即可操作，进入`.github/workflows`文件夹，点击查看`update_moments.yml` 文件，单击铅笔图标进行文件编辑。
- 将`#-schedule:` 和下方 `#- cron:  '0 * */1 * *'` 前面的井号#删除，取消注释，并保持缩进对齐。
- 修改完成后，点击右上角 `Commit changes...` 保存修改即可


**恭喜完成了！**


