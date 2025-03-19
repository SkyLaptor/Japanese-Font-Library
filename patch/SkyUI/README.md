# SkyUI向けパッチ
## 何をするもの？
### MCMのフォントマップ変更
コンフィグメニュー(MCM)はデフォルトで `$EverywhereFont` 系の汎用フォントを使用するが、日本語のような全角フォントだとUIをぶち抜いてしまう。かと言って `$EverywhereFont` 系にコンデンスドなフォント(幅を狭くしたもの)を指定すると他のUIが見づらくなる。その解決策として、MCMには専用のフォントマップを使用するようにする。
MCMを実現しているUIは LE/SE共に`Interface/skyui/configpanel.swf` 。[FFDec](https://github.com/jindrapetrik/jpexs-decompiler)を使用してちまちま書き換える。
