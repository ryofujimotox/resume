# 職務経歴書

## 担当工程

上流工程から下流工程までを一貫して担当しています。<br>
基本的なチーム構成は営業、デザイナー、フロントCSS、バックエンド、QAの5名体制になります。

|<center>担当</center>|<center>技術</center>|<center>内容</center>|<center>目標/課題</center>|
|:---|:---|:---|:---|
|要件定義| | WEB会議に開発担当として同席します | 説明・提案力
|詳細設計| スライド | 画面遷移図を作成して確認を進めます<br>テキストベースで質問・回答を行います | 効率化
|DB設計| | 視認性・拡張性を意識してER図を作成します<br>規模感: 最大30テーブル、70万レコード<br>【その他】インデックス, view, trigger | DBチューニング<br>パーティショニング<br>レプリケーション
|インフラ|VPS, AWS<br>ロードバランサ<br>スケールアップ |OSからLAMP環境の構築<br>WAFやFail2banでのセキュリティ対策<br>Zabbixでのサービス監視 <br>【その他】LDAP, postfix, AWS-EC2 | CI/CD<br>AWS, GCP<br>Github Action
|バックエンド|PHP/CakePHP<br>Python | 規模感: 見積もり400万円 / 3ヶ月 | チーム開発<br>OSS開発/貢献<br>Node.js/Java
|フロントエンド|React| 使いやすさ・速度を重視します | SSG量<br>結合テスト
|アプリ開発|ReactNative|スムーズに動作するようメモリを意識します


### サーバー構築

VPS構築をメインに、AWS-EC2の構築や、LDAPサーバー構築、ロードバランサ構築等、幅広く携わりました。<br>
基本的にはマニュアル通りにLAMP環境+メールサーバー構築+セキュリティ対策を行います。<br>
CentOS6からCentOS7、AlmaLinuxへの移行を担当し、脆弱性対策とともにマニュアルの更新を行いました。<br>
サーバー構築に半日~夕方まで時間がかかっていたところ、スクリプトを作成し30分以下に短縮しました。<br>
直近ではビルド構築されていたWEBサーバーを改修し、PHPモジュール等を手動で導入しました。


### 開発

自社CMSの改修- 汎用的関数のライブラリ化

こだわりは、応答時間を0.8秒以下にすることです。<br>
処理を最適化した上で、改善が見込めない/難しい場合は他言語でも解決できないか模索します。<br>
その結果としてバックエンド部署に所属しながらもフロントエンドにも携わりました。

- 時間のかかるサブコンテンツは、Reactを導入し非同期に
- ダイアログ処理が多いサイトには、Reactを導入し手軽に
- 動画を流す際に負荷が高い場合は、Pythonを利用し編集処理



---
<div style="page-break-before:always"></div>




## プロジェクトまとめ

2ヶ月以上かかったプロジェクトの概要をまとめています。<br>
その他にも1週間~2ヶ月未満の案件(HP作成,サーバ構築)に数多く携わっております。<br>
わずかな待機時間には、自社開発、自社CMSの改修、スクリプト作成等に従事しております。

|<center>プロジェクト名</center>|<center>期間(目安)</center>|<center>金額(目安)</center>|<center>主な技術</center>|
|:---:|:---|:---|:---|
|サイネージアプリ|2022年12月~ 2ヶ月||CakePHP, ReactNative, Python
|教育支援システム|2022年06月~ 3ヶ月|400万円|CakePHP, React, 言語解析, AWS, Laravel
|内覧受付システム|2021年10月~ 2ヶ月|200万円|WordPress
|販促システム|2021年07月~ 2ヶ月|200万円|CakePHP, SMS, OCR, ロードバランサ
|学内システム|2021年03月~ 3ヶ月|300万円|CakePHP, LDAPS
|見積システム|2020年06月~ 3ヶ月||CakePHP, Backlog


---
<div style="page-break-before:always"></div>






## サイネージアプリ(2022-12~ 2ヶ月)

PHP管理画面でプレイリストを作成し、Android端末からモニタに出力するアプリ。<br>

### 特徴

自社開発, 5,000円のAndroid端末, モバイル開発


### 作業内容

|<center>内容</center>|<center>期間</center>|<center>技術</center>|<center>詳細</center>|
|:---|:---|:---|:---|
|詳細設計|約3日||- プレイリストコンテンツ内容の確認 (動画,画像,url,テキスト,,)<br/>- コンテンツ表示方法の確認 (表示間隔, モニタ向き,,)<br/>- 端末環境の確認 (端末スペック,通信環境,,)<br/>- 編集権限の確認 (本社と支店とそれぞれの関係)|
|DB設計|約1日||柔軟性を維持しながら管理者と店舗の権限を明確にすること|
|技術選定|約1日||- 端末の選定 (候補: シングルボードコンピュータか、Android端末)<br>- Android開発言語の選定 ( 候補: Kotlin,ReactNative,Cordova )<br>- 動画編集言語 ( Python )|
|サーバー構築|約30分|Apache,Bash|自作スクリプトを利用しVPS構築|
|開発-管理画面|約8日|CakePHP, Shell|DBに基づいた登録が可能であること<br>アプリの要求に正しくAPIを返すこと<br>動画処理の進捗状況が視覚的に確認できること|
|開発-アプリ開発|約5日|ReactNative|管理画面で登録したデータと連携ができること<br>プレイリストを正しく再生すること|
|開発-m3u8拡張子導入|約3日|PHP, FFmpeg|ライブ配信で使われている拡張子(m3u8)を利用する<br>クライアント側の読み込み速度を安定させること|
|開発-オフライン対応|約5日|ReactNative|プレイリストデータを外部ストレージに保存すること|
|開発-動画編集ツール|約4日|Python, MoviePy|プレイリストデータを1つの動画に変換すること|


### 業務での実績

**Android/ReactNativeの開発経験**

ストレージ操作の知識が深まり、同時にAndroid端末への苦手意識もなくなりました。

**m3u8の活用**

1秒単位で動画を分割することで、サーバー参照型の読み込みを安定化することができました。<br>
使用する場面は限定的ですが、貴重な経験を積むことができました。


**Pythonの開発経験**

サーバー側での動画編集処理を提案し、実現することができました。

---
<div style="page-break-before:always"></div>









## 教育支援システム(2022-06~ 4ヶ月)

課題に対する生徒の意見を形態素解析し、集計することが主な目的のシステム<br>

### 特徴

自然言語処理, React導入, アクセス権限

### 作業内容

|<center>内容</center>|<center>期間</center>|<center>技術</center>|<center>詳細</center>|
|:---|:---|:---|:---|
|詳細設計|||スライド|- クライアント提供の仕様書を読み認識をすり合わせる<br/>- 権限の確認(管理者, 学校, 先生, 生徒)<br>- 形態素解析の方法(MeCab)
|DB設計|約3日||クライアント提供の仕様書からDBを設計すること<br>不明な点は旧システムを参考にする|
|サーバー構築|約半日|AWS|VPSと同じ要領で構築する
|開発-API開発|約24日|CakePHP|DBに基づいた登録が可能であること<br>アプリの要求に正しくAPIを返すこと
|開発-形態素解析|約3日|MeCab|旧システムから処理方法が変わらないように構築すること<br>システム側から辞書の追加を行うこと
|開発-フロント開発|約15日|React|管理画面で登録したデータと連携ができること
|開発-関数の共通化|約5日|React|再利用可能なページネーション<br>編集後に戻る時のConfirm機能

### 業務での実績

**形態素解析**

形態素解析を学ぶことで、データ分析の実用性について再認識しました。<br>
お問い合わせから検索方法など、応用が効く機能だと考えています。


---
<div style="page-break-before:always"></div>









## 内覧受付システム(2021-10~ 2ヶ月)

スムーズな内覧受付機能を重視したホームページ<br>

### 特徴

WordPress, ブロックエディタの拡張, API開発

### 作業内容

|<center>内容</center>|<center>期間</center>|<center>技術</center>|<center>詳細</center>|
|:---|:---|:---|:---|
|設計|約1日||物件情報、部屋情報、お知らせ等<br/>カスタムフィールドによるリレーション対応
|サーバー構築|約30分|Bash|Bashスクリプトを利用し構築する
|開発-管理画面|約3日|WordPress|DBに基づいた登録が可能であること<br>登録のしやすい登録画面であること<br>
|開発-API開発|約3日|WordPress|フロント側の要求に正しくAPIを返すこと
|開発-多言語対応|約1日|WordPress|英語用の登録を可能にする
|開発-ブロックエディタの拡張|約2日|プラグイン|ブロックエディタのブロックを追加
|開発-カスタマイズ|約3日|プラグイン|お問い合わせとカスタムフィールドを連携させる<br>物件等の情報CSVをインポート・エクスポートする

### 業務での実績

これまでにもWordPressを実装してきましたが、<br>
データ登録の大変さ、集計方法、スピード面など、多くの面で悔いが残ってしまいました。<br>



**多言語化**

1つの物件に対する項目量が多いため、日本語の枠の隣に英語用の枠を用意するのではなく、<br>
英語用のサイトとして、サイトごと複製することが最善の策だと判断し実装しました。<br>
今思えば、DeepLのAPIで自動翻訳する策も視野に入れるべきだったと思います。

**CSVインポート・エクスポート**

WPの制限が多いものの、通常のCMSと同じようにインポート対応しました。<br>
実装時はCSVが前提にあったので画像のインポートは実用的ではないと考えていましたが、<br>
ZIP形式なら対応できるのではないかと思います。

**API連携**

REST APIを使う際のフロントエンド部署との連携の難しさと、実装した時の使いやすさを再認識しました。<br>
フロントエンドとの連携を深めるためにも、可読性の高いAPI設計書(Swagger)を作成することと、自分自身Reactを学ぶことを決めました。

---
<div style="page-break-before:always"></div>










## 販促システム(2021-07~ 2ヶ月)

抽選を行いキャッシュバックを約束することで、購買意欲を高めることを目的とするシステム<br>

### 特徴

SMS, OCR, ロードバランサ, rsync

### 作業内容

|<center>内容</center>|<center>期間</center>|<center>技術</center>|<center>詳細</center>|
|:---|:---|:---|:---|
|詳細設計|約4日||キャンペーンごとに複製することを考慮する
|DB設計|約2日||キャンペーンごとに複製することを考慮する<br>
|選定|約2日||SMS会社<br>OCR会社
|サーバー構築|約1日|Bash|Bashスクリプトを利用し構築する<br>2つのサーバーをロードバランサを組む<br>振り分け先の2つサーバーをrsync同期させる
|開発-管理画面|約20日|CakePHP, crontab|DBに基づいた登録が可能であること<br>登録のしやすい登録画面であること<br>crontabによるスケジュール処理
|開発-SMS|約3日|SMS|応募時・登録時・結果発表全てにSMSを用いる<br>管理画面からのCSV送信にも対応すること<br>未着時にコールバックを行う
|開発-OCR|約3日|OCR|レシートをOCRで読み込み、目視での作業の簡略化を図る
|開発-フロント|約3日||外部フロントエンジニアとの連携

### 業務での実績

**ロードバランサ**

全国規模で一斉に応募されることが想定されるため、ロードバランサを使って負荷を分散しました。<br>
振り分け先のサーバ間をrsyncで同期させることで経験・技術も身につきました。

**SMS**

不正抽選を防ぐための認証および景品の送信のためにSMSを利用しました。 <br>
到着率が課題となるため多用はできませんがいい経験です。<br>

**OCR**

目視で行う購入確認作業を簡略化しました。<br>
確認する項目が絞り込まれるだけでも効率的になったかと思います。


---
<div style="page-break-before:always"></div>















## 学内システム(2021-03~ 4ヶ月)

教職員と学生(約10,000人)へページを共有するシステム。<br>

### 特徴

LDAPS, リッチエディタ, アクセス権限, 70万レコード, 20テーブル

### 作業内容

|<center>内容</center>|<center>期間</center>|<center>技術</center>|<center>詳細</center>|
|:---|:---|:---|:---|
|詳細設計|約3日||用意された仕様書を読み認識をすり合わせる
|DB設計|約3日||リッチエディタ登録ができること<br>あらゆるテーブルにユーザー権限を付与すること<br>あらゆる操作のログを残すこと<br>複数のページ種別/スラッグ対応
|サーバー構築|約30分|Bash|Bashスクリプトを利用し構築する
|開発-管理画面|約15日|CakePHP|DBに基づいた登録が可能であること<br>登録のしやすい登録画面であること
|開発-記事入力画面|約8日|JS|WPのようなリッチエディタを実装すること<br>それをHTMLとして出力すること
|開発-LDAP連携|約5日|LDAP|アカウントはLDAPから取得すること<br>テスト用のLDAPサーバーを構築すること
|開発-通知処理|約3日|CakePHP|ページ追加・更新・削除時に通知を行うこと
|開発-フロント|約10日||登録した内容を正しく表示すること

### 業務での実績

**WPのようなリッチエディタ開発**

WPのリッチエディタを再現しました。<br>
より複雑なページ構成、コンテンツごとのオプションにも柔軟に対応できるようになりました。


**複雑な権限管理**

ほぼ全てのテーブルに権限を付与することになったので権限確認が大変でした。<br>
緊張感を持ち無事に実装を終えることができました。


**LDAP利用**

複数システムにわたるアカウント情報をLDAPにて一元管理しました。<br>
LDAPの挙動を把握するため、別途LDAPS環境を構築しました。


---
<div style="page-break-before:always"></div>











## 見積システム(2020-06~ 3ヶ月)

業務の効率化、見積案件の整理、それらに紐づく実動工数の可視化を図るシステム。<br>
入社して間もない頃に開発したシステムですが、多くのスタッフに利用されておりいいものを作れたと実感しています。


### 特徴

自社開発, Backlog, PDF生成, SSL監視, React導入

### 業務での実績

**PDF生成**

見積書・請求書の自動生成を実装しました。<br>
様々なフォーマットを用意することで書類作成作業を簡略化しました。


**BacklogのAPI利用**

タスク管理に利用していたBacklogと連携させることで、案件ごとの実動工数を算出しました。<br>
Backlogに限らずツールのAPIを活用することで、タスク管理、実働工数、スケジュール管理を一元的に管理したいと考えました。


**サイトデータのシステム管理**

システム上でサイトを登録し、SSLの有効期限を監視します。<br>
エクセルやWikiでまとめていたところをシステムに組み込むことで、スクリプトでの一括確認が可能になりました。


---

