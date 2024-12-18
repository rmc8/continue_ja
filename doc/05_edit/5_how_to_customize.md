---
title: カスタマイズ方法
sidebar_position: 5
description: 編集機能のカスタマイズ方法
keywords: [編集, cmd i, 動作]
---

`inlineEdit`プロパティを使用して、編集機能に特定のモデルを設定することができます。

```json title="config.json"
"experimental": {
    "modelRoles": {
        "inlineEdit": "MODEL_TITLE",
    }
}
```

このようにconfig.jsonを設定することで、編集機能に使用するモデルを指定できます。"MODEL_TITLE"の部分には、使用したいモデルの名前（タイトル）を入力します。これにより、編集タスクに最適なモデルを選択し、パフォーマンスや結果の質を調整することができます。
