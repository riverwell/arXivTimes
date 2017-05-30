# Tools

機械学習モデルの実装を行う際に役立つツールについてまとめています。  
なお、深層学習系のフレームワーク(TensorFlow/Chainerなど・・・)は既知だと思うので、その当たりは除外しています。

# Vision

* [OpenFace](https://cmusatyalab.github.io/openface/)
  * 画像から顔を認識し、128次元の特徴量を算出するツール。この特徴を利用し、独自の分類機などを作ることができる。
  * 顔の検知には、OpenCV/dlibを使用
  * Apache 2.0 License
* [openpose](https://github.com/CMU-Perceptual-Computing-Lab/openpose)
  * 体のキーポイント(関節など)を検知するためのライブラリ
  * OpenCV/Caffeベース
  * ライセンスは独自のもので、商用利用については応相談
* [self-driving-car](https://github.com/udacity/self-driving-car/)
  * Udacityで自動運転車の講座が開講されるに伴い公開された、オープンソースの自動運転車の実装
  * 他の公開されている実装としては、[comma.ai](https://github.com/commaai/research)の実装などがある。

# NLP

* [NLTK](http://www.nltk.org/)
  * 形態素解析や品詞タグ認識など、自然言語処理に関する基礎的な処理を行うライブラリ。微妙に日本語にも対応している。
* [spaCy](https://spacy.io/)
  * NLTKど同様だが、固有表現抽出などの機能も搭載している
  * 最大のポイントとしてはエンタープライズでの利用を想定しており、マルチスレッドを用い高速に動作するよう設計されている
* [Stanford CoreNLP](https://stanfordnlp.github.io/CoreNLP/)
  * Stanfordが提供する自然言語処理のライブラリ。基礎的なライブラリでできることは網羅されており、照応表現(彼=○○さん、とか)の解釈や、構文解析結果を利用した処理なども可能(名詞を対象にｘｘするなど)
  * 多様なプログラミング言語へのインタフェースを持つことも特徴で、[ClojureやErlang/Elixirなどまでサポートされている](https://stanfordnlp.github.io/CoreNLP/other-languages.html)
  * なお、CoreNLPも含めたStanfordが開発しているツールは[Stanford NLP Software](https://nlp.stanford.edu/software/)にまとまっている。自然言語系で何かないかなと思ったら、まず目を通してみると良い。
* [ParlAI](https://github.com/facebookresearch/ParlAI)
  * Facebookが発表した、対話モデルを開発するためのフレームワーク。
  * SQuADやbAbI、Ubuntu Dialogなど有名な質問応答/対話系のデータセットが簡単に扱えるようになっている
  * モデル評価のためにAmazon Mechanical Turkとの連携も兼ね備えるなど、対話研究を行うならとても便利なフレームワークになっている。
* [NeuroNER](http://neuroner.com/)
  * TensorFlowベースの固有表現抽出ツール。学習済みモデルが利用できるほか、追加データによる学習も可能。
* [chazutsu](https://github.com/chakki-works/chazutsu)
  * 自然言語関係のデータセットを簡単にダウンロードし、使えるようにできるツール
  * データをダウンロード、展開して、整形して・・・という作業は以外と時間がかかるもので、その個所をスキップできる
* [chakin](https://github.com/chakki-works/chakin)
  * 単語の分散表現を簡単にダウンロードできるツール。こちらも探してくるのが面倒なので、これを利用すれば簡単に利用できる。


**Additional**

* [日本語自動品詞分解ツール](http://tool.konisimple.net/text/hinshi_keitaiso)
  * オンラインでさっと品詞分解ができるツール。手軽なのでよく使う

# Audio

* [Magenta](https://github.com/tensorflow/magenta)
  * Googleが開発を進める、機械学習をアートに適用するためのプロジェクト。音楽生成や、スタイルトランスファーなどのコードが組み込まれている
  * 特に音声系では、MIDIファイルを扱うためのAPIなども提供されているので、単純にデモを動かすだけでなく開発のベースとしても利用ができる。
* [librosa](https://github.com/librosa/librosa)
  * 音声データを読み込み、特徴量(MFCCなど)を算出するなどを行ってくれるライブラリ。tempoの推定なども行える。


# Reinforcement Learning

* [OpenAI Gym](https://gym.openai.com/)
  * 強化学習モデルのトレーニング環境を提供するフレームワーク
  * OpenAI Gym自体にも多くの環境(Atariのゲーム)などが入っているが、Open AI GymのAPIを備えたサードパーティー製の環境も追加でインストールできる([gym_pull](https://github.com/openai/gym/wiki/Environments#gym_pull)参照)。
* [malmo](https://github.com/Microsoft/malmo)
  * 協調するマルチエージェントの学習に特化した学習プラットフォーム。
  * Microsoftが公開しており、Minecraftの上で動く
  * Python、Lua、C#、C++、Javaなど多様なインタフェースを持つ

# Others

## Annotation Tool

* [visdial-amt-chat](https://github.com/batra-mlp-lab/visdial-amt-chat)
  * 画像に関する質問＋回答のデータを収集するためのアプリケーション。[実際のアプリケーション開発](https://visualdialog.org/)に使用したものを公開してくれている

## DataAPI

* [pandas](http://pandas.pydata.org/)
  * 表形式データを扱いやすくるためのツール。描画機能も付属しているため、簡単なグラフならpandasのみでかなりいける([こちら](http://pbpython.com/effective-matplotlib.html)参照)。
* [feather](https://github.com/wesm/feather)
  * 様々なプラットフォーム(Python/pandas、Rなど)で共通して扱え、なおかつ高速性を担保するデータフレームのファイルフォーマット、およびそれを扱うツール
  * いったんfeather形式のファイルフォーマットで保存し、それを読み込む形になる。この操作は特にメモリに乗らないような大規模なデータセットで力を発揮し、デモでは600MBのファイルを1秒たらずで読み込めている([Feather: A Fast On-Disk Format for Data Frames for R and Python, powered by Apache Arrow](https://blog.rstudio.org/2016/03/29/feather/))。

## Visualization

* [bokeh](http://bokeh.pydata.org/en/latest/)
  * Pythonのグラフ描画ツールで、描画結果からHTMLコンテンツの作成が可能。このため、Jupyter上で使うほかWebページに埋め込んだりすることもできる
* [seaborn](https://seaborn.pydata.org/)
  * Matplotlib上で稼働し、より使いやすく、きれいに描画できる
* [HyperTools](http://hypertools.readthedocs.io/en/latest/)
  * 高次元のデータの可視化に特化したツール
* [Picasso](https://medium.com/merantix/picasso-a-free-open-source-visualizer-for-cnns-d8ed3a35cfc5)
  * CNNの層を可視化するためのツール。Keras/TensorFlowのチェックポイントファイルをベースに動く。

## Official Implementation

ベースラインとして利用できるような、オフィシャルの実装を紹介します。

* [OpenAI Baselines](https://github.com/openai/baselines)
* [Memory-Augmented Neural Networks](https://github.com/facebook/MemNN)
* [Neural-Dialogue-Generation](https://github.com/jiweil/Neural-Dialogue-Generation)
* [PixelCNN++](https://github.com/openai/pixel-cnn)