# バニラ向けパッチ
## 何をするもの？
### 本UIの内蔵フォント除去
SE版は1.6系から解消しているが、互換性のためパッチが必要。  
本UI `Interface/book.swf` にはなぜかフォントファイルそのものが格納されており、そちらが優先されてしまう。  
[FFDec](https://github.com/jindrapetrik/jpexs-decompiler)を使用して余分なフォントを除去する。

### レベルアップメニューのUI
SE版は1.6系から解消しているが、互換性のためパッチが必要。  
日本語版のレベルアップメニューUI `Interface/levelupmenu.swf` のフォントマップが正しく指定されておらず、きちんと表示されない。英語版の最新から `Interface/levelupmenu.swf` を取り出して使用する。