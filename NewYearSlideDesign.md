「AIで描く2026年の私！ 新春スライドデザイン講座」Webサイト要件定義書

1. サイト概要

本サイトは、GEG Asahikawa（Google Educator Group Asahikawa）が主催する、教職員向けの生成AI活用（スライドデザイン）講座のための特設ランディングページ（LP）およびハンズオン用ポータルサイトである。

1.1 目的

脱・スライド職人: 教師が時間をかけずに、AI（Gemini, NotebookLM）を活用して質の高いスライドを作成する方法を啓蒙する。

ビジョンの可視化: 言葉だけでなく、ビジュアルを用いて「未来」や「抱負」を語る重要性を伝える。

ハンズオン支援: ワークショップ当日に参加者がスムーズに作業できるよう、プロンプトのコピーやツールへのアクセスを集約する。

1.2 ターゲットユーザー

学校教職員

教育ICTに関心のある教育関係者

2. サイト構成・機能要件

2.1 サイト構造

SPA（Single Page Application）ライクな挙動を持つ、1ページ完結型のWebサイト。JavaScriptによりDOMの表示/非表示を切り替えることで、ページ遷移なしにコンテンツを展開する。

画面構成:

Header (Global Navigation)

常に画面上部に追従（Sticky）。

4つのメインビューへの切り替えボタン（Home, Prompts, ハンズオン, 学校活用）。

Main Content Area

Home View: トップページ。コンセプト、ワークフロー、メニュー。

Prompts View: 画像生成プロンプト集、テクニック紹介、Before/After比較。

Handson View: ワークショップの手順ガイド、ツールリンク、実践フロー。

Cases View: 学校現場での具体的な活用事例集。

Footer

著作権表示、SNSリンク（LINE OpenChat, Facebook, Instagram）。

2.2 機能要件

View Transition (画面遷移):

ナビゲーションクリック時に、ブラウザの View Transition API またはCSSアニメーションを用いて、コンテンツがフェードイン・スライドアップするリッチな遷移を行う。

Scroll Reveal (スクロール連動表示):

スクロールに合わせて要素が下からふわっと浮き上がり、ピントが合うようなアニメーション（IntersectionObserver 使用）。

Copy to Clipboard (クリップボードコピー):

プロンプトコードブロックやテキストエリアをクリックすると、内容をクリップボードにコピーし、画面下部に「トースト通知」を表示する。

External Links:

Gemini, NotebookLM, Google Slides等の外部ツールへ新しいタブで遷移する。

3. デザイン・UI/UX要件

3.1 デザインコンセプト

"Ultra-Glassmorphism & Fluid Physics"
（極上のガラス質感と、物理演算のような滑らかな動き）

脱・絵文字 (No Emoji): 絵文字を一切使用せず、モダンなベクターアイコン（Lucide Icons）を採用し、洗練されたプロフェッショナルな印象を与える。

没入感 (Immersion): 背景に淡く動くオーロラのようなグラデーションメッシュを配置し、空間の奥行きを演出。

3.2 カラーパレット (Google Colors Refined)

Googleブランドカラーをベースにしつつ、目に優しく高級感のあるトーンに調整。

Primary Blue: #4285F4 (知性、NotebookLM)

Primary Red: #EA4335 (情熱、Gemini)

Primary Yellow: #FBBC04 (注意、ハイライト)

Primary Green: #34A853 (成長、Google Sheets/Classroom)

Background:

Base: #FFFFFF

Secondary: #F8F9FB (薄いグレー)

Glass: rgba(255, 255, 255, 0.65) + backdrop-filter: blur(20px)

3.3 タイポグラフィ

欧文: 'Outfit' (モダンで幾何学的、親しみやすいサンセリフ体)

和文: 'Noto Sans JP' (可読性の高いゴシック体)

ウェイト: 300(Light), 400(Regular), 600(SemiBold), 800(ExtraBold) を使い分け、メリハリをつける。

3.4 アニメーション・インタラクション

Easing (イージング): cubic-bezier(0.16, 1, 0.3, 1) を多用。初速が速く、停止直前に粘り気のある「ぬるっ」とした慣性動作を実現。

Hover Effects:

カードやボタンはホバー時に「浮き上がる（TranslateY）」かつ「光沢が走る（Box-shadow/Border）」演出。

物理的な手触りを感じさせるマイクロインタラクション。

4. コンテンツ詳細要件

4.1 Home View

Hero Section: イベントタイトル、サブタイトル、主催者バッジ。

Workflow: 生成AI活用における3つの視点（Audience, Teachers, Future）をカードで提示。

Tips: 構成、言葉、配色に関するプロの技術とAI活用のメリット（Pain/Gain）。

Contents Menu: 各詳細ページへの大きなナビゲーションカード。

4.2 Prompts View (プロンプト工場)

Prompt Dictionary: 「画風」「カメラ・構図」「照明・雰囲気」の3カテゴリで、コピー可能なプロンプト部品（呪文）をリスト化。

Hacks: スライドデザイン特化のプロンプトテクニック（余白作成、文字なし指定など）。

Comparison Demo: 「走っている先生」をテーマに、普通のプロンプトと工夫したプロンプトの生成結果の違いを比較解説。

4.3 Handson View (ハンズオン会場)

Goal: 「1年の抱負をインフォグラフィックにする」というゴールの提示。

Timeline: 4ステップ（Think, Prompt, Generate, Design）の時間配分と流れ。

Step 1 & 2 (Gemini): 抱負を言語化し、プロンプトを作成するためのテンプレートプロンプト（コピー可）。

Step 3 (Generation):

Gemini: 想像力重視（0→1）の生成。リンクボタンあり。

NotebookLM: 文脈分析重視（資料→画像）の生成。リンクボタンあり。

Step 4 (Finish): Googleスライドへの貼り付け手順と、共有スライドへのリンクボタン。

4.4 Cases View (学校現場での活用)

Hero Case: 「学校評価アンケート」をインフォグラフィック化する事例を大きく紹介。

校務編: 職員会議（要約）、全校集会（注意喚起）、保護者会（経営方針）での活用例。

授業編: 導入（ゴール可視化）、展開（概念図解）、深掘り（AIディベート）での活用例。

スライド生成の極意: 「16:9の指定」「文字は後乗せ」「原稿作成」の3大原則を強調表示。

5. 技術スタック要件

HTML5: セマンティックなマークアップ。

CSS3:

CSS Variables（変数）による一括色管理。

Flexbox / CSS Grid によるレスポンシブレイアウト。

backdrop-filter によるすりガラス表現。

JavaScript (Vanilla):

IntersectionObserver API（スクロール検知）。

View Transition API（画面遷移アニメーション）。

DOM操作による表示切り替え。

External Libraries:

Lucide Icons: アイコン表示用（スクリプト読み込み）。

Google Fonts: フォント読み込み。

6. 特記事項・制約

レスポンシブ対応: PC、タブレット、スマートフォン（縦・横）のいずれでも崩れず、美しく表示されること。特にモバイル時はナビゲーションが横スクロール可能になるなどの最適化を行う。

パフォーマンス: 画像は遅延読み込みや軽量化を意識し（プレースホルダー等）、アニメーションがFPSを落とさない