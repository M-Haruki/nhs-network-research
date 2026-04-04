# 対策AndroidでのDoHを用いた対策

[フィルタリングの仕組みと対策](./bypass.md)を読んで仕組みをある程度理解したうえで行うこと。

## 1. [RethinkDNS](https://rethinkdns.com/)のインストール

- [GooglePlay](https://play.google.com/store/apps/details?id=com.celzero.bravedns)
- [F-Droid](https://f-droid.org/packages/com.celzero.bravedns/)

GooglePlay版は機能制限があるため、F-Droidを使える場合はF-Droid版をインストールすることを推奨する。

## 2. DNS over HTTPSの設定

RethinkDNSを起動し、`DNS`をタップして設定を開く。

`その他のDNS`より`DoH`を選択し、右下の`+`をタップしてDNSサーバーを追加する。

わかりやすいリゾルバ名をつけ、リゾルバURLを次のうちから選んで入力する。

|名称|リゾルバURL|
|-|-|
|OpenNIC(ns1.mo.us.dns.opennic.glue)|<https://renardbleu.dev/dns-query>|
|OpenNIC(ns2.au.dns.opennic.glue)|<https://dns1.slowb.ro/dns-query>|
|OpenNIC(ns5.au.dns.opennic.glue)|<https://dns2.slowb.ro/dns-query>|

追加したDNSサーバーを選択して有効にする。

## 3. DNS over HTTPSの有効化

RethinkDNSのトップ画面に戻り、下部の`開始`をタップしてRethinkDNSを有効にする。

DoHを使うとわずかに通信が遅くなったり、不安定になることがあるため、フィルタリング回避が不要な時はRethinkDNSを無効にしておくことを推奨する。
