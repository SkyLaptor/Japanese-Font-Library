# xTranslator用ユーザー辞書
[xTranslator](https://www.nexusmods.com/starfield/mods/313)ディレクトリ内のUserDictionariesの中にコピーして使用する。
この辞書は[Improved Japanese Translation](https://tktk1.net/skyrim/mymod/improved-japanese-translation/) v1.3.0 を元に生成されたものである。

## 導入手順
1. xTranslatorをインストールする。
2. xTranslatorインストールフォルダ内に `UserDictionaries` フォルダがあるので、その中にこのユーザー辞書をコピーする。


## 辞書を使用したMOD翻訳手順
Improved Japanese Translationを導入した状態でこの辞書を基準にMODを翻訳しないと、翻訳に不整合が発生する。
翻訳作業は以下の手順で作業する。

1. 翻訳対象ESPを読み込む。
2. 翻訳ファイルを読み込む。「ファイル」→「翻訳ファイルのインポート」
    * 上書き: 全て上書き
    * 翻訳する対象: FormID(ルーズ)と原文が一致
    * フィルターで表示されている部分のみ: □
    * インポートする前にテキストをリセット: □
3. 画面下部の「語彙」を開く。
4. 以下の順で辞書を選択して適用する。辞書を右クリック→「SSTを適用」
   1. skyrim
   2. dawnguard
   3. hearthfires
   4. dragonborn
   5. update
   * 上書き: 全て上書き
   * 翻訳する対象: FormIDが一致
   * フィルターで表示されている部分のみ: □
   * インポートする前にテキストをリセット: □
   * グループID行のみ適用: □