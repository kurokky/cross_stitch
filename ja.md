# Inksacpeでクロスステッチデータを作る方法

## はじめに

このページを見ている方はInk/Stitchの存在を知っていると思います。Ink/StitchはInkscapeの拡張機能で、刺繍データを作成するためのツールです。しかし、クロスステッチのデザインを作成する方法についてはあまり情報がありません。  
ここでは、私が開発したInk/PixelとStitchHelperとInk/Stitchを使用してクロスステッチデータを作成する方法を説明します。


## なぜInk/PixelとStitchHelperを使うのか？

そもそも、Inkscapeはドット絵（海外ではPixel Art）を作成するのに適したツールではありません。  
そこで、ドット絵を簡単に作成できるInk/PixelというInkscapeの拡張機能を作りました。かなり無理矢理な実装にしているので専用ツールには叶いませんが、ある程度のデータであれば矩形ツールを駆使して作成するよりも遥かに簡単にドット絵を作成できます。

そして、StitchHelperはドット絵をクロスステッチデータに変換するためのInkscapeの拡張機能です。
こちらはフランスの[Alyogau](https://lyogau.over-blog.com/2022/03/faire-du-point-de-croix-avec-inkstitch-2.1-partie-1.html)の記事を参考にInkscapeの正方形をInk/Stitchで扱いやすくするための拡張です。

この2つの拡張を使うことで、ようやくInk/Stitchで刺繍用のデータを作成することができるようになります。

## 使い方

まずは、以下の方法でやってみてください。

1. InkscapeにInk/PixelとStitchHelperをインストールします。(Ink/Stitchと同じでDLしたファイルを解凍してextensionフォルダの中に入れてInkscapeを起動してください)
1. まずは、刺繍枠に適したDocumetntのサイズを設定します。Extension -> StitchHelper -> Embroidery Hoop から自分で使っている刺繍枠のサイズを選択します。（見つからない場合はCtrl+Shift+Dで変更してください）
1. Extension -> Ink/Pixel ->Pixel Size:Cross stitch(fabric count) -> 11spi(2.3mm) を選択します。（まずは2.3mmからはじめましょう）
1. すると、自動でGridと2.3mmの正方形が作成されます。(この正方形は、クリックしやすいように白のグラデーションがデフォルトになっています)
1. 自分のやりたいデザインを作ります。（くれぐれもPixelのサイズを変更したり、グループ化などは使わないようにしてください）
1. デザインができたら刺繍データにしたいPixelを選択します。（通常は何か1つのPixelを選択してCtrl+Aの全て選択で大丈夫です）
1. Extension -> StitchHelper -> Create the Pattern from Pixel -> By Separating layers for each color をクリックします。
1. すると、レイヤーに色ごとのクロスになったデータができます。(元のPixelデータのレイヤーは非表示になります)
1. 刺繍データにしたいレイヤーのデータだけを選択します。(このスクリーンショットでは他のレイヤーを非表示にしています)
1. Extension -> Ink/Stitch -> Tools:Satin -> Auto-Route Satin -> Columns を選択します。
1. 次にExtension -> Ink/Stitch -> Tools:Stroke -> Satin to Stroke を選択します。
1. Extension -> Ink/Stitch -> Params でデータを確認します。糸の細さが#50ならば「4」#60なら「3」をrepeatsに値を入れることをお勧めします。

データができたら、Ink/Stitchのシミュレーションで確認してみましょう。  

## FAQ

- Q. どうしてInk/Stitchにcommitしないんですか？
- A. 自分が開発している時に、どこまでがInk/Stitchで対応すべきか？が分からなかったからです。クロスステッチにはPixelデータを作ることから始まり、刺繍データに変換するまでに多くのステップがあります。  
  そのため、Ink/Stitchに全てを詰め込むのは適切ではないと考えました。  
  ただし、将来的にはInk/Stitchに取り込まれる可能性もあります。
- Q. どうしてInk/Pixelで作られるPixelは白のグラデーションがついているのですか？
- A. 最初は透明で、borderなしの正方形を作成していましたが、この状態だとInkscapeではクリックしづらく非常にストレスを感じました。  
  そこで、クリックしやすいように白のグラデーションをつけることにしました。  
  刺繍データに変換する際にはこのグラデーションは無視されるので問題ありません。
- Q. どうして多言語化しないのですか？
- A. moファイルを使って多言語化しようと思ったのですが、うまくいきませんでした。いつか対応するかもしれません。

## おわりに

Ink/Stitchユーザーは、なるべく高価な刺繍ソフトを使わずに刺繍データを作成したいと考えていると思います。少しでもあなたの役に立てば幸いです。


