---
title: "iOSの課金テスト用アカウントまとめ"
date: 2021-03-12 18:12
tag: 
- モバイルアプリ
- flutter
projects: false
description: ""
category: blog
author: evange_
externalLink: false
---

iOSアプリの課金をテストする時のアカウントの種類をいつも忘れるので備忘録を兼ねてまとめておきます。

SANDOBOXユーザーを作成する手順はこの記事にお世話になりました。  
[App内課金をSANDBOXユーザーでテストする - AppStoreConnect編(2019年版)]
(https://qiita.com/shuntarou/items/a9ae2649ff642cd17ca9)

(flutterでの) 課金まわり実装にはこの記事にお世話になりました。  
[【Flutter】もう怖くない！アプリ内課金・定期購入機能を実装する方法を丁寧に説明してみた。](https://qiita.com/YuKiO-OO/items/a0fe8e0a256afbb69fc7

## sandboxTestのT/Fで何が変わるの？

前提として、課金のテストは実機でないと行えません。  
逆に、実機であればデバッグ実行でも、releaseビルドでTestFlightにデプロイしてからでもテストできます。

### アプリのコード上でsandboxTestがTrueの状態

課金処理を呼び出した際、現在端末でログインしているApple IDではなく、SANDOBOXユーザーが使用されます。      
SANDOBOXユーザーでまだログインしていない場合、ログインのダイアログが表示されます。  
この状態ではSANBOX環境用のレシートが返却されます。
サブスクリプションの期間をチェックするための時間が実際の時間とは異なります。  
  
    

### アプリのコード上でsandboxTestがFalseの状態

現在、端末でログインしているApple IDが使用されます。  
レシートも本番環境用のレシートが返却されるようになります。  
