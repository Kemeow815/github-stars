---
project: valaxy-addon-autosummary
stars: 3
description: |-
    手写文章摘要！？太麻烦了！这是一款适用于Valaxy的插件，可以自动生成文章摘要。Writing article summaries by hand? Too much hassle! This is a plugin for Valaxy that automatically generates article summaries.
url: https://github.com/Okysu/valaxy-addon-autosummary
---

# Valaxy-addon-autosummary

<p align="center">English | <a href="README.zh-CN.md">中文</a></p>

## Overview

![WOW](https://source.yby.zone/upload/images/1705667938_o0VGDYLJwTL.png)

Writing article summaries by hand? Too much hassle! This is a plugin for Valaxy that automatically generates article summaries.

## Usage

First, you need to modify the `excerpt_type` field in the `frontmatter` of the article to use AI summarization. Set the value to `ai`.

```yaml
excerpt_type: ai
```

Place the `autoSummary.ts` file from this repository in any folder you like. If you don't like the name of this plugin, you can rename the file to your liking.

Then, add this plugin to the Valaxy configuration file (`valaxy.config.ts`):

```ts
import { startAISummary } from "./autoSummary";

export default defineValaxyConfig<UserThemeConfig>({
  // ... other configurations

  hooks: {
    "build:before": async () => {
      console.log("start auto summary");
      await startAISummary();
    },
  },
});
```

If you are deploying on platforms like Vercel, you need to set the following environment variables in the platform's settings page:

- `OPENAI_BASE_URL`: The API endpoint for OpenAI, usually `https://api.openai.com/`. If empty, the default URL will be used.
- `OPENAI_API_KEY`: Your OpenAI API Key.

If you are deploying locally, you need to set these two environment variables in your environment.

## Notes

The dependencies used by this plugin are already installed by Valaxy, so you don't need to install them again.

Therefore, you only need to place `autoSummary.ts` in your project and add this plugin to the Valaxy configuration file.

When an article has an `excerpt`, this plugin will not generate a summary for the article.

## Adjusting Model Parameters

You can modify the model parameters in `autoSummary.ts` to achieve the desired results.

```ts
const data = {
  model: "gpt-3.5-turbo",
  messages: prompt, // Do not modify this
  max_tokens: 300,
  temperature: 0.9,
  top_p: 1,
  frequency_penalty: 0,
  presence_penalty: 0.3,
  stop: ["\n"],
};
```

If the output is not satisfactory, it may be due to the `prompt`. You can modify the content of `openaiConfig.prompt` to achieve the desired results.


## I don't have an OpenAI API Key

You can register an account on "[For fun via AI.](https://ai.coolers.fun/register?aff=Af6f)" This is a platform of mine. New users receive credits that are enough to generate many article summaries.
