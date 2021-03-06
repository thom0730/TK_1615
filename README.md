# こえもじVR

![こえもじVR](https://github.com/jphacks/TK_1615/blob/master/Image/koemojiVR_logo.png)

## 製品概要
声を絵文字に変換して相手に伝える オンラインVRアプリケーション

### コミュニケーション X Tech

### 背景（製品開発のきっかけ、課題等）
課題「伝えたいことが上手く伝わらない。」

伝える手法、コミュニケーション手法は、実世界での対話に始まり、手紙、電話、チャットと発達してきて、現代では遠隔地で仮想的な対話ができるVRが、新たな手法として着目されています。

FaceBookは先月に、VR空間上での感情表現の曖昧さを問題視し、HTCviveのコントローラーを用いて取得したジェスチャーを感情と置き換え、アバターに表現する手法を提案しました。
しかし、特に日本人は、ジェスチャーや表情が外国人と比較して乏しい傾向にあり、また、コントローラーやセンサーなどのVR専用の外部機器はコストが高いといった問題があると考えます。

そこで、より的確な感情表現を低コストで汲み取ることはできないか、伝えたいことを目に見える形で手軽に伝えられないか、と考え、私たちはコミュニケーションに必須の「声」と、文字の意味を的確に表現する「絵文字」に着目しました。

### 製品説明（具体的な製品の説明）
こえもじVRは、伝えたいことが上手く伝わらない時などに、会話に含まれる単語🐶や感情😂をリアルタイム🕐に解析し、VR空間上に具象化💫して相手に伝える🙏🏻、オンラインコミュニケーションプラットフォームです。

例えば、VR空間上で
* しりとりで発言したものが目の前に現れます🍎->🐵->🎺->🍞
* 寿司の話題では🍣ネタの元となる🐟魚が周りを泳ぎ始めます
* 複数人でゲームをプレイしながら、＼ナイス！/などの発言の”声量"に応じて＼👏🏻/などの3D絵文字が”大きく"共有されます
* ブレストでは、話題に上がったものを目に見える形🖊🍍🍎🖊にして残すことができます
* 白熱した喧嘩では、感情を表現する顔文字を"喋る向き"に応じて、投げ掛け😠、ぶつけ合い😡、かわしあい合う😣ことができます
* リアルタイム音声認識は58カ国語に対応しているため、言葉が通じなくとも絵文字🤗で通じ合うことができます

日本が発祥の「絵文字」は、デザインの力で、人々のコミュニケーションの方法を変えたと、海外からも高く評価され、現代では多くの人が利用しています。LINEに代表されるスタンプも同様です。こえもじVRでは、絵文字の力をより拡張した、3Dモデルを用いたVR絵文字を、文字からではなく声から変換することで、コミュニケーションをさらに発展させることができると考えています。

Devpost  
https://devpost.com/software/tk_1615
    
### 特長
####1.自然な会話を交わすだけで、リアルタイムにものが現れる、魔法にかけられたVR空間
####2.スマートフォンで手軽にアクセスできる、最大20名接続可能オンラインプラットフォーム
####3.喋る向きや声量によって、動きや大きさなど、表現が変化する声の形
    

### 解決出来ること
* 伝達の齟齬の削減
* 伝達の高速化
* 感情表現の曖昧さの削減
* 議事録の手間の削減
* 他言語間コミュニケーション
* 外部センサなどのVR導入コストの削減（外部センサとの組み合わせも考えている）

### 今後の展望
* FacebookのVRアバターチャットやオンラインゲームに組み込み
* 動画・ゲーム画面などをVR空間上に表示
* スマートフォンに付属するカメラを用いて具象化したものとのインタラクション
* Photon voiceによる遠隔音声通話の導入
* 音声と一致するオブジェクトがない場合、gooのAPI等を用いて名詞を抽出、検索から呼び出しまでの実装

### 注力したこと（こだわり等）
* 会話に対するリアルタイム音声認識をスマートフォンで動くVR空間上に実現したこと
* オンラインでスマホ間のVR空間の同期を行なったこと
* 軽くする処理を実装して複数人接続を可能にしたこと
* 顔文字・手文字に対する日本語の表現の抽出
* オブジェクトの出現演出
* GitHubでのUnityのチーム管理（一番大変でした）


## 開発技術
### 活用した外部技術
#### API・データ
* iOS音声認識：Speech Recognition API
* iOS音量識別：AudioToolbox.framework
* スマートフォンVR：Google Cardboard
* iOS Emoji：http://punchdrunker.github.io/iOSEmoji/table_html/ios6/
* Asset Store - Unity：https://www.assetstore.unity3d.com/jp/

#### フレームワーク・ライブラリ・モジュール
* ゲームエンジン：Unity
* ネットワークエンジン：Photon
* IDE：Xcode

#### デバイス
* iPhone
* スマートフォン用3Dメガネ
* スマートフォン用ヘッドマウント3Dメガネ

### 独自技術
#### 期間中に開発した独自機能・技術
独自で開発したものの内容をこちらに記載してください
* iOSについて、先月から公開されたSiriに用いられている音声認識APIをUnityからObjective-Cを通して呼び出し、会話からリアルタイムにオブジェクトを出力するプラグインを自作。また、音声認識と並行して音量測定処理を走らせる処理を実装。
code：https://github.com/jphacks/TK_1615/blob/master/iOS/SpeechRecognizerModel.swift
* UnityVR化SDKとしてメジャーなGoogle Cardboardが、音声認識に必要なiOS10においてバグがあり動かず未解決とのことで、VR化をジャイロセンサなどを取得しつつ自作。自作した後、解決手法を発見したため、全世界の困っている人に伝達。

