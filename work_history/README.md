# 職務経歴書

## サイネージアプリ(2022-12~ 2ヶ月)

### プロジェクト概要

管理画面にてプレイリストを作成し、Android端末を通してモニタに出力し続けるアプリです。
主にフランチャイズ経営の飲食店や多数の店舗を抱えるショッピングモール向けに販売を目的としたサービスになります。

- **プロジェクトカテゴリ:**
    - WEBサービス, スマホアプリ, 自社プロダクト, パッケージ開発
- **担当工程:** 
    - 要件定義, 設計, コーディング, テスト, 運用/保守
- **経験した職種・役割:**
    - フロントエンド, バックエンド, インフラ, アプリ開発(Android)
- **使っていた技術:**
    - PHP, CakePHP, ReactNative, Python, Apache, MySQL
- **チーム情報:**
    - 実装 x1名 (自分)
    - 端末選定 x1名

### 機能まとめ

- **要件定義**
    - コンテンツ内容の確認 (動画,画像,url,テキスト,,)
    - コンテンツ表示方法の確認 (表示間隔, モニタ向き,,)
    - 端末環境の確認 (端末スペック,通信環境,,)
    - 編集権限の確認 (本社と支店とそれぞれの関係)
- **技術選定**
    - 端末の選定 (候補: シングルボードコンピュータか、Android端末)
    - Android開発言語の選定 ( 候補: Kotlin,ReactNative,Cordova )
    - 動画編集言語 ( Python )
- **DB設計**
    ```
    管理者 -< 店舗 -< 端末 - プレイリスト -<
    ```
- **サーバー構築**
    - マニュアルに従ってサーバーを構築します
    - 既にサーバー構築を自動化するためのスクリプトを自作しているため、作業負担はほぼありません。

### 実装内容

1. 管理画面の開発 (CakePHP)
    設計したDBに沿うように登録画面を実装しました。
    - **使用した技術:**
        - CakePHP, Shell
    - **フロントサイドのカスタマイズ**
        - テンプレートにある程度用意されていますが、次の2点を追加しました。
        - 直感的に操作できるリスト形式の入れ替え機能
        - 動画編集処理の進捗状況が可視化されるようプログレスバー



#### プレイリスト拡張子の利用(m3u8)

ライブ配信で使われている拡張子(m3u8)を利用し、クライアント側の読み込み速度を安定させました。

- **使用した技術:**
    - ReactNative, FFmpeg
- **実装目的:**
    - 動画のサイズが大きいと読み込む待機時間が発生しました。
      1つだけでも裏で読み込もうとすると、字幕がカクつき、メモリが耐えきれなくなります。
      そのため1動画のサイズを減らすことで対策しました。
- **成果**
    - 大きい動画ファイルを定期的に読み込む時と比べると、安定して読み込むことができます。
- **課題**
    - 一見問題ないように見えましたが、やはり負担が大きいです。
      CDNを利用していないためサーバー側の負担も計り知れません。


#### プレイリストのオフライン対応 (ReactNative)

APIで取得したプレイリストのデータ・データ構造を外部ストレージに保存します。

- **使用した技術:**
    - ReactNative, react-native-fs
- **実装目的:**
    - クライアントのさまざまな環境を考慮し、通信環境に依存しない機能が必要でした。
- **課題・問題点**
    - 基本的なコンテンツ表示に使われる`import`に変数が利用できない事実に躓きました。
      バイナリ型としてローカル保存することも考えましたが、
      コンテンツデータを外部ストレージに保存することで実現しました。

#### プレイリストの統合処理 (Python)

サーバー側で、プレイリスト内のすべてのコンテンツを1つの動画に変換するツールです。

- **使用した技術:**
    - Python, MoviePy
- **実装目的:**
    - コンテンツの切り替えや字幕を流す処理はクライアントのスペックに依存するため、
      安直ではありますがサーバー側で1つの動画に変換することにしました。
      多少なりともクライアント側の負荷を減らすことが目的です。
- **成果**
    - クライアント側の負担を大きく減らすことができました。
      責任を分散することでテストも容易になりました。
      (動画が構成されていない時はPython側、想定通りに表示されないときはReact側)


### 成果

#### ReactNative,Androidの開発経験

画像はimportするもので、importは変数を利用できないという固定概念が変わりました。
Android端末への苦手意識もなくなり、どんどん活用していきたいと考えています。


#### Pythonの開発経験

端末のスペックによるものだから暗転状態が発生するのは仕方がないと諦めず、
サーバー側での動画編集処理を提案し、実現することができました。
このような技術的な課題を解決するには、フルスタックの経験と技術が重要だと感じました。






























---

## 業務外活動

### OSS・個人開発活動

#### 主要リポジトリ

<table>
  <thead>
    <tr>
      <td><b>Projects</b></td>
      <td><b>Lang / FW</b></td>
      <td><b>Stars</b></td>
      <td><b>Forks</b></td>
      <td><b>Issues</b></td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://github.com/kawamataryo/chikamichi"><b>Chikamichi</b></a></td>
      <td><img alt="TypeScript" src="https://img.shields.io/badge/-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="Vue" src="https://img.shields.io/badge/-4FC08D?style=flat-square&logo=Vue.js&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/chikamichi?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/chikamichi?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/chikamichi?style=flat-square&labelColor=343b41"/></td>
    </tr>
    <tr>
      <td><a href="https://github.com/kawamataryo/vue-word-highlighter"><b>Vue Word Highlighter</b></a></td>
      <td><img alt="TypeScript" src="https://img.shields.io/badge/-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="Vue" src="https://img.shields.io/badge/-4FC08D?style=flat-square&logo=Vue.js&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/vue-word-highlighter?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/vue-word-highlighter?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/vue-word-highlighter?style=flat-square&labelColor=343b41"/></td>
    </tr>
    <tr>
      <td><a href="https://github.com/kawamataryo/vue-word-highlighter"><b>suppress ts errors</b></a></td>
      <td><img alt="TypeScript" src="https://img.shields.io/badge/-007ACC?style=flat-square&logo=typescript&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/suppress-ts-errors?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/suppress-ts-errors?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/suppress-ts-errors?style=flat-square&labelColor=343b41"/></td>
    </tr>
    <tr>
      <td><a href="https://github.com/kawamataryo/github-trending-bot"><b>GitHub Trending Bot</b></a></td>
      <td><img alt="TypeScript" src="https://img.shields.io/badge/-007ACC?style=flat-square&logo=typescript&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/github-trending-bot?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/github-trending-bot?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/github-trending-bot?style=flat-square&labelColor=343b41"/></td>
    </tr>
    <tr>
      <td><a href="https://github.com/kawamataryo/sync-raise-hand"><b>Sync Raise hand</b></a></td>
      <td><img alt="TypeScript" src="https://img.shields.io/badge/-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="Vue" src="https://img.shields.io/badge/-4FC08D?style=flat-square&logo=Vue.js&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/sync-raise-hand?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/sync-raise-hand?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/sync-raise-hand?style=flat-square&labelColor=343b41"/></td>
    </tr>
    <tr>
      <td><a href="https://github.com/kawamataryo/v-change-tags-order"><b>V Change Tags Order</b></a></td>
      <td><img alt="TypeScript" src="https://img.shields.io/badge/-007ACC?style=flat-square&logo=typescript&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/v-change-tags-order?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/v-change-tags-order?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/v-change-tags-order?style=flat-square&labelColor=343b41"/></td>
    </tr>
    <tr>
      <td><a href="https://github.com/kawamataryo/animated-emoji-gen"><b>Animated emoji gen</b></a></td>
      <td><img alt="TypeScript" src="https://img.shields.io/badge/-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="Vue" src="https://img.shields.io/badge/-4FC08D?style=flat-square&logo=Vue.js&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/animated-emoji-gen?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/animated-emoji-gen?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/animated-emoji-gen?style=flat-square&labelColor=343b41"/></td>
    </tr>
	  <tr>
      <td><a href="https://github.com/kawamataryo/copy-python-path"><b>Copy Python Path</b></a></td>
      <td><img alt="Python" src="https://img.shields.io/badge/-3776AB?style=flat-square&logo=Python&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/copy-python-path?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/copy-python-path?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/copy-python-path?style=flat-square&labelColor=343b41"/></td>
    </tr>
	  <tr>
      <td><a href="https://github.com/kawamataryo/alfred-imagemin"><b>Alfred Imagemin</b></a></td>
      <td><img alt="JavaScript" src="https://img.shields.io/badge/-F7DF1E?style=flat-square&logo=JavaScript&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/alfred-imagemin?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/alfred-imagemin?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/alfred-imagemin?style=flat-square&labelColor=343b41"/></td>
    </tr>
    <tr>
      <td><a href="https://github.com/kawamataryo/tell-me-bot"><b>Tell me bot</b></a></td>
      <td><img alt="TypeScript" src="https://img.shields.io/badge/-007ACC?style=flat-square&logo=typescript&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/tell-me-bot?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/tell-me-bot?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/tell-me-bot?style=flat-square&labelColor=343b41"/></td>
    </tr>
	  <tr>
      <td><a href="https://github.com/kawamataryo/copy-git-link"><b>copy-git-link</b></a></td>
      <td><img alt="Kotlin" src="https://img.shields.io/badge/-0095D5?style=flat-square&logo=Kotlin&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/copy-git-link?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/copy-git-link?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/copy-git-link?style=flat-square&labelColor=343b41"/></td>
    </tr>
	  <tr>
      <td><a href="https://github.com/kawamataryo/schema2type"><b>Schema2type</b></a></td>
      <td><img alt="Ruby" src="https://img.shields.io/badge/-CC342D?style=flat-square&logo=Ruby&logoColor=white" /></td>
      <td><img alt="Stars" src="https://img.shields.io/github/stars/kawamataryo/schema2type?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Forks" src="https://img.shields.io/github/forks/kawamataryo/schema2type?style=flat-square&labelColor=343b41"/></td>
      <td><img alt="Issues" src="https://img.shields.io/github/issues/kawamataryo/schema2type?style=flat-square&labelColor=343b41"/></td>
    </tr>
  </tbody>
</table>

#### その他
- **type-challenges のメンバー（日本語ローカライズを担当）**
    - [type-challenges](https://github.com/type-challenges/type-challenges)
- **OSS への PR 作成**
    - Raycast 拡張機能の開発
      - [TinyPNG](https://www.raycast.com/kawamataryo/tinypng)
      - [esa Search](https://www.raycast.com/kawamataryo/esa-search)
    - Hasura Console の TypeScript 化・Issue の対応
    - Gatsby.js の TypeScript 化・ドキュメント翻訳
    - Vue3 のドキュメント翻訳

### 副業

- **鍼灸院専門の Web デザイン事業**
    - 担当：営業・企画・デザイン・実装
    - 使用技術：PHP, JavaScript, WordPress, Nuxt.js, GraphCMS
    - 妻の仕事（鍼灸師）のホームページを作成したことでスタート。口コミ、web サイト経由で受注。契約交渉から実装・保守管理まですべてを行う
- **ソフトウェア受託開発**
    - 担当：実装
    - 使用技術：JavaScript, TypeScript, Vue.js, React, Firebase
    - 元同僚が起業した会社の受託開発業務のサポート。フロントエンドの実装を主に行う

### 技術記事投稿

- **Zenn**
    - サービススタートから投稿を開始。2022/10 現在 88 記事、 5,500LIKE
    - [https://zenn.dev/ryo_kawamata](https://zenn.dev/ryo_kawamata)
- **Qiita**
    - 消防士時代から投稿を続け 2022/10 現在、143 記事、 17,551LGTM
    - [https://qiita.com/ryo2132](https://qiita.com/ryo2132)
- **note**
    - 主に月報を記載。2020/04 現在 , 23 記事、 1,068 いいね
    - [https://note.com/ryo_kawamata](https://note.com/ryo_kawamata)

### 勉強会での登壇

- **Frontend LT 回（2022/06/15）**
  - [suppress-ts-errors を使って TypeScriptの型チェックを漸進的に強化する](https://speakerdeck.com/kawamataryo/introducing-suppress-ts-errors)
- **iCARE Dev Meetup (2022/04/20）**
  - [OSS活動ことはじめ 〜OSS活動への壁と乗り越え方〜](https://speakerdeck.com/kawamataryo/begin-oss-activities)
- **ジャムジャム Jamstack!!（2021/09/30）**
  - [esa + VuePress で Jamstack なドキュメントサイトを作る](https://speakerdeck.com/kawamataryo/build-jamstack-site-with-vuepress-and-esa)
- **iCARE Dev Meetup（2021/03/17）**
  - [Vue.js 状態管理の選択肢 - その Vuex 本当に必要ですか -](https://speakerdeck.com/kawamataryo/vue-dot-js-state-management-options)
- **Remote.vue（2020/07）**
  - [Ref vs Reactive Vue3 Composition API のリアクティブ関数の探究](https://speakerdeck.com/kawamataryo/ref-vs-reactive-vue-composition-api-deep-in)
- **もくテク（2019/12）**
  - [入門 Hasura](https://speakerdeck.com/kawamataryo/ru-men-hasura)
- **もくテク（2019/10）**
  - [ここまで出来るよ Firestore セキュリティルール](https://speakerdeck.com/kawamataryo/kokomadechu-lai-ruyo-firestore-sekiyuriteiruru)
- **他登壇資料**
  - [https://speakerdeck.com/kawamataryo](https://speakerdeck.com/kawamataryo)

### 勉強会の開催

- **茨城県水戸市にて勉強会を企画・運営**
    - 水戸エンジニア勉強会（開催回数 37 回、 メンバー 86 人）
    - [https://mito-web-engineer.connpass.com/](https://mito-web-engineer.connpass.com/)
- **社内・社外勉強会の企画・運営**
    - もくテク powerd by Misoca
    - フロントエンド輪読回（Vue Composition API ドキュメント , JavaScript Promise の本輪読回、 Jest 公式ドキュメント、 TypeScript 公式ドキュメント）
    - Go ではじめるインタプリタ輪読回

### その他

- **Podcast**
  - [しがないラジオ sp.91【ゲスト: KawamataRyo】楽しい元消防士がエンジニア転職を決意した理由、そして挫折と復活](https://shiganai.org/ep/sp91-KawamataRyo)
- **YouTube**
  - [消防士からエンジニアへ（ゲスト：川俣さん） #エンジニアと人生 Vol.28](https://www.youtube.com/watch?v=bP8hTmGixuI&t=1587s)

---

## 意欲・興味
- 少人数チームで小さく早くリリースし、フィードバックを受けながら改善のサイクルを回していくアジャイルな開発スタイルを好みます
- フロントエンドだけではなくバックエンド・インフラなど新しい分野・技術への興味関心が強く、学習しながらアウトプットをすることが得意です
- ペアプロ・モブプロを積極的に取り入れ、チームで暗黙知の共有や、技術の継承を行っていきたいと思っています
- 開発に携わったサービスが、身近な人の生活をより良くしていく過程を肌で感じられる時、時間を忘れてそれに没頭します

---

## 希望条件
- 地方在住なのでフルリモートワークでの勤務を希望します（月数回の出社等は可）
- ユーザーファーストなプロダクトを作っていく過程が好きです。言われたとおりにただ作るのではなく、機能要件に対しても一緒に考えていけるチームだと良いです
- 新しい挑戦（技術的なもの・制度的なもの）に積極的に取り組める環境が好きです
