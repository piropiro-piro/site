---
title: "【Flutter】UIWebViewの廃止に対応したTwitter認証アプリのiOSリリース"
layout: post
date: 2021-02-28 23:00
tag: 
- Flutter
- Twitter
- iOS
description: 
"こんにちは、やっくるです。
先日、Flutter フレームワークを使用し、Firebase で Twitter の認証機能を実装し実機で試そうとしました。"
category: blog
author: yakkuru
externalLink: false
---

## 問題

ところが、App Store Connect へのアップロード時に、以下のエラーを受け取り、ビルドが受け付けられませんでした。

> ITMS-90809: Deprecated API Usage - New apps that use UIWebView are no longer accepted. Instead, use WKWebView for improved security and reliability. Learn more (https://developer.apple.com/documentation/uikit/uiwebview).

上記の文章は「UIWebView を使用した新規アプリのビルド・リリースは許可されておらず、代わりに WKWebView を使用してくれ。」という内容です。

## 原因

本アプリの中に、UIWebView を使用した部分は無いはずなのに…、と調査したところ、導入していた以下のパッケージで UIWebView を使用していたことが判明しました。

```
<pubspec.yaml>

dependencies:
  flutter_twitter_login: ^1.1.0
```

[flutter_twitter_login](https://github.com/roughike/flutter_twitter_login)

上記パッケージは、TwitterKit SDK を使用しており、その中で UIWebView が使用されていたようです。
既に TwitterKit SDK はサポートが終了しており、WKWebView への移行がされておらず、また、本パッケージも 2018/3/24 時点で更新がされておらず、現状ではリリースに対応していない状態です。

## 対応方法

調べたところ、有志の方がこちらのリポジトリをフォークして、UIWebView 問題を回避した新しいリポジトリを用意していただいていました。

[flutter_twitter_loginに挙げられたissueに対するコメント](https://github.com/roughike/flutter_twitter_login/issues/32#issuecomment-624033596)

こちらでは、TwitterKit SDK ではなく、TwitterKit5 と呼ばれる、カスタマイズされた SDK を使用しているとのことです。こちらを利用することで、問題なくビルド・リリースすることが可能になりました。

```
<pubspec.yaml>
dependencies:
  flutter_twitter_login:
    git: 
      url: https://github.com/Kiruel/flutter_twitter_login
```

参考になれば幸いです。