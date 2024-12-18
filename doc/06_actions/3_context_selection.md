---
title: コンテキスト選択
description: アクション - コンテキスト選択
keywords: [コンテキスト, スラッシュ, デバッグ, クイックフィックス, 右クリック]
sidebar_position: 3
---

## スラッシュコマンド

スラッシュコマンドは、[コンテキストプロバイダー](chat/context-selection.md)や[ハイライトされたコード](chat/context-selection.md)を含む追加の指示と組み合わせることができます。

例えば、"/edit" スラッシュコマンドを使用する場合、LLMに実行してほしい編集を説明する必要があります。

一部のスラッシュコマンドは入力を認識しません。例えば、"/share" スラッシュコマンドは、他に何を要求しても、現在の会話のマークダウンコピーを作成するだけです。

## クイックアクション

クイックアクションは常にクラスまたは関数の上に表示され、そのクラスまたは関数を編集しますが、それ以外の部分は編集しません。

## 右クリックアクション

選択したハイライトコードは、選択したアクションに応じて事前に書かれた一連の指示とともにプロンプトに含まれます。モデルが編集を試みるのは、このコードセクションのみです。

## デバッグアクション

デバッグアクションは、最後に実行されたターミナルコマンドとその出力を選択し、以下のプロンプトをチャットウィンドウに挿入します。言語モデルに送信される追加の非表示情報はありません。

```
以下のエラーが発生しました。修正方法を説明していただけますか？

[エラーメッセージ]
```

## クイックフィックス

デバッグアクションと同様に、クイックアクションはプロンプトを透過的にチャットウィンドウに挿入します。"Ask Continue" を選択すると、エラーの上下3行がチャットに送信され、その後に "上記のコードで以下の問題をどのように修正しますか？: [エラーメッセージ]" という質問が続きます。
