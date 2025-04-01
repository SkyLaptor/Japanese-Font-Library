# README: SkyUI 5.2SE用 MCM専用文字
**当オプションの利用は非推奨です。MCMに日本語が収まらなくて困っているという方は[Wider MCM Menu for SkyUI](https://www.nexusmods.com/skyrimspecialedition/mods/22825)の利用をお勧めします。**  
SkyUI 5.2SEのMCM表示UIファイルを置き換え、専用のフォントを利用できるようにします。  
オプション導入状態では`Interface\fontconfig.txt`または`Interface\fontconfig_ja.txt`に対し以下のようなフォントマップを追記し、適切にフォントを読み込ませる必要があります。追記しない場合、MCMがすべて□表示になります。  

```
map "$MCMFont" = "フォント名" Normal
map "$MCMMediumFont" = "フォント名" Normal
map "$MCMBoldFont" = "フォント名" Normal
```