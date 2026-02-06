# コントリビューションガイド
開発するに当たっての留意事項、ナレッジなど。

## 開発時に使用するツール
### Vortex
MODマネージャー
https://www.nexusmods.com/about/vortex

### ModOrganizer2
MODマネージャー 
https://www.nexusmods.com/about/vortex

### XMLEDITOR.NET
fomodインストーラー作成時のXMLエディタとして利用。
http://www.xmleditor.jp/


## 旧バージョンのゲームデータを入手する方法
Steamクライアントをインストールした状態で、steam://open/console にアクセスする。
Steamがコンソールモードで起動するので、以下のコマンドを実行する。

```
download_depot {AppID} {DepotID} {ManifestID}
```

`DepotID` や `ManifestID` は https://steamdb.info/ から入手可能。

* Skyrim: https://steamdb.info/app/72850/depots/  
* SkyrimSE: https://steamdb.info/app/489830/depots/

実行すると、`C:\Program Files (x86)\Steam\steamapps\content` の中に `app_{AppID}\depot_{DepotID}` というディレクトリが作成されて、その中にデータがダウンロードされる。  

以下、大きく変更があったバージョンごとの入手コマンド。  

●: フォントに関するコンテンツを含んでいない。
★: フォントに関するコンテンツを含んでいる。

### Skyrim
#### v1.9.31.0 (2013.3.1)
日本語版の最終バージョン

```
★ The Elder Scrolls V: Skyrim Japanese (1 May 2013 – 08:20:28 UTC)
download_depot 72850 72861 400878757036949667

● Skyrim High Resolution Texture Pack (16 June 2014 – 08:08:16 UTC)
download_depot 72850 202485 3360479978025462854

● The Elder Scrolls V: Skyrim japanese Dawnguard (16 June 2014 – 08:08:17 UTC)
download_depot 72850 211725 8299795016551985184

● The Elder Scrolls V: Skyrim japanese Hearthfire (16 June 2014 – 08:08:19 UTC)
download_depot 72850 220765 257722701370938794

● The Elder Scrolls V: Skyrim Japanese Dragonborn (16 June 2014 – 08:08:21 UTC)
download_depot 72850 226888 921222014325323019
```

#### v1.9.32.0 (2013.3.19)
英語版の最終バージョン

```
● Skyrim exe (19 March 2013 – 18:40:17 UTC)
download_depot 72850 72852 5176728229505148062

● The Elder Scrolls V: Skyrim Dragonborn (16 June 2014 – 08:08:15 UTC)
download_depot 72850 226880 7775806625498321311

● The Elder Scrolls V: Skyrim Hearthfire (16 June 2014 – 08:08:15 UTC)
download_depot 72850 220760 11352126252031938

● The Elder Scrolls V: Skyrim Dawnguard DLC (16 June 2014 – 08:08:16 UTC)
download_depot 72850 211720 8455218688827025070

● Skyrim High Resolution Texture Pack (16 June 2014 – 08:08:16 UTC)
download_depot 72850 202485 3360479978025462854

★ Skyrim Content (12 March 2015 – 18:06:51 UTC)
download_depot 72850 72851 430694959351693705

● The Elder Scrolls V: Skyrim english (5 September 2024 – 15:02:03 UTC)
download_depot 72850 72853 5477471785942614203
```

### SkyrimSE
#### v1.5.97.0 (～2019.11.20)
1.5系の最終バージョン

```
● Skyrim Special Edition exe (20 November 2019 – 21:45:02 UTC)
download_depot 489830 489833 2289561010626853674

★ Skyrim Special Edition core (20 November 2019 – 21:45:02 UTC)
download_depot 489830 489832 8702665189575304780

★Skyrim Special Edition japanese (13 March 2019 – 14:57:00 UTC)
download_depot 489830 544861 3124924854513767273
```

#### v1.6.317.0 (2021.11.11～)
このバージョンを境にSE/AE/VRのコア部分が統合された模様。

#### v1.6.629.0 (2022.9.15)
日本語版1.6系の初期バージョン  
ここからコアに日本語版も統合され、日本語デポには音声コンテンツのみ収録されるようになっている。  
フォント定義はこれまでの `Interface/fontconfig.txt` 固定ではなく、`Skyrim_Default.ini` 中の `sFontConfigFile` で指定するように変更された模様。日本語版の場合 `Interface\FontConfig_ja.txt` がデフォルトとなっている。

#### v1.6.1170.0 (2024.1.17～現在)
2025.4.1時点の最新版

```
● Skyrim Special Edition exe (17 January 2024 – 16:01:14 UTC)
download_depot 489830 489833 1914580699073641964

★ Skyrim Special Edition core (17 January 2024 – 16:01:14 UTC)
download_depot 489830 489832 8042843504692938467

●Skyrim Special Edition japanese (15 September 2022 – 10:25:14 UTC)
download_depot 489830 544861 3494476046078906882
```


## ゲームバージョン毎のフォント定義
### Skyrim
| ゲームバージョン  | フォント定義ファイル | 読み込みフォント |
| - | - | - |
| v1.9.31.0(JP) | Interface/fontconfig.txt | Interface/fonts_console.swf, Interface/fonts_jp.swf |
| v1.9.32.0(EN) | Interface/fontconfig.txt | Interface/fonts_console.swf, Interface/fonts_en.swf |

| ゲームバージョン  | フォントファイル | 格納フォント |
| - | - | - |
| v1.9.31.0(JP) | Interface/fonts_console.swf | Arial |
| v1.9.31.0(JP) | Interface/fonts_jp.swf | Skyrim_JP_EveryFont, Dragon_script, Skyrim_JP_HandWriteFont, MS PGothic, Daedric, Dwemer, Falmer, SkyrimSymbols, Mage Script, SkyrimBooks_Unreadable, Futura Condensed, Skyrim_JP_BookFont |
| v1.9.32.0(EN) | Interface/fonts_console.swf | Arial |
| v1.9.32.0(EN) | Interface/fonts_jp.swf | Futura CondensedLight, Futura Condensed, Futura Condensed (Bold), Dragon_script, SkyrimBooks_Gaelic, SkyrimBooks_Handwritten_Bold, Daedric, Dwemer, Falmer, SkyrimSymbols, Mage Script, SkyrimBooks_Unreadable |

| フォントマップ名  | v1.9.31.0(JP) | v1.9.32.0(EN) |
| - | - | - |
| $ConsoleFont | Arial | Arial |
| $StartMenuFont | Skyrim_JP_EveryFont | Futura Condensed |
| $DialogueFont | Skyrim_JP_EveryFont | utura CondensedLight |
| $EverywhereFont | Skyrim_JP_EveryFont | Futura CondensedLight |
| $EverywhereBoldFont | Skyrim_JP_EveryFont | Futura Condensed (Bold) |
| $EverywhereMediumFont | Skyrim_JP_EveryFont | Futura Condensed |
| $DragonFont | Dragon_script | Dragon_script |
| $SkyrimBooks | Skyrim_JP_BookFont | SkyrimBooks_Gaelic |
| $HandwrittenFont | Skyrim_JP_HandWriteFont | SkyrimBooks_Handwritten_Bold |
| $HandwrittenBold | Skyrim_JP_HandWriteFont | SkyrimBooks_Handwritten_Bold |
| $FalmerFont | Falmer | Falmer |
| $DwemerFont | Dwemer | Dwemer |
| $DaedricFont | Daedric | Daedric |
| $MageScriptFont | Mage Script | Mage Script |
| $SkyrimSymbolsFont | SkyrimSymbols | SkyrimSymbols |
| $SkyrimBooks_UnreadableFont | SkyrimBooks_Unreadable | SkyrimBooks_Unreadable |
| $CreditsFont | Futura Condensed | - |



### SkyrimSE
| ゲームバージョン  | フォント定義ファイル | 読み込みフォント |
| - | - | - |
| v1.5.73.0(JP) | Interface/fontconfig.txt | Interface/fonts_console.swf, Interface/fonts_en.swf |
| v1.5.97.0(EN) | Interface/fontconfig.txt | Interface/fonts_console.swf, Interface/fonts_en.swf |
| v1.6.629-1170.0(JP) | Interface/fontconfig_ja.txt | Interface/fonts_console.swf, Interface/fonts_ja.swf, Interface/fonts_buttons.swf |
| v1.6.629-1170.0(EN) | Interface/fontconfig.txt | Interface/fonts_console.swf, Interface/fonts_en.swf, Interface/fonts_cclub.swf |

| ゲームバージョン  | フォントファイル | 格納フォント |
| - | - | - |
| v1.5.73.0(JP) | Interface/fonts_console.swf | Arial |
| v1.5.73.0(JP) | Interface/fonts_en.swf | Skyrim_JP_EveryFont, Dragon_script, Skyrim_JP_HandWriteFont, MS PGothic, Daedric, Dwemer, Falmer, SkyrimSymbols, Mage Script, SkyrimBooks_Unreadable, Futura Condensed, Skyrim_JP_BookFont |
| v1.5.97.0(EN) | Interface/fonts_console.swf | Arial (exp:$ConsoleFont) |
| v1.5.97.0(EN) | Interface/fonts_en.swf | Controller  Buttons (exp:$ControllerButtons), Controller  Buttons inverted (exp:$ControllerButtonsInverted), Eurostile Cyr Std (Bold, exp:$CClub_Font_Bold), Eurostile LT Cyr Std (exp:$CClub_Font), Futura CondensedLight, Futura Condensed, Futura Condensed (Bold), Dragon_script, SkyrimBooks_Gaelic, SkyrimBooks_Handwritten_Bold, Daedric, Dwemer, Falmer, SkyrimSymbols, Mage Script, SkyrimBooks_Unreadable |
| v1.6.629-1170.0(JP/EN) | Interface/fonts_console.swf | Arial (exp:$ConsoleFont), Consolas |
| v1.6.629-1170.0(JP) | Interface/fonts_ja.swf | Controller  Buttons (exp:$ControllerButtons), Controller  Buttons inverted (exp:$ControllerButtonsInverted), 1_Skyrim_JP_EveryFont_0805 (Bold, exp:$CClub_Font), 22_Skyrim_JP_BookFont_0805, Futura Condensed, 5_Skyrim_JP_HandWriteFont_0805, Dragon_script, SkyrimBooks_Gaelic, SkyrimBooks_Handwritten_Bold, Daedric, Dwemer, Falmer, SkyrimSymbols, Mage Script, SkyrimBooks_Unreadable |
| v1.6.629-1170.0(JP) | Interface/fonts_buttons.swf | Controller  Buttons inverted (exp:$ControllerButtonsInverted), Controller  Buttons (exp:$ControllerButtons) |
| v1.6.629-1170.0(EN) | Interface/fonts_en.swf | Controller  Buttons (exp:$ControllerButtons), Controller  Buttons inverted (exp:$ControllerButtonsInverted), Eurostile Cyr Std (Bold, exp:$CClub_Font_Bold), Eurostile LT Cyr Std (exp:$CClub_Font), Futura CondensedLight, Futura Condensed, Futura Condensed (Bold), Dragon_script, SkyrimBooks_Gaelic, SkyrimBooks_Handwritten_Bold, Daedric, Dwemer, Falmer, SkyrimSymbols, Mage Script, SkyrimBooks_Unreadable |
| v1.6.629-1170.0(EN) | Interface/fonts_cclub.swf | Eurostile Cyr Std (Bold, exp:$CClub_Font_Bold), Eurostile LT Cyr Std (exp:$CClub_Font) |

CreationClubが実装されたあたりから、フォントに対し `ExportAssets` タグが付き始めた。  

| フォントマップ名  | v1.5.73.0(JP) | v1.5.97.0(EN) | v1.6.629-1170.0(JP) | v1.6.629-1170.0(EN) |
| - | - | - | - | - |
| $ConsoleFont | Arial | Arial | Consolas | Consolas |
| $StartMenuFont | Skyrim_JP_EveryFont | Futura Condensed | 1_Skyrim_JP_EveryFont_0805 | Futura Condensed |
| $DialogueFont | Skyrim_JP_EveryFont | Futura CondensedLight | 1_Skyrim_JP_EveryFont_0805 | Futura CondensedLight |
| $EverywhereFont | Skyrim_JP_EveryFont | Futura CondensedLight | 1_Skyrim_JP_EveryFont_0805 | Futura CondensedLight |
| $EverywhereBoldFont | Skyrim_JP_EveryFont | Futura Condensed (Bold) | 1_Skyrim_JP_EveryFont_0805 | Futura Condensed (Bold) |
| $EverywhereMediumFont | Skyrim_JP_EveryFont | Futura Condensed | 1_Skyrim_JP_EveryFont_0805 | Futura Condensed |
| $DragonFont | Dragon_script | Dragon_script | Dragon_script | Dragon_script |
| $SkyrimBooks | Skyrim_JP_BookFont | SkyrimBooks_Gaelic | 22_Skyrim_JP_BookFont_0805 | SkyrimBooks_Gaelic |
| $HandwrittenFont | Skyrim_JP_HandWriteFont | SkyrimBooks_Handwritten_Bold | 5_Skyrim_JP_HandWriteFont_0805 | SkyrimBooks_Handwritten_Bold |
| $HandwrittenBold | Skyrim_JP_HandWriteFont | SkyrimBooks_Handwritten_Bold | 5_Skyrim_JP_HandWriteFont_0805 | SkyrimBooks_Handwritten_Bold |
| $FalmerFont | Falmer | Falmer | Falmer | Falmer |
| $DwemerFont | Dwemer | Dwemer | Dwemer | Dwemer |
| $DaedricFont | Daedric | Daedric | Daedric | Daedric |
| $MageScriptFont | Mage Script | Mage Script | Mage Script | Mage Script |
| $SkyrimSymbolsFont | SkyrimSymbols | SkyrimSymbols | SkyrimSymbols | SkyrimSymbols |
| $SkyrimBooks_UnreadableFont | SkyrimBooks_Unreadable | SkyrimBooks_Unreadable | SkyrimBooks_Unreadable | SkyrimBooks_Unreadable |
| $CreditsFont | Futura Condensed | - | Futura Condensed | - |
| $CClub_Font | - | Eurostile LT Std (Roman) | 1_Skyrim_JP_EveryFont_0805 | Eurostile LT Cyr Std (Roman) |
| $CClub_Font_Bold | - | Eurostile LT Std (Demi) | 1_Skyrim_JP_EveryFont_0805 | Eurostile LT Cyr Std (Demi) |
| ControllerButtons | - | Controller  Buttons | Controller  Buttons | Controller  Buttons |
| ControllerButtonsInverted | - | Controller  Buttons inverted | Controller  Buttons inverted | Controller  Buttons inverted |
| Times New Roman | - | - | 1_Skyrim_JP_EveryFont_0805 | - |

フォントマップは使用していないものがあっても、原理的には動作に影響ないはず。つまり、全部のフォントマップを網羅していればSkyrim/SkyrimSE/英語版/日本語版を気にせず利用できるマスターコンフィグが作れる。

## バニラバグフィックスパッチの作り方
### 本UIの内蔵フォント除去
SE版はv1.6.629以降解消しているが、下位バージョンを使用している場合向けにパッチする必要あり。  
英語版の最新の本UI `interface/book.swf` にはなぜかフォントファイルそのものが格納されており、そちらが優先されてしまう。  
[FFDec](https://github.com/jindrapetrik/jpexs-decompiler)を使用して余分なフォントを除去する。
動作確認としては、「エリトリスのノート」や「アーヴェルの日記」を開いてみると良い。  
参考: https://obachanskyrim.blogspot.com/2012/07/bookswf.html

### レベルアップメニューUI
SE版はv1.6.629以降解消しているが、下位バージョンを使用している場合向けにパッチする必要あり。  
日本語版のレベルアップメニューUI `interface/levelupmenu.swf` のフォントマップが正しく指定されておらず、きちんと表示されない。英語版ではバグがないため、英語版の `interface/levelupmenu.swf` を取り出して使用する。  
ただ、デフォルトUIはバグは解消されていても表示が非常に大きく見切れているため、そこも修正する。yminを増やして文字の位置を変えた上で、HTMLレンダリングに変えてフォントサイズを指定する。

## SkyUI向けMCM専用フォントマップ適用パッチの作り方
コンフィグメニュー(MCM)はデフォルトで `$EverywhereFont` 系の汎用フォントを使用するが、日本語のような全角フォントだとUIをぶち抜いてしまう。かと言って `$EverywhereFont` 系にコンデンスドなフォント(幅を狭くしたもの)を指定すると他のUIが見づらくなる。その解決策として、MCMには専用のフォントマップを使用するようにする。
MCMを実現しているUIは LE/SE共に`Interface/skyui/configpanel.swf` 。[FFDec](https://github.com/jindrapetrik/jpexs-decompiler)を使用してフォントマップを指定している箇所を書き換える。

## 参考
Fomod Doc: https://fomod-docs.readthedocs.io/en/latest/index.html