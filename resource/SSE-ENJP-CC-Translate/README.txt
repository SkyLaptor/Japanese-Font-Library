# 無料配布CreationClubプラグイン用の翻訳ファイル
SSE v1.6.1170 英語版に対してを [Improved Japanese Translation](https://tktk1.net/skyrim/mymod/improved-japanese-translation/) v1.3.0 の英語設定の日本語化版を導入したけど、なぜか一部が日本語化されない。例えば `Red Apple` など。
これは何時ぞやからか以下のCreationClubの一部プラグインが無料で組み込まれたことによる弊害。
* ccBGSSSE001-Fish
* ccBGSSSE025-AdvDSGS
* ccBGSSSE037-Curios
* ccQDRSSE001-SurvivalMode

特にサバイバルモード(ccQDRSSE001-SurvivalMode)が相当量を上書きしている。

そこで、以下の手順をもって当翻訳ファイルを作成した。

1. Improved Japanese Translationを使用してユーザー辞書を生成。
2. v1.6.1170に含まれている対象プラグインの日本語化ファイルを使用してユーザー辞書を作成
3. Improved Japanese Translationを優先するようにして翻訳。