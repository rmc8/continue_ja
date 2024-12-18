---
title: コンテキスト選択
description: チャットのためのコンテキスト選択方法
keywords: [コンテキスト]
sidebar_position: 3
---

## 入力

入力ボックスに質問や指示を入力することが唯一の必須コンテキストです。以下に記載する追加のコンテキストを選択して含める他の方法はすべてオプションです。

## ハイライトされたコード

<kbd>cmd/ctrl</kbd> + <kbd>L</kbd>（VS Code）または<kbd>cmd/ctrl</kbd> + <kbd>J</kbd>（JetBrains）を押して選択したハイライトされたコードは、あなたが提供する入力と共にプロンプトに含まれます。これは、追加のセクションをハイライトするか、以下の他の選択方法を使用しない限り、モデルに提供される唯一のコードセクションです。

## アクティブなファイル

リクエストを送信する際に<kbd>cmd</kbd> + <kbd>opt</kbd> + <kbd>enter</kbd>（Mac）または<kbd>ctrl</kbd> + <kbd>alt</kbd> + <kbd>enter</kbd>（Windows）を押すことで、現在開いているファイルをコンテキストとして含めることができます。

## 特定のファイル

[`@Files`](../customize/context-providers.md#file)と入力してファイルを選択することで、現在のワークスペース内の特定のファイルをコンテキストとして含めることができます。

## 特定のフォルダ

[`@Folder`](../customize/context-providers.md#folder)と入力してディレクトリを選択することで、現在のワークスペース内のフォルダをコンテキストとして含めることができます。これは[`@Codebase`と同様に機能](../customize/deep-dives/codebase.md)しますが、選択したフォルダ内のファイルのみを含みます。

## コードベース全体

[`@Codebase`](../customize/context-providers.md#codebase)と入力することで、コードベース全体をコンテキストとして含めることができます。@Codebaseの動作方法については[こちら](../customize/deep-dives/codebase.md)で学ぶことができます。

## ドキュメントサイト

[`@Docs`](../customize/context-providers.md#docs)と入力してドキュメントサイトを選択することで、ドキュメントサイトをコンテキストとして含めることができます。@Docsの動作方法については[こちら](../customize/deep-dives/docs.md)で学ぶことができます。

## ターミナルの内容

[`@Terminal`](../customize/context-providers.md#terminal)と入力することで、IDEのターミナルの内容をコンテキストとして含めることができます。

## Gitの差分

[`@Git Diff`](../customize/context-providers.md#git-diff)と入力することで、現在のブランチに加えたすべての変更をコンテキストとして含めることができます。

## その他のコンテキスト

組み込みのコンテキストプロバイダーの完全なリストは[こちら](../customize/context-providers.md)で確認でき、独自のカスタムコンテキストプロバイダーの作成方法は[こちら](../customize/tutorials/build-your-own-context-provider.md)で学ぶことができます。
