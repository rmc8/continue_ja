---
title: カスタマイズ方法
description: アクションのカスタマイズ方法
keywords: [カスタマイズ, アクション]
sidebar_position: 5
---

## ビルトインのスラッシュコマンド

Continueには多数のビルトインスラッシュコマンドがありますが、初めてインストールした時は "/edit"、"/comment"、"/share" など最もよく使用されるものだけが表示されます。より多くのアクションを追加するには、[config.json](../reference.md)を開き、`slashCommands`配列に追加することができます。

## カスタムスラッシュコマンド

カスタムスラッシュコマンドを追加する方法は2つあります：

1. `.prompt`ファイルを使用する - ほとんどの場合、これが推奨されます。完全なリファレンスは[こちら](../customize/deep-dives/prompt-files.md)をご覧ください。
2. `config.ts`を使用する - JavaScript/TypeScript関数を書くことで、LLM、IDE、その他の重要なエンティティへの完全なプログラムアクセスが可能になります。

### `config.ts`を使用したカスタムスラッシュコマンド

自然言語でカスタムコマンドを書く以上のことをしたい場合は、レスポンスを返すカスタム関数を書くことができます。これには`config.json`の代わりに`config.ts`を使用する必要があります。

これを行うには、新しい`SlashCommand`オブジェクトを`slashCommands`リストにプッシュします。このオブジェクトには、スラッシュコマンドを呼び出すために入力する「name」、ドロップダウンメニューに表示される「description」、そして「run」が含まれます。`run`関数は、UIにストリーミングしたい文字列を生成する非同期ジェネレータです。関数の引数として、IDE内の特定の情報/アクションへのアクセス、現在の言語モデル、その他いくつかのユーティリティへのアクセスを提供する`ContinueSDK`オブジェクトにアクセスできます。例えば、以下はコミットメッセージを生成するスラッシュコマンドです：

```typescript title="config.ts"
export function modifyConfig(config: Config): Config {
  config.slashCommands?.push({
    name: "commit",
    description: "コミットメッセージを書く",
    run: async function* (sdk) {
      // getDiff関数は、ステージングされていない変更をdiffに含めるかどうかを
      // 示すブール値のパラメータを取ります。
      const diff = await sdk.ide.getDiff(false); // falseを渡してステージングされていない変更を除外
      for await (const message of sdk.llm.streamComplete(
        `${diff}\n\n上記の変更に対するコミットメッセージを書いてください。20トークン以内で、命令形の簡潔な説明を行ってください（例：'機能を追加' ではなく '機能を追加する'）:`,
        new AbortController().signal,
        {
          maxTokens: 20,
        },
      )) {
        yield message;
      }
    },
  });
  return config;
}
```

## その他のカスタムアクション

現在、他のアクショントリガーは設定のために開放されていませんが、将来的に.promptファイルを通じてこれを許可する予定です。
