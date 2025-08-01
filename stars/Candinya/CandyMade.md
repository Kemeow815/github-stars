---
project: CandyMade
stars: 5
description: |-
    简单，清晰，干净的项目展示页
url: https://github.com/Candinya/CandyMade
---

<div align="center">

<img src="./public/assets/logos/candymade.svg" width="120" height="120" alt="CandyMade Logo"/>

</div>

# CandyMade

简单，清晰，干净的项目展示页

## 开始使用

### 定义主页

主页最顶上的大图和介绍在 `src/components/Hero.tsx` ，您可以自行修改这个组件来替换掉它。

### 定义项目

主要的项目定义在 `src/projects` 目录下的对应目录中，这里我们提供了一个模板项目 `template` 供您可以直接复制修改，您也可以参考其他现有的项目填写相关的信息。

为了方便共用资源文件（如项目 LOGO 和屏幕截图）在其他地方使用，我们推荐您将这些资源文件放在 `public/assets` 目录中。当然，您完全可以根据您的喜好组织对应的资源结构。

为避免造成困惑或带来不必要的麻烦，在定义项目 id 时请尽量不要使用 小写字母、数字、减号和下划线 以外的字符。

### 展示项目

当项目定义完成后，请在 `src/projects/index.ts` 文件中按照上面的定义将项目的简单介绍和详细信息分别添加到 `AllProjectsBasic` 和 `AllProjectsDetails` 中。
项目会自动读取这两个变量，并为您生成对应的结构。

- 如果您不希望某个项目被展示在主页，但又希望能为它提供独立页面的话，您可以不在 `AllProjectsBasic` 中放置它。
- 对应的，如果您只希望某个项目在主页呈现，而不希望它拥有自己的详情页的话，可以不在 `AllProjectsDetails` 中放置它。

### 获取 JSON 数据

为方便其他场合的使用，项目支持生成一个 /data.json 文件，里面会包含您所有已经配置的项目信息。如果您不需要这个功能，可以自行删除 `src/app/data.json` 目录及其中的内容。

## 二次开发

### 技术栈

- [Next.js](https://nextjs.org/)
- [React](https://react.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [TailwindCSS](https://tailwindcss.com/)

### 项目结构

```
├───public           -> 资源（构建时直接被原样复制到结果中）
└───src
    ├───app          -> 项目页面路由
    ├───components   -> 主要组件
    ├───icons        -> 使用到的图标
    ├───projects     -> 展示项目配置
    ├───translations -> 文本映射（翻译）
    ├───types        -> 类型定义
    └───utils        -> 实用工具
```

## 开源许可

- 项目的代码部分基本基于 Apache 2.0 许可，这意味着您可以在遵守它的情况下自由 fork 并变更这个项目，并自由使用在任何商业/非商业，或是开源/非开源的场合。
- 项目的资源部分（ public/assets 目录下的内容）为 Nya Candy 版权所有，请不要在任何其他地方使用。

