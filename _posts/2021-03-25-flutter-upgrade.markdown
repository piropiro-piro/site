---
title: "Visual Studio CodeでFlutterバージョンを切り替える方法"
layout: post
date: 2021-03-25 21:00
tag: 
- flutter
- Visual Studio Code
description: "Visual Studio CodeでFlutterバージョンを切り替える方法"
category: blog
author: piropiro
externalLink: false
---

こんにちは。ピロピロです。

皆さんflutterを書くときのエディタは何を使っていますか？
私は使い慣れているVSCodeを使っています。
git連携やデバッグなど使い勝手は非常にいいのですが、1点「flutter upgradeを誤ってしてしまいがち」というところだけが困りポイントでした。（flutter バージョンを固定しておけばいいじゃんという話ではありますが…）

今回は、VSCodeでflutter のバージョンを簡単に切り替える方法を知ったので共有します。

## 方法
flutter本体が参照する、gitリポジトリをバージョン指定してチェックアウトするだけです。簡単ですね。

1. flutter本体に含まれるコードを開く
![開き方]({{ "/assets/images/posts/2021-03-25-flutter-upgrade/1.png" | relatvie_url }}){:width="720px"}
2. サイドバーのgitメニューから、flutterのバージョンを指定してチェックアウト
![バージョン選択]({{ "/assets/images/posts/2021-03-25-flutter-upgrade/2.png" | relatvie_url }}){:width="720px"}
3. flutter doctorを実行（このタイミングで自動でflutter pub getも動くはずです）