---
title: "Unreal Engine5で専用サーバーモード"
slug: ue5server
date: 2022-06-14T00:42:03+09:00
categories:
    - UE5
tags: [UE5]
---

#　はじめに
とりあえず素人ながらUnrealEngine5を触ってみたいとなりサーバーを立てて見ました。
今回のゴールは、TSPのテンプレートをAWSに立ててオンライン通信をするところまでです。

まず以下のリンクをとても参考にしたので興味のある方は一緒に読んでいただけると良いと思います。
- [AWSのブログ](https://aws.amazon.com/jp/blogs/news/compiling-unreal-engine-4-dedicated-servers-for-aws-graviton-ec2-instances/)
- [UnrealEngineのチュートリアル](https://docs.unrealengine.com/5.0/ja/setting-up-dedicated-servers-in-unreal-engine/)


# 環境
- Windows11 21H2
- UnrealEngine 5.0.2

# Epic LauncherからインストールしたUEだと専用サーバーはたてられない罠
実はEpicLauncherからインストールしたUnreal Enigineからだと専用サーバーをビルドできません。
Epicのgithubからソースをダウンロードしてきてビルドする形になります。

まずは以下からEpicのgithub Organizationに参加しましょう。
[https://www.unrealengine.com/en-US/ue-on-github](Epicのサイト)

それができたら以下のリポジトリが閲覧可能になるはずなので、クローンしてReadmeの手順通りにファイルを実行していけばビルド版のUEが使えます。
[https://github.com/EpicGames/UnrealEngine](UEのソース)

# TPSのテンプレートから準備していく
UEを開いてGames-ThirdPersonから今回のプロジェクトを作成します。C++版を選択する必要があるので注意です。
![](images/ue5server/tpstemplate.png)