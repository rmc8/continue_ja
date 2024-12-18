---
title: チャット
description: チャットの使い方
sidebar_label: 使用方法
keywords: [使い方, チャット]
sidebar_position: 1
---

チャット

## 使用方法

チャットを使用すると、IDEを離れることなくLLMに簡単に助けを求めることができます。タスクを送信し、関連情報を含めると、LLMはそのタスクを完了するのにもっとも適したテキストやコードで返答します。望む結果が得られない場合は、フォローアップメッセージを送信して、タスクが完了するまでアプローチを明確にし、調整できます。

チャットは、コードを理解し改善する際や、検索エンジンのクエリの代替として最適です。

## リクエストを入力してEnterを押す

質問を送信すると、回答が返ってきます。問題を解決するよう指示すると、解決策が提供されます。コードを求めると、生成されます。

## コードセクションをハイライトしてコンテキストとして含める

マウスでコードセクションを選択し、<kbd>cmd/ctrl</kbd> + <kbd>L</kbd>（VS Code）または<kbd>cmd/ctrl</kbd> + <kbd>J</kbd>（JetBrains）を押してLLMに送信し、説明を求めたり、何らかの方法でリファクタリングを要求したりできます。

## @記号でコンテキストを参照する

コードベース、ドキュメント、IDE、その他のツールからの情報をコンテキストとして含めたい場合は、@を入力して選択し、コンテキストとして含めることができます。これの使用方法の詳細については、[チャットコンテキスト選択](context-selection.md)で学ぶことができます。

## 生成されたコードをファイルに適用する

LLMがファイルの編集を返信した場合、「適用」ボタンをクリックできます。これにより、エディター内の既存のコードが提案された変更を反映して更新されます。

## 新しいタスクのために新しいセッションを開始する

タスクを完了し、新しいタスクを開始したい場合は、<kbd>cmd/ctrl</kbd> + <kbd>L</kbd>（VS Code）または<kbd>cmd/ctrl</kbd> + <kbd>J</kbd>（JetBrains）を押して新しいセッションを開始し、次のタスクに関連するコンテキストのみがLLMに提供されるようにします。

## 異なるモデル間を切り替える

複数のモデルを設定している場合、ドロップダウンを使用するか、<kbd>cmd/ctrl</kbd> + <kbd>'</kbd>を押してモデル間を切り替えることができます。
