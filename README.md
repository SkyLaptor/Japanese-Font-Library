# Japanese Font Library

## インストール


# メモ
## 旧バージョンのゲームデータを入手する方法
Steamクライアントをインストールした状態で、ターミナルで `start steam://open/console` を実行する。
実行するとSteamがコンソールモードで起動するので、以下のコマンドを実行する。

```:steamconsole
download_depot {AppID} {DepotID} {ManifestID}
```

`DepotID` や `ManifestID` は [SteamDB](https://steamdb.info/) から入手可能。

Skyrim(LE): https://steamdb.info/app/72850/depots/  
SkyrimSE: https://steamdb.info/app/489830/depots/

実行すると、`C:\Program Files (x86)\Steam\steamapps\content` の中に `app_{AppID}\depot_{DepotID}` というディレクトリが作成されて、その中にデータがダウンロードされる。

### Skyrim v1.9.32(11 March 2025 – 23:17:30 UTC)の最新リソース
```:steamconsole
● Skyrim exe
download_depot 72850 72852 5176728229505148062

● Skyrim Content
download_depot 72850 72851 430694959351693705

● The Elder Scrolls V: Skyrim Dragonborn
download_depot 72850 226880 7775806625498321311

● The Elder Scrolls V: Skyrim Hearthfire
download_depot 72850 220760 11352126252031938

● The Elder Scrolls V: Skyrim Dawnguard DLC
download_depot 72850 211720 8455218688827025070

● Skyrim High Resolution Texture Pack
download_depot 72850 202485 3360479978025462854

● The Elder Scrolls V: Skyrim english
download_depot 72850 72853 5477471785942614203

● The Elder Scrolls V: Skyrim Japanese
download_depot 72850 72861 400878757036949667

● The Elder Scrolls V: Skyrim japanese Dawnguard
download_depot 72850 211725 8299795016551985184

● The Elder Scrolls V: Skyrim japanese Hearthfire
download_depot 72850 220765 257722701370938794

● The Elder Scrolls V: Skyrim Japanese Dragonborn
download_depot 72850 226888 921222014325323019
```

### SkyrimSE v1.6.1170(18 March 2025 – 03:40:49 UTC)の最新リソース
```:steamconsole
● Skyrim Special Edition disk
download_depot 489830 489831 8442952117333549665

● Skyrim Special Edition core
download_depot 489830 489832 8042843504692938467

● Skyrim Special Edition exe
download_depot 489830 489833 1914580699073641964

●Skyrim Special Edition japanese
download_depot 489830 544861 3494476046078906882
```
