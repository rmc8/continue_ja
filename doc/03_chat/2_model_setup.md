---
title: モデルのセットアップ
description: チャットモデルのセットアップ方法
keywords: [モデル]
sidebar_position: 2
---

import Tabs from "@theme/Tabs";
import TabItem from "@theme/TabItem";

:::info
このページではチャット用のモデルとプロバイダーを推奨しています。`config.json`のセットアップ方法の詳細については[こちら](../reference.md)をご覧ください。
:::

## 全体的に最高の体験

チャットで最高の体験を得るには、400B以上のパラメータを持つモデルまたは最先端のモデルを使用することをお勧めします。

### AnthropicのClaude Sonnet 3.5

現在最も推奨されるのは、[Anthropic](../customize/model-providers/top-level/anthropic.md)のClaude Sonnet 3.5です。

```json title="config.json"
 "models": [
   {
     "title": "Claude 3.5 Sonnet",
     "provider": "anthropic",
     "model": "claude-3-5-sonnet-latest",
     "apiKey": "[ANTHROPIC_API_KEY]"
   }
 ]
```

### MetaのLlama 3.1 405B

オープンウェイトモデルを使用したい場合は、現時点でMetaのLlama 3.1 405Bが最適な選択肢です。SaaSモデルプロバイダー（例：[Together](../customize/model-providers/more/together.md)や[Groq](../customize/model-providers/more/groq.md)）を通じて使用するか、自己ホスティング（例：[vLLM](../customize/model-providers//more/vllm.md)や[Ollama](../customize/model-providers/top-level/ollama.md)を使用）するかを決める必要があります。

<Tabs groupId="providers">
    <TabItem value="Together">
        ```json title="config.json"
            "models": [
                {
                    "title": "Llama 3.1 405B",
                    "provider": "together",
                    "model": "llama3.1-405b",
                    "apiKey": "[TOGETHER_API_KEY]"
                }
            ]
        ```
    </TabItem>
    <TabItem value="Groq">
        ```json title="config.json"
            "models": [
                {
                    "title": "Llama 3.1 405B",
                    "provider": "groq",
                    "model": "llama3.1-405b",
                    "apiKey": "[GROQ_API_KEY]"
                }
            ]
        ```
    </TabItem>
    <TabItem value="vLLM">
        ```json title="config.json"
            "models": [
                {
                    "title": "Llama 3.1 405B",
                    "provider": "vllm",
                    "model": "llama3.1-405b"
                }
            ]
        ```
    </TabItem>
    <TabItem value="Ollama">
        ```json title="config.json"
            "models": [
                {
                    "title": "Llama 3.1 405B",
                    "provider": "ollama",
                    "model": "llama3.1-405b"
                }
            ]
        ```
    </TabItem>
    <TabItem value="Nebius">
        ```json title="config.json"
            "models": [
                {
                    "title": "Llama 3.1 405B",
                    "provider": "nebius",
                    "model": "llama3.1-405b",
                    "apiKey": "[NEBIUS_API_KEY]"
                }
            ]
        ```
    </TabItem>
</Tabs>

### OpenAIのGPT-4o

[OpenAI](../customize/model-providers/top-level/openai.md)のモデルを使用したい場合は、GPT-4oをお勧めします。

```json title="config.json"
 "models": [
   {
     "title": "GPT-4o",
     "provider": "openai",
     "model": "",
     "apiKey": "[OPENAI_API_KEY]"
   }
 ]
```

### GoogleのGemini 1.5 Pro

[Google](../customize/model-providers/top-level/gemini.md)のモデルを使用したい場合は、Gemini 1.5 Proをお勧めします。

```json title="config.json"
  "models": [
    {
      "title": "Gemini 1.5 Pro",
      "provider": "gemini",
      "model": "gemini-1.5-pro-latest",
      "apiKey": "[GEMINI_API_KEY]"
    }
  ]
```

## ローカル、オフラインでの体験

最高のローカル、オフラインでのチャット体験を得るには、お使いのマシンで十分に大きくかつ高速なモデルを使用する必要があります。

### Llama 3.1 8B

ローカルマシンで8Bパラメータのモデルを実行できる場合は、Llama 3.1 8Bをマシン上で実行することをお勧めします（例：[Ollama](../customize/model-providers/top-level/ollama.md)や[LM Studio](../customize/model-providers/more/lmstudio.md)を使用）。

<Tabs groupId="providers">
    <TabItem value="Ollama">
        ```json title="config.json"
            "models": [
                {
                    "title": "Llama 3.1 8B",
                    "provider": "ollama",
                    "model": "llama3.1-8b"
                }
            ]
        ```
    </TabItem>
    <TabItem value="LM Studio">
        ```json title="config.json"
            "models": [
                {
                    "title": "Llama 3.1 8B",
                    "provider": "lmstudio",
                    "model": "llama3.1-8b"
                }
            ]
        ```
    </TabItem>
</Tabs>

### DeepSeek Coder 2 16B

ローカルマシンで16Bパラメータのモデルを実行できる場合は、DeepSeek Coder 2 16Bを実行することをお勧めします（例：[Ollama](../customize/model-providers/top-level/ollama.md)や[LM Studio](../customize/model-providers/more/lmstudio.md)を使用）。

<Tabs groupId="providers">
    <TabItem value="Ollama">
        ```json title="config.json"
            "models": [
                {
                    "title": "DeepSeek Coder 2 16B",
                    "provider": "ollama",
                    "model": "deepseek-coder-v2:16b"
                }
            ]
        ```

    </TabItem>
    <TabItem value="LM Studio">

        ```json title="config.json"
            "models": [
                {
                    "title": "DeepSeek Coder 2 16B",
                    "provider": "lmstudio",
                    "model": "deepseek-coder-v2:16b"
                }
            ]
        ```
    </TabItem>

</Tabs>

## その他の体験

上記以外にも、チャットで使用できる多くのモデルとプロバイダーがあります。詳細は[こちら](../customize/model-types/chat.md)をご覧ください。
