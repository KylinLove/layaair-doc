# LayaNative2.0

LayaNative 2.0は開発者にとって最大の改善はLayaAir 3 Dを全面的にサポートし、開発者に3 D-Appのリリースを便利にすることです。また、LayaNative 2.0はLayaBoxが5世代にわたるNativeソリューションを覆しました。目的はより速く、より開放的で、より簡単で、より良い3 Dを設計目標としています。LayaNative 2.0はWebGL＋の特許技術の設計理念を採用し、より先進的で、より開放的で、WebGL契約のように、関数の不定規則だけを定めて、小さくて、しかも拡張性の強い解決案です。エンジンの構造、性能、機能、使いやすさの四つの面から簡単に紹介します。

##一、エンジンアーキテクチャ
開発者がLayaAirエンジンで開発したプロジェクトは、ブラウザに投稿することもできるし、元のAppに発表することもできます。下図はエンジンの構造図と開発フローチャートです。
![图](img/1.jpg)

![图](img/2.png)

##二、性能

LayaNative 2.0はコード再構成を経て、性能は1.0バージョンと比較して大きく向上しました。
1、LayaNative 1.0と比較する。


|       |2D   |3D     |
|:---：|:--：|：
|Android 124;を10%上げ90%向上させる
|IOS 124; 13%アップ270%アップ

2、国内の他の汎用runtimeエンジンと比較する。


|       |2D    |3D       |
|:------：|:------------------：|
|Android 124;は85%向上し90%向上します。
|IOS 124;を240%上げて270%上げます。



##三、拡張機能

1、LayaNative 2.0はシングルスレッドとダブルスレッドの2つのモードをサポートしていますが、開発者は自分のプロジェクトの実際のテスト結果に基づいて、どのモードを使うかを決めています。

＊スレッドモード：JSとRenderはスレッド内で動作します。
*利点：操作に遅延がない（例えば、touch、キー）。
*欠点：性能はダブルスレッドモードに及ばない。
＊ダブルスレッドモード：JSとRenderはそれぞれのスレッドで動作します。
*長所：性能はシングルスレッドバージョンより高いです。
*欠点：操作には半フレームがあり、最大から一フレームまでの遅延（例えば、touch、ボタン）があります。

2、グラフィックカードのテクスチャの圧縮をサポートし、レンダリング効率を高めるだけでなく、現存の占用も減らすことができます。

3、最適化された二次開発は、より分かりやすく、開発者が使いやすく、詳細は文書を参照してください。
https://github.com/layabox/layaair-doc/tree/master/LayaAir 2.0/Chinese/LayaNative/Secondary Development


##四、使いやすさ

###1.より便利なデバッグ機能を提供する

1）Androidプラットフォームは本物の機械でJavaScriptを調整できます。

LayaNative 1.0バージョンでは、デバッグ項目のJavaScriptコードは、consolie.logまたはalert関数のみを呼び出します。layaNative 2.0バージョンではChromeブラウザを使ってJavaScriptコードのデバッグを正式にサポートします。Chromeのコーディネーターでコードを断点的に追加したり、コード追跡したりする機能があります。

![图](img/debug_connected.png)

詳細は文書を参照:
https://github.com/layabox/layaair-doc/tree/master/LayaAir 2.0/Chinese/LayaNative/realuviceugg ing

2）テストアプリはコードスキャン起動項目に対応しています。

開発者がより速くデバッグ開発ができるように、新しいバージョンのテストアプリにスキャンコード起動アプリの機能を追加しました。デバッグ時にマニュアルでURLを入力する手間を省きました。

![图](img/app_debug_1_0.png)

詳細は文書を参照:
https://githb.com/layabox/layaair-doc/tree/master/LayaAir 2.0/Chinese/LayaNative



###2.より豊富な起動画面をカスタマイズできます。

LayaNative 2.0のloadingviewはプラットフォーム原生言語を用いて開発されたもので、AndroidはJava言語を使用し、IOSはObjective-C言語を使用している。1.0をJavaScript言語で開発したLoadingViewに比べて、2.0はより豊富なカスタマイズ機能を提供しています。写真を変更するだけでなく、開発者はプラットフォーム言語を使って自分のほしい機能を実現することができます。

![图](img/loadingview_2_0.png)

詳細は文書を参照:
https://github.com/layabox/layaair-doc/tree/master/LayaAir 2.0/Chinese/LayaNative/loadingyi ew