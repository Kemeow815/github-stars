---
project: siri-ultra
stars: 1135
description: |-
    The most intelligent Siri powered by LLMs
url: https://github.com/fatwang2/siri-ultra
---

# Siri Ultra

This is a Siri Ultra that works with Apple Shortcuts removing the need for a dedicated hardware device.

[中文使用手册](Usage_zh.md)

More discussions, please join in our offical [discord](https://discord.com/invite/AKXYq32Bxc) channel.

## How it works

The assistant is run on Cloudflare Workers and can work with any LLMs. 

[Siri Ultra Demo Video](https://x.com/fatwang2ai/status/1789601031313035281)

[Siri Ultra Vision Demo Video](https://x.com/fatwang2ai/status/1791648375693361161)

## Features
- Real-time dialogue 💬
- Real-time voice 🎙️
- Real-time Web Search 🔍
- URL Content Digest 🔗
- Support Reasoning Models like DeepSeek-R1 🔬
- Talk with pictures 🌄(Siri Ultra Vision)
- Talk with videos 📹(Siri Ultra Vision)

# Usage

## Method 1: Setting Up the Shortcut Directly
1. **Install the Shortcut**: 
   - Click [Siri Ultra](https://s.search1api.com/siriultra006) for chat with LLMs to install.

   Beta Version:
   - Click [Siri Ultra Vision](https://s.search1api.com/siriultravision001) for vision of LLMs to install.

2. **Configure**: 
   - Open the Shortcut, follow prompts to input necessary variables.
   - Change the name of the shortcut to your desired name,for example, "Siri Ultra".

3. **Usage**:
   - **Siri Conversation (Common)**: Open Siri, say "Siri Ultra" to start the conversation.
   - **URL Summary (Common)**: Copy a URL, or share a URL to the shortcut, the shortcut will extract the content of the URL and return a summary.
   - **Text Conversation**: Open the shortcut, input the question, click the "finish" button.
   - **Voice Conversation**: Change the number 6 variable in the shortcut to "no", when you input the question, the shortcut will return the answer in voice.


## Method 2: Setting Up the Self-Hosted Version

### Getting Started

1. **Clone the repository**:
   - Clone this repository and navigate to the root directory.

2. **Install dependencies**:
   - Run `npm install` to install the necessary dependencies.

3. **Authenticate with Cloudflare**:
   - Run `npx wrangler login` to log in to your Cloudflare account.

4. **Create KV namespaces**:
   - Run `npx wrangler kv:namespace create chats` to create a KV namespace. Note down the ID.

5. **Configure the project**:
   - Update `wrangler.toml` with the namespace IDs:

   ```toml
      [[kv_namespaces]]
      binding = "siri_ai_chats"
      id = "<id>"
    ```

6. **Set up API keys**:

- Run `npx wrangler secret put API_KEY` to set the LLMs API Key,such as [Groq](https://console.groq.com/login) or [OpenAI](https://openai.com/) or [Search1API](https://www.search1api.com/?utm_source=siri_ultra).
- Run `npx wrangler secret put SEARCH1API_KEY` to set the [Search1API](https://www.search1api.com/?utm_source=siri_ultra) API key.

   > **Note**: You can only set API_KEY if you don't need search function, and if you use Search1API as your LLMs, you don't need to set the SEARCH1API_KEY to use the search function.

7. **Update the LLMs Vars**:
   ```toml
      [vars]
      API_BASE= "https://api.groq.com/openai/v1/"
      MODEL="deepseek-r1-distill-llama-70b"
      SYSTEM_PROMPT="You are Siri Ultra. Answer in 1-2 sentences. Be friendly, helpful and concise. Default to metric units when possible. Keep the conversation short and sweet. You only answer in text. Don't include links or any other extras. Don't respond with computer code, for example don't return user longitude."
    ```

### Deploying the Worker

To deploy the worker, run `npx wrangler deploy`.

### Setting Up the Shortcut

1. **Install the shortcut**:
   - Use [Siri Ultra](https://s.search1api.com/siriultra006) to install the chat shortcut.
   - Use [Siri Ultra Vision](https://s.search1api.com/siriultravision001) to install the vision shortcut.
2. **Configure the shortcut**:
   - Open the shortcut and replace the `URL` field with your worker's URL.
   - If you didn't change the default name, the URL should be `https://siri-ultra.<your-username>.workers.dev`.

