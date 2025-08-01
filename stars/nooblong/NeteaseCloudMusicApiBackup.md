---
project: NeteaseCloudMusicApiBackup
stars: 269
description: |-
    null
url: https://github.com/nooblong/NeteaseCloudMusicApiBackup
---

# 网易云音乐 API

网易云音乐 Node.js API service

<p>
<a href="https://www.npmjs.com/package/NeteaseCloudMusicApi"><img src="https://img.shields.io/npm/v/NeteaseCloudMusicApi.svg" alt="Version"></a>
<a href="https://www.npmjs.com/package/NeteaseCloudMusicApi"><img src="https://img.shields.io/npm/l/NeteaseCloudMusicApi.svg" alt="License"></a>
<a href="https://www.npmjs.com/package/NeteaseCloudMusicApi"><img src="https://img.shields.io/david/dev/binaryify/NeteaseCloudMusicApi.svg" alt="devDependencies" ></a>
<a href="https://www.npmjs.com/package/NeteaseCloudMusicApi"><img src="https://img.shields.io/david/binaryify/NeteaseCloudMusicApi.svg" alt="devDependencies" ></a>
<a href="https://codeclimate.com/github/Binaryify/NeteaseCloudMusicApi"><img src="https://codeclimate.com/github/Binaryify/NeteaseCloudMusicApi/badges/gpa.svg" /></a>
</p>

## 灵感来自

[disoul/electron-cloud-music](https://github.com/disoul/electron-cloud-music)

[darknessomi/musicbox](https://github.com/darknessomi/musicbox)

[sqaiyan/netmusic-node](https://github.com/sqaiyan/netmusic-node)

[greats3an/pyncm](https://github.com/greats3an/pyncm)

## 环境要求

需要 NodeJS 14+ 环境

## 安装

```shell
$ git clone git@gitlab.com:Binaryify/NeteaseCloudMusicApi.git
$ cd NeteaseCloudMusicApi
$ npm install
```

或者

```shell
$ git clone https://gitlab.com/Binaryify/NeteaseCloudMusicApi.git
$ cd NeteaseCloudMusicApi
$ npm install
```

## 运行

调用前务必阅读文档的`调用前须知`

```shell
$ node app.js
```

服务器启动默认端口为 3000,若不想使用 3000 端口,可使用以下命令: Mac/Linux

```shell
$ PORT=4000 node app.js
```

windows 下使用 git-bash 或者 cmder 等终端执行以下命令:

```shell
$ set PORT=4000 && node app.js
```

## npx 方式运行

可在终端直接执行

```bash
npx NeteaseCloudMusicApi@latest
```

使用此命令，可直接启动服务，无需下载或者 clone 项目

## Vercel 部署

v4.0.8 加入了 Vercel 配置文件,可以直接在 Vercel 下部署了,不需要自己的服务器

### 操作方法

1. fork 此项目
2. 在 Vercel 官网点击 `New Project`
3. 点击 `Import Git Repository` 并选择你 fork 的此项目并点击`import`
4. 点击 `PERSONAL ACCOUNT` 的 `select`
5. 直接点`Continue`
6. `PROJECT NAME`自己填,`FRAMEWORK PRESET` 选 `Other` 然后直接点 `Deploy` 接着等部署完成即可

## 腾讯云 serverless 部署

因 `Vercel` 在国内访问太慢,在此提供腾讯云 serverless 部署方法(注意:腾讯云 serverless 并不是免费的,前三个月有免费额度,之后收费)

### 操作方法

1. fork 此项目
2. 在腾讯云 serverless 应用管理页面( https://console.cloud.tencent.com/sls ),点击`新建应用`
3. 顶部`创建方式`选择 `Web 应用`
4. 选择 `Express框架`,点击底部`下一步按钮`
5. 输入`应用名`,上传方式选择`代码仓库`,进行 GitHub 授权(如已授权可跳过这一步),代码仓库选择刚刚 fork 的项目
6. 启动文件填入:

```
#!/bin/bash
export PORT=9000
/var/lang/node16/bin/node app.js
```

7. 点击`完成`,等待部署完成,点击`资源列表`的 `API网关` 里的 `URL`,正常情况会打开文档地址,点击文档`例子`可查看接口调用效果

## 可以在 Node.js 调用

v3.31.0 后支持 Node.js 调用,导入的方法为`module`内的文件名,返回内容包含`status`和`body`,`status`为状态码,`body`为请求返回内容,参考`module_example` 文件夹下的 `test.js`

```js
const { login_cellphone, user_cloud } = require('NeteaseCloudMusicApi')
async function main() {
  try {
    const result = await login_cellphone({
      phone: '手机号',
      password: '密码',
    })
    console.log(result)
    const result2 = await user_cloud({
      cookie: result.body.cookie, // 凭证
    })
    console.log(result2.body)
  } catch (error) {
    console.log(error)
  }
}
main()
```

## 支持 TypeScript

```ts
// test.ts
import { banner } from 'NeteaseCloudMusicApi'
banner({ type: 0 }).then((res) => {
  console.log(res)
})
```

## 使用文档

[文档地址](https://docs-neteasecloudmusicapi.vercel.app)

## 功能特性

1. 登录
2. 刷新登录
3. 发送验证码
4. 校验验证码
5. 注册(修改密码)
6. 获取用户信息 , 歌单，收藏，mv, dj 数量
7. 获取用户歌单
8. 获取用户电台
9. 获取用户关注列表
10. 获取用户粉丝列表
11. 获取用户动态
12. 获取用户播放记录
13. 获取精品歌单
14. 获取歌单详情
15. 搜索
16. 搜索建议
17. 获取歌词
18. 歌曲评论
19. 收藏单曲到歌单
20. 专辑评论
21. 歌单评论
22. mv 评论
23. 电台节目评论
24. banner
25. 获取歌曲详情
26. 获取专辑内容
27. 获取歌手单曲
28. 获取歌手 mv
29. 获取歌手专辑
30. 获取歌手描述
31. 获取相似歌手
32. 获取相似歌单
33. 相似 mv
34. 获取相似音乐
35. 获取最近 5 个听了这首歌的用户
36. 获取每日推荐歌单
37. 获取每日推荐歌曲
38. 私人 FM
39. 签到
40. 喜欢音乐
41. 垃圾桶
42. 歌单 ( 网友精选碟 )
43. 新碟上架
44. 热门歌手
45. 最新 mv
46. 推荐 mv
47. 推荐歌单
48. 推荐新音乐
49. 推荐电台
50. 推荐节目
51. 独家放送
52. mv 排行
53. 获取 mv 数据
54. 播放 mv/视频
55. 排行榜
56. 歌手榜
57. 云盘
58. 电台 - 推荐
59. 电台 - 分类
60. 电台 - 分类推荐
61. 电台 - 订阅
62. 电台 - 详情
63. 电台 - 节目
64. 给评论点赞
65. 获取动态列表
66. 热搜列表(简略)
67. 发送私信
68. 发送私信歌单
69. 新建歌单
70. 收藏/取消收藏歌单
71. 歌单分类
72. 收藏的歌手列表
73. 订阅的电台列表
74. 相关歌单
75. 付费精选接口
76. 音乐是否可用检查接口
77. 登录状态
78. 获取视频播放地址
79. 发送/删除评论
80. 热门评论
81. 视频评论
82. 退出登录
83. 所有榜单
84. 所有榜单内容摘要
85. 收藏视频
86. 收藏 MV
87. 视频详情
88. 相关视频
89. 关注用户
90. 新歌速递
91. 喜欢音乐列表(无序)
92. 收藏的 MV 列表
93. 获取最新专辑
94. 听歌打卡
95. 获取视频标签/分类下的视频
96. 已收藏专辑列表
97. 获取动态评论
98. 歌单收藏者列表
99. 云盘歌曲删除
100. 热门话题
101. 电台 - 推荐类型
102. 电台 - 非热门类型
103. 电台 - 今日优选
104. 心动模式/智能播放
105. 转发动态
106. 删除动态
107. 分享歌曲、歌单、mv、电台、电台节目到动态
108. 通知-私信
109. 通知-评论
110. 通知-@我
111. 通知-通知
112. 设置
113. 云盘数据详情
114. 私信内容
115. 我的数字专辑
116. batch 批量请求接口
117. 获取视频标签列表
118. 全部 mv
119. 网易出品 mv
120. 收藏/取消收藏专辑
121. 专辑动态信息
122. 热搜列表(详细)
123. 更换绑定手机
124. 检测手机号码是否已注册
125. 初始化昵称
126. 更新歌单描述
127. 更新歌单名
128. 更新歌单标签
129. 默认搜索关键词
130. 删除歌单
131. 电台 banner
132. 用户电台
133. 热门电台
134. 电台 - 节目详情
135. 电台 - 节目榜
136. 电台 - 新晋电台榜/热门电台榜
137. 类别热门电台
138. 云村热评
139. 电台 24 小时节目榜
140. 电台 24 小时主播榜
141. 电台最热主播榜
142. 电台主播新人榜
143. 电台付费精品榜
144. 歌手热门 50 首歌曲
145. 购买数字专辑
146. 获取 mv 点赞转发评论数数据
147. 获取视频点赞转发评论数数据
148. 调整歌单顺序
149. 调整歌曲顺序
150. 独家放送列表
151. 获取推荐视频
152. 获取视频分类列表
153. 获取全部视频列表接口
154. 获取历史日推可用日期列表
155. 获取历史日推详细数据
156. 国家编码列表
157. 首页-发现
158. 首页-发现-圆形图标入口列表
159. 数字专辑-全部新碟
160. 数字专辑-热门新碟
161. 数字专辑&数字单曲-榜单
162. 数字专辑-语种风格馆
163. 数字专辑详情
164. 更新头像
165. 歌单封面上传
166. 楼层评论
167. 歌手全部歌曲
168. 精品歌单标签列表
169. 用户等级信息
170. 电台个性推荐
171. 用户绑定信息
172. 用户绑定手机
173. 新版评论
174. 点赞过的视频
175. 收藏视频到视频歌单
176. 删除视频歌单里的视频
177. 最近播放的视频
178. 音乐日历
179. 电台订阅者列表
180. 云贝签到信息
181. 云贝签到
182. 云贝所有任务
183. 云贝 todo 任务
184. 云贝今日签到信息
185. 云贝完成任务
186. 云贝收入
187. 云贝支出
188. 云贝账户信息
189. 账号信息
190. 最近联系人
191. 私信音乐
192. 抱一抱评论
193. 评论抱一抱列表
194. 收藏的专栏
195. 关注歌手新歌
196. 关注歌手新 MV
197. 歌手详情
198. 云盘上传
199. 二维码登录
200. 话题详情
201. 话题详情热门动态
202. 歌单详情动态
203. 绑定手机
204. 一起听状态
205. 用户历史评论
206. 云盘歌曲信息匹配纠正
207. 云贝推歌
208. 云贝推歌历史记录
209. 已购单曲
210. 获取 mlog 播放地址
211. 将 mlog id 转为视频 id
212. vip 成长值
213. vip 成长值获取记录
214. vip 任务
215. 领取 vip 成长值
216. 歌手粉丝
217. 数字专辑详情
218. 数字专辑销量
219. 音乐人数据概况
220. 音乐人播放趋势
221. 音乐人任务
222. 账号云豆数
223. 领取云豆
224. 获取 VIP 信息
225. 音乐人签到
226. 发送文本动态
227. 获取客户端歌曲下载 url
228. 获取歌单所有歌曲
229. 乐签信息
230. 最近播放-歌曲
231. 最近播放-视频
232. 最近播放-声音
233. 最近播放-歌单
234. 最近播放-专辑
235. 最近播放-播客
236. 签到进度
237. 重复昵称检测
238. 歌手粉丝数量
239. 音乐人任务(新)
240. 内部版本接口
241. 歌单更新播放量
242. 黑胶时光机
243. 音乐百科 - 简要信息
244. 乐谱列表
245. 乐谱内容
246. 曲风列表
247. 曲风偏好
248. 曲风详情
249. 曲风-歌曲
250. 曲风-专辑
251. 曲风-歌单
252. 曲风-歌手
253. 私信和通知接口
254. 回忆坐标
255. 播客搜索
256. 播客声音上传
257. 验证接口-二维码生成
258. 验证接口-二维码检测
259. 听歌识曲
260. 根据 nickname 获取 userid 接口
261. 播客声音列表
262. 专辑简要百科信息
263. 歌曲简要百科信息
264. 歌手简要百科信息
265. mv 简要百科信息
266. 搜索歌手
267. 用户贡献内容
268. 用户贡献条目、积分、云贝数量
269. 年度听歌报告
270. 播客声音搜索
271. 播客声音排序
272. 播客列表详情
273. 本地歌曲文件匹配网易云歌曲信息
274. 歌曲音质详情
275. 歌曲红心数量
276. 私人 FM 模式选择
277. 播客删除
278. 电台排行榜获取
279. 获取声音歌词
280. 获取专辑歌曲的音质
281. 歌手动态信息
282. 最近听歌列表
283. 云盘导入歌曲
284. 获取客户端歌曲下载链接 - 新版
285. 当前账号关注的用户/歌手
286. 会员下载歌曲记录
287. 会员本月下载歌曲记录
288. 已购买单曲
289. 歌曲是否喜爱
290. 用户是否互相关注
291. 歌曲动态封面
292. 用户徽章
293. 用户状态
294. 用户状态 - 支持设置的状态
295. 用户状态 - 相同状态的用户
296. 用户状态 - 编辑
297. 听歌足迹 - 年度听歌足迹
298. 听歌足迹 - 今日收听
299. 听歌足迹 - 总收听时长
300. 听歌足迹 - 本周/本月收听时长
301. 听歌足迹 - 周/月/年收听报告
302. 歌单导入 - 元数据/文字/链接导入
303. 歌单导入 - 任务状态
304. 副歌时间
305. 相关歌单推荐
306. 歌词摘录 - 歌词摘录信息
307. 歌词摘录 - 我的歌词本
308. 歌词摘录 - 添加/修改摘录歌词
309. 歌词摘录 - 删除摘录歌词

## 单元测试

```shell
$ npm test
```

## SDK

|  语言  |                    作者                     |                                                    地址                                                    |  类型  |
| :----: | :-----------------------------------------: | :--------------------------------------------------------------------------------------------------------: | :----: |
|  Java  |    [JackuXL](https://github.com/JackuXL)    | [https://github.com/JackuXL/NeteaseCloudMusicApi-SDK](https://github.com/JackuXL/NeteaseCloudMusicApi-SDK) | 第三方 |
|  Java  | [1015770492](https://github.com/1015770492) |                              https://github.com/1015770492/yumbo-music-utils                               | 第三方 |
| Python |    [盧瞳](https://github.com/2061360308)    |          [NeteaseCloudMusic_PythonSDK](https://github.com/2061360308/NeteaseCloudMusic_PythonSDK)          | 第三方 |

## 贡献者

![](https://opencollective.com/NeteaseCloudMusicApi/contributors.svg?width=890)

## License

[The MIT License (MIT)](https://gitlab.com/Binaryify/NeteaseCloudMusicApi/blob/main/LICENSE)

