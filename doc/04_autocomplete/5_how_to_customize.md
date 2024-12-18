---
title: カスタマイズ方法
description: オートコンプリートのカスタマイズ方法
keywords: [カスタマイズ]
sidebar_position: 5
---

Continueは[`config.json`](../reference.md)内にいくつかのパラメータを提供しており、これらを調整することで、特定のニーズやハードウェア能力に合わせて提案の品質とシステムパフォーマンスの最適なバランスを見つけることができます：

```json title="config.json"
 "tabAutocompleteOptions": {
   "maxPromptTokens": 400,
   "prefixPercentage": 0.5,
   "multilineCompletions": "always"
 }
```

- `maxPromptTokens`: プロンプトの最大トークン数を設定し、コンテキストと速度のバランスを取ります。
- `prefixPercentage`: カーソル前のコードに割り当てるプロンプトの割合を定義します。
- `multilineCompletions`: 提案が複数行にまたがるかどうかを制御します（"always"、"never"、または"auto"）。

すべての設定オプションとその影響に関する包括的なガイドについては、[オートコンプリートの深掘り](../customize/deep-dives/autocomplete.md)をご覧ください。
