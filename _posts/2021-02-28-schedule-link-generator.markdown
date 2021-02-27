---
title: "Google Calendarの共有リンクを作成する"
layout: post
date: 2021-02-28 03:00
tag: 
- google cloud platform
description: "イベントの参加者に予定を連絡する際に、Google Calendarの予定を共有リンクとして貼り付けられたらいいなと思い、Google Calendarの共有リンクを作成するツールを作成しました。"
category: blog
author: piropiro
externalLink: false
---

イベントの参加者に予定を連絡する際に、Google Calendarの予定を共有リンクとして貼り付けられたらいいなと思い、Google Calendarの共有リンクを作成するツールを作成しました。

相手が予定を登録する手間を減らしたり、予定をブッチされないようにするなどで使えると思います。
[予定リンク ジェネレータ]({{ "/ScheduleLinkGenerator/" | relatvie_url }})

![ツールイメージ]({{ "/assets/images/posts/2021-02-28-schedule-link-generator/1.png" | relatvie_url }}){:width="360px"}

## 仕組み
そもそもGoogle Calenderにはリンクでの予定共有機能がないため、自分の予定を生成するためのURLを発行することで実現しています。
