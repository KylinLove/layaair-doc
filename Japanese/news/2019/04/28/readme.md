# LayaAir引擎放弃Canvas API，打造次世代3D引擎与云游戏引擎，提供AI赋能！

>2019-04-28

LayaAirエンジンはCanvasの元のAPIを放棄して、2 Dを放棄するのではなくて、もっと良い発展の2 Dと3 Dのためです！どうしてキャンバスの元のAPIを放棄しますか？また、LayaAirエンジンの未来の発展計画について、ここで皆さんとお話ししましょう。

### **1、Canvas元のAPIの性能が悪い**

Canvasが発売された後に、自分のAPIを持って開発者に素早く動的効果を実現させて、ゲームを作ることを含みます。長い間、HTML 5エンジンはすべてブラウザの中のCanvasが持っている2 D APIに基づいて設計されていますが、これらのAPIは高性能なグラフィックスをレンダリングするために設計されたのではなく、複雑なゲームの性能要求を満たすことができないという問題をもたらしました。Canvasのエンジンに基づいて作ったゲームは、APPの画面品質を達成するためには、Runtimeプラグインによって加速されてこそ、ゲームの性能に対するニーズを満たすことができる。今日でも、Canvas粒子とWebGL粒子の性能は100倍以上の差があります。

### **2、Canvas API対応でエンジン機能を束縛する**

2015年、Layaboxは第二世代エンジンLayaAirを開発する際に、まずWebGLとCanvasの互換性のあるモデルを発売しました。そしてエンジンを極めて最適化したので、全体的な性能は大幅に向上しています。WebGLをサポートする環境下で、Runtimeを利用しなくてもAPPクラスのゲームの性能需要を満たすことができます。まだWebGLがサポートされていない環境では自動的にCanvasモードに切り替わり、Canvasモードへの互換性が保たれています。

もちろん、互換性も価格があります。エンジンの機能拡張を制限します。たとえばWebGLモードでは、エンジンの中にテクスチャのための実用的な属性を追加したいですが、Canvasの元のAPIはサポートされていません。また、2 Dにカスタムsharer機能を追加したい場合も、互換性のためには、捨てる必要があります。他にも多くの応用シーンが例として挙げられません。つまり、CanvasとWebGLの互換性を保つためには、エンジンの使いやすさ、機能の拡張に縛られます。

### **3、GPUグラフィックスAPIを全面的に抱擁する**

上層部のCanvas 2 D APIを捨てると、LayaAirエンジンは、下層部のGPUグラフィックスAPIに基づいて、エンジンを設計し、束縛から脱却することでエンジンをより自由に発展させることができる。特に3 D空間画布の設計によって、2 Dと3 Dシーンが非常に友好的に融合することができます。

時代の発展につれて、ハードウエアの設備は今日まで発展して、WebGL環境のプラットフォームを支持しませんでした。また、3 DはもともとCanvasモードでは動作しないので、3 Dゲームにとっては、Canvasモードの互換性は価値がない。したがって、我々はCanvasの原生APIとの互換性をはかり、深く考えた結果、率先してCanvasの原生APIの互換性を放棄しました。

現在から見れば、全体のエンジンの体積を減らす以外に、Canvasの元のAPIを捨てて開発者に対して無意識です。未来を見ると、LayaAirをもっと自由にして、もっと強くして、使いやすくて、適用範囲がもっと広い全プラットフォームのゲームエンジンの方向に発展させます。

>事前にドラマを通して、5月にリリースされるLayaAir 2.1 betaはすでにCanvasの元のAPIの放棄を完了しました。Canvasの元のAPI互換性のある開発者がいたら、LayaAir 2.1以下のバージョンを使えばいいです。

### **4、設備の性能を絶えず圧搾する**

究極の性能は常にLayaAir設計研究開発の礎石の一つです。ですから、私たちは絶えず設備の性能を搾取します。LayaAirの現在サポートしているWebGL 1.0を除いて、私たちはもうすぐエンジンの中でWebGL 2.0をサポートします。そして、常にWebGPUへの関心を持っています。一旦WebGPUが成熟したら、すぐにエンジンサポートをします。

エンジン機能の性能最適化において、リアルタイムレンダリング性能、骨格動画モデルの性能などの面で引き続き極致の最適化と向上を行います。つまり、究極の性能はLayaAirエンジンの追求です。

# **5、次世代三次元エンジン**

周知のように、性能以外に、3 Dの成熟とリードはLayaAirエンジンの最大の優位性です。LayaAirエンジンは今後も3 Dエンジンの投入を強めていきます。绝えずエンジンの実用的な机能を豊かにし、エンジンの使いやすさを强化するとともに、PBR材质のレンダリング効果、多光源レンダリング及び多光源シェーディング効果、グローバル光照射、遅延レンダリング、オープンPost-processパイプライン及びHDR、SSAO、景深などの后期処理効果を重点的に向上させる。

LayaAirエンジンの位置付けは高性能次世代の三次元エンジンです。

### **6、5 GクラウドゲームエンジンとAI**

5 G時代が近づくにつれて、ゲーム産業関連の最大のものはクラウドコンピューティング、3 D、AR、VR、AIの高速発展である。Layaboxはエンジン側として先行しなければならず、すでに次世代クラウドゲームエンジンの探索と設計を開始しています。

5 Gネットワークの最も明らかな特徴の一つはスピードが速いことで、毎秒Gbpsランクのダウンロード速度は、きっとエンジンに多くのことをさせることができます。例えば、いくつかのハードウエアに対して圧力の計算とレンダリングを雲の端に置いて処理します。このようにして、性能が高くないテレビボックス、一体機、モバイル機器などの5 G端末を使えます。

5 G時代は万物の相互接続の時代で、未来の各種の主流のプラットフォームについて、LayaAirエンジンはすべて支持を行って、ブラウザーAPIの束縛を抜け出した後に、LayaAirエンジンは更に全プラットフォームのエンジンの位置付けを重視します。ARとVRは5 G時代に高速発展が期待されています。主流のタイプになる可能性もあります。これらは良質の3 Dエンジンのサポートから離れていません。LayaAirエンジンは将来5 G時代のARとVRの開発ニーズを完全に満たすことができます。WebXR標準を全面的にサポートします。開発者はLayaAirエンジンの製品を使ってSteeamなどの有名なプラットフォームに登録することができます。

最後に言わなければならないのはAIモジュールです。AIは科学技術の高速発展と社会の進歩の趨勢であり、自主的に学習と自動的なインタラクティブ能力を持ち、バーチャルゲームの世界のプレイヤーにもっと没頭的な体験をさせる。例えば、ゲームガイド、競技の付き添い、基礎的な社交、ストーリーのインタラクティブなどです。ゲームの痛点需要で、AIモジュールは今後LayaCloudフレームのオプション機能になる予定です。

LayaClooudはLayaAir 2.0エンジンと一緒に発売された無サーバーゲームのフレームです。このフレームを使って、管理サーバに接触する必要がなく、フロントエンド言語を使って、フレームワークで提供されるサーバAPIを使って、オンラインゲームを簡単に作成することができます。現在のフレームワークは、ユーザー登録と検証、データ記憶と読み取り、管理部屋の作成、ユーザーマッチングと部屋への参加、メッセージ放送とフレーム同期などのオンラインゲームの一般的なAPIを提供しています。開発者が製品業務の論理開発により焦点を当て、モジュール開発時間を大幅に削減し、ネットワーク開発の敷居とコストを低減することを目標とする。

### **7、可視化3 D編集ツール**

3 Dツールの可視化については、将来的には長い間、3つの主要ラインを維持し、1つのラインは現在のユニティツールベースのプラグイン方式である。開発者はUnity環境でLayaAirプラグイン内蔵の材質を使って3 Dシーンを編集し、プラグインを通じて無料でエクスポートして使用できます。

もう一つのラインは4月26日に発表されたプログラムフリーの3 Dシーン開発ツールLayaMakerで、このツールは特定の業界（例えば教育）の3 Dインタラクティブ製品の可視化開発をサポートしています。使用者はプログラムの基礎が全く必要なくて、簡単に操作できます。LayaMakerの詳細については、リンクをクリックして知ることができます。[Layabox推出无编程3D教育制作工具LayaMaker，携手精锐教育集团进军新领域！](http://mp.weixin.qq.com/s?__biz=MzAxMjI4NjA1OA==&mid=2650584620&idx=1&sn=fcf341b4b53e1c3d4f8e500c75893a06&chksm=83bc3729b4cbbe3f52fd830e15be04e808ba43103113abef2474322979feae941731589f7fd2&scene=21%3Ch1%3Ewechat_redirect)

第三条ラインはLayaAir開発者向けの3 D編集ツールで、このツールはすでに原形があり、2.0の正式版が発売される予定です。私たちの期待の目標に達していないので、一時的に遮蔽し、再構成が満足されると、今後はLayaAirエンジンに適した3 D編集ツールを発売します。

### **8、エンジン開発言語をType Scriptに切り替える**

LayaAirエンジンはAS 3、TS、JSの3つの言語開発製品に対応していますが、エンジン自体はAS 3言語に基づいて開発されています。言語の変更をサポートする核心的な原因は、AS 3言語はすでにメンテナンスを停止しており、近代的なプログラミング言語の新しい特性をサポートすることができないからです。新しい特性をより友好的に使うために、LayaAirエンジンは近くエンジン開発言語を変更する予定です。これは広大な開発者には無感知です。開発者はAS 3、TS、JSの3つの言語で製品を開発することができるからです。しかし、長い目で見れば、TSは新しい特性、LayaAirIDEのサポート、効率的な開発などの各方面に対してより友好的であるので、開発者の皆様には、新しいプロジェクトを作成する際に、TSを優先開発言語として採用することを提案します。

エンジン開発言語を変更するのは、私たちのエンジン開発者が究極のエンジンの追求に基づいて決定しただけです。これは一種の態度です。

### **9、LayaAirエンジンをさらに開放する**

LayaAirエンジンはGithubにずっと委託していますが、Githubに基づいて開発されたわけではありません。毎月公式サイトが更新された時だけ、同時に更新されます。今後、LayaAirエンジンの開発チームはGithubの活性化を強化し、エンジンは公網に基づくGithubを開発し、いつでも最新のコードをGithubに提出して、Layaboxチームのエリート大神さんをLayaAirエンジンの開発に参加させます。

LayaAirエンジンコードの提出に参加した開発者に対して、コードが採用されると、Layaboxの現金奨励を受けます。積極的な貢献者に招待し、LayaAirグローバル開発チームに参加し、LayaAirエンジンの重要な技術決定討論に参加するよう要請しました。

###最後に書く

今後、LayaAirエンジンは2 Dの最適化と安定を維持し、次世代3 Dエンジンの発展に重点を置いています。技術上の究極の追求に対して、足を止めたことがなく、製品の使いやすさに対して、不足がありました。LayaAir 2.0から私達は常に十分な重視を維持し、絶えず最適化を高めています。私たちが前に進むたびに、多くの開発者のサポートを離れられません。ありがとうございます。友達を歓迎して友達の輪あるいはWeChatグループを転送して、更に多くの開発者に私達の最新の技術の動態を理解させます。