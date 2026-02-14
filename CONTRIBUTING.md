# 開発ガイドライン
## はじめに（必ずお読みください）
本プロジェクトへの貢献を検討いただきありがとうございます。 メンテナーの負担軽減とプロジェクトの品質維持のため、以下のルールを遵守してください。これらが守られていないプルリクエストは、内容を確認せずにクローズする場合があります。

* Issue優先: 大きな変更や機能追加を行う前に、必ずIssueで提案し合意を得てください。
* 最小PRs: 変更は可能な限り最小単位に分割してください。巨大な変更はレビュー対象外となります。
* 品質管理: ローカルでのビルドおよびテスト通過は必須条件です。

## 開発フロー
本リポジトリでは GitLab-Flow を採用しています。

1. mainブランチ: 全ての開発のベースです。
2. 作業ブランチ: `main` からブランチ( `feature/issue-番号` 等）を切って作業してください。
3. マージ: `main` へのマージは、レビュー承認およびCI通過後に行われます。
4. プレリリース: 仮公開は、`main` から `pre-production` ブランチへのマージによって実行されます。
5. リリース: 公開は、`pre-production` から `production` ブランチへのマージによって実行されます。

## 大まかな開発手順

1. リポジトリから `main` ブランチをクローン/チェックアウトする。
2. 開発ツール類、テスト環境をセットアップする。
3. コンテンツを修正し、テストを実行する。
4. `main` ブランチに対してプルリクエストを作成する。

## テスト環境
* 対象のゲーム: Skyrim, SkyrimSE(SkyrimAE), SkyrimVR
* 対象のModマネージャー: [Vortex](https://www.nexusmods.com/about/vortex), [ModOrganizer2](https://www.nexusmods.com/about/vortex) ※公式そのままの状態でカスタムを加えていないものであること。
* Mod: [SKSE](https://skse.silverlock.org/), [SkyUI](https://www.nexusmods.com/skyrimspecialedition/mods/12604) ※フォント周りに影響を及ぼす場合はIssueで提案して下さい。



## ゲームバージョン追跡情報
### Skyrim v1.9.31.0 (2013.3.1)
* 日本語版の最終バージョン。

### Skyrim v1.9.32.0 (2013.3.19)
* 英語版の最終バージョン。

### SkyrimSE v1.5.97.0 (2019.11.20)
* 1.5系の最終バージョン。一部に人気のためこのバージョンも考慮して開発。

### SkyrimSE(AE,VR) v1.6.317.0 (2021.11.11)
* このバージョンを境にSE/AE/VRのコア部分が統合された模様。

### SkyrimSE(AE,VR) v1.6.629.0 (2022.9.15)
* 日本語版1.6系の初期リリース
* コア部分は各言語共通化され日本語リソースも格納されている。日本語デポには音声コンテンツのみ収録されるようになっている。  
* フォント定義はこれまでの `Interface/fontconfig.txt` 固定ではなく、`Skyrim_Default.ini` 中の `sFontConfigFile` で指定するように変更された模様。日本語版の場合 `Interface\FontConfig_ja.txt` がデフォルトとなっている。

### SkyrimSE(AE,VR) v1.6.1170.0 (2024.1.17)
2026.2.7時点の最新版


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

CreationClubが実装されたあたりから、フォントに対し `ExportAssets` タグが付き始めました。
調査したところ、フォントへの参照リンケージであり、格納フォント名と同じにした方が良い模様です。  

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

フォントマップは使用していないものがあっても、原理的には動作に影響はないはずです。つまり、全部のフォントマップを網羅していればゲームバージョンやエディションを気にせず利用できるマスターコンフィグが作れるということになります。


## ゲーム設定
テストをスムーズに行うための設定などのメモです。

### 最初のベセスダロゴを表示させない
Skyrim.ini内に以下を追加。

```
[General]
sIntroSequence=
```

Skyrim.iniの場所はOSやMO2の設定で異なります。

* 通常: `C:\Users\<username>\Documents\My Games\Skyrim Special Edition`
* 通常(OneDrive): `C:\Users\<username>\OneDrive\Document\My Games\Skyrim Special Edition`
* MO2: `<MO2 Skyrimインスタンスディレクトリ>\profiles\<プロファイル名>`

## Fomodについて
下記ドキュメントを参考にします。
https://fomod-docs.readthedocs.io/en/latest/index.html