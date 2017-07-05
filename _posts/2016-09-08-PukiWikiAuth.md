---
layout: post
title: PukiWikiの認可辺りについて
---

PukiWikiで閲覧許可を与えられていないページを見るということをやってみる  

修正されてたっぽい [BugTrack](http://pukiwiki.osdn.jp/dev/?BugTrack/598)  

[PukiWiki/1.4/ちょっと便利に/任意のページごとの閲覧・編集制限](http://pukiwiki.osdn.jp/dev/?PukiWiki/1.4/%E3%81%A1%E3%82%87%E3%81%A3%E3%81%A8%E4%BE%BF%E5%88%A9%E3%81%AB/%E4%BB%BB%E6%84%8F%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%94%E3%81%A8%E3%81%AE%E9%96%B2%E8%A6%A7%E3%83%BB%E7%B7%A8%E9%9B%86%E5%88%B6%E9%99%90)
このリンクの中に

> 上記の方法でうまくいきましたが、雛形から見ることが出来てしまいます・・・何か良い対処法はありませんでしょうか？ -- どん? 2007-07-23 (月) 17:36:23

との記述があるので既出です。  

検証環境は、VMwareでUbuntu14.04LTSの上にPukiWiki-1.5.1_utf8入れてホスト側から接続です  

まず、PukiWikiを入れる  
参考:[Ubuntu14.04にPukiwiki1.5.0をインストールする by @tuneyukkie on @Qiita](http://qiita.com/tuneyukkie/items/e7565fb0856e6a9f517d)  
![install]({{site.baseurl}}/images/20160908/install.png)  

そして、適当にページを作成する
![add]({{site.baseurl}}/images/20160908/add.png) 
![add2]({{site.baseurl}}/images/20160908/add2.png) 
![add3]({{site.baseurl}}/images/20160908/add3.png) 

作ったhogehogeページにユーザ認証を追加する
参考:[PukiWiki/Authentication](https://pukiwiki.osdn.jp/?PukiWiki/Authentication)  
![auth]({{site.baseurl}}/images/20160908/auth.png) 

ログインしてないので閲覧不可  
![noauth]({{site.baseurl}}/images/20160908/noauth.png) 
ログインしてないので編集不可  
![noauth2]({{site.baseurl}}/images/20160908/noauth2.png) 

hogehogeを閲覧するために、新規からページを新しく作成  
![add4]({{site.baseurl}}/images/20160908/add4.png) 

雛形とするページからhogehogeを選んで読み込む  
![pass]({{site.baseurl}}/images/20160908/pass.png) 
![pass2]({{site.baseurl}}/images/20160908/pass2.png) 
![pass3]({{site.baseurl}}/images/20160908/pass3.png) 
![pass4]({{site.baseurl}}/images/20160908/pass4.png) 

見れました  


[BugTrack/598](http://pukiwiki.osdn.jp/dev/?BugTrack/598)  ここにこれについての記述がありますね  
デフォルトで対応していない?のはなんだろ...  
