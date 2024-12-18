---
title: モデルのセットアップ
description: オートコンプリート - モデルのセットアップ
keywords: [モデル, オートコンプリート]
sidebar_position: 2
---

## 全体的に最高の体験

最高のオートコンプリート体験を得るには、[Mistral API](https://console.mistral.ai/)を通じてCodestralを使用することをお勧めします。このモデルは、コードのコンテキストを優れた理解力で高品質の補完を提供します：

```json title="config.json""
{
  "tabAutocompleteModel": {
    "title": "Codestral",
    "provider": "mistral",
    "model": "codestral-latest",
    "apiKey": "YOUR_API_KEY"
  }
}
```

:::tip[Codestral APIキー]
CodestralとMistral一般のAPIキーは異なります。Codestralを使用する場合は、おそらくCodestral APIキーが必要ですが、チームでキーを共有する場合や`api.mistral.ai`を使用したい場合は、`tabAutocompleteModel`に`"apiBase": "https://api.mistral.ai/v1"`を設定してください。
:::

## ローカル、オフライン / セルフホスト体験

ローカル実行やセルフホストを好む場合、`Qwen2.5-Coder 1.5B`は多くのユーザーにとってパフォーマンスと品質のバランスが良好です：

```json title="config.json""
{
  "tabAutocompleteModel": {
    "title": "Qwen2.5-Coder 1.5B",
    "model": "qwen2.5-coder:1.5b",
    "provider": "ollama"
  }
}
```

より高い計算能力がある場合は、`qwen2.5-coder:7b`を使用してより高品質の提案を得られる可能性があります。

:::note

LM Studioユーザーの場合、「My Models」セクションに移動し、希望のモデルを見つけて、パス（例：`Qwen/Qwen2.5-Coder-1.5B-Instruct-GGUF/wen2.5-coder-1.5b-instruct-q4_k_m.gguf`）をコピーしてください。このパスを設定の`model`値として使用してください。

:::

## その他の体験

オートコンプリートで使用できる他の多くのモデルとプロバイダーがあります。[こちら](../customize/model-types/autocomplete.md)でそれらをチェックしてください。
