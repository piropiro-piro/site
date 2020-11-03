# URL
- https://webbbbbbb.com

# 初回のみ作業
1. siteのgithubリポジトリをローカルにクローン
```
https://github.com/piropiro-piro/site.git
```
2. _config.ymlにユーザを追加
   - 画像を付けたい場合はassets/imagesフォルダに配置したのちそのパスを指定してください
```yaml:_config.yml
authors:
  piropiro:
    name: piropiro
    bio: 家系ラーメンが食べたい
    external-image: false
    picture: assets/images/profile.jpg
    twitter: 
```

3. masterブランチにプッシュすればサイトが更新されます

# Blogの更新
## ファイルの作成
- _postフォルダ直下に下記の命名規則でファイルを配置
   - yyyy-mm-dd-*ここに簡単なタイトル*.markdown
## メタ情報の記載
- そのファイルの頭に以下のようなメタ情報を仕込んでください
```markdown:yyyy-mm-dd-*ここに簡単なタイトル*.markdown
---
title: "競馬予測AIの仕組み解説"
layout: post
date: 2016-01-23 22:10
tag: 
- 競馬
- 機械学習
description: "記事作成中"
category: blog
author: piropiro
externalLink: false
---
以下本文
```
- title...ブログのタイトルを入れてください
- layout...postと入力
- date...ブログの更新日時を入れてください
- tag...付けたいタグを複数入れられます
- description...リンク貼ったときとかに出る文章です。ブログの概要を入れてください。
- category...blogと入力
- author...初回作業で作ったユーザ名を入れていください
- externalLink:...falseと入力
## 本文の書き方
- markdownでテキトーに（HTMLを入れても動くはず）
- 画像はassets/images/に入れてください

# Projectの更新
- 基本はBlogと同じ、メタ情報だけ少し変える
## メタ情報の記載
- そのファイルの頭に以下のようなメタ情報を仕込んでください
```markdown:yyyy-mm-dd-*ここに簡単なタイトル*.markdown
---
title: "競馬予測AI"
layout: post
date: 2016-01-23 22:10
tag: 
- 競馬
- 機械学習
projects: true
hidden: true
description: "記事作成中"
category: project
author: piropiro
externalLink: false
---
以下本文
```
- projects...trueと入力
- hidden...trueと入力
- category...projectと入力