
# re:Invent 2022 re:Cap 1st Night

## お気持ち

- 亀田さんによる、毎日アップデート紹介
  - [こちら](https://awsbasics.connpass.com/event/265644/)
  - ほんとありがとうございます。
  - 最後にまとめてだと、脳みそが追いつかないのです
- 手を動かして確認したいと思ったもの
  - Amazon CodeWhisperer
  - AWS CloudWatch Internet Monitor
  - AWS Backup -CloudFormation stack
  - Amazon Verified Permission
  - AWS CloudTrail Lake / AWS config integration

## 次回はこちら

- [re:Invent 2022 re:Cap 2nd Night](https://awsbasics.connpass.com/event/265645/)
  - 参加できなくなったらちゃんとキャンセルしましょうね（自戒も込めて）
  - 私は参加できないので、誰かのアウトプットに期待です！！
  
## Amazon CodeWhisperer: ML-powered coding companion

- 一般提供が開始された
- コーディングの補助をしてくれるサービス
- C#とTypeScriptが追加された
- 認証方式がIAM Identity Center 経由に変更

## Amazon RDS Optimized Reads/Writes for  MySQL

- Reads
  - クエリ処理の高速化を実現
  - ソート、ハッシュアグリゲーション、甲府かジョイン、Common Table Expressions を含む一時テーブルを含むものが対象
  - 50％高速化
  - 新しいものが対象
- Writes
  - 16Kibバッファーを4Kibチャンクで書き込んでいたものを16Kibに統一して書き込み
  - 新しいものだけ、db.r5b or db.r6i など

## Amazon RDS Blue/Green Deployment

- わずかな手順で本番環境をミラーリング
- 同期されたステージング環境を個別に作成可能

## AWS IoT Core Device Location

- 消費電力の大きいGPSの代替
- さまざまな方法を合わせて使って、デバイスの地理座標を決定
  - セルラー三角測量があるということは、クラウド側だけではなく、デバイス側の情報と合わせて実現しているアップデート
- Device Shadow で位置を管理
- Location Service との連携で、ジオフェンスとの連携

## AWS IoT Core MQTT v5

- v5 の主な機能
  - メッセージ有効期限の設定
  - 永続セッションの柔軟な管理と有効期限管理
  - トピックエイリアス
    - 従来のトピックを2バイト整数に置き換え
  - 最大パケットサイズの指定
- 従来の v3.1.1 との混在が可能

## AWS IoT Device Management Job Scheduler

- IoT のデバイスシャドウと連携する
- いままでは、自分でコントロールする仕組みを用意する必要があったが、スケジュールの指定が可能になった

## AWS CloudWatch Internet Monitor

- これまで出たアップデート
  - シンセティクス
  - もういっこ
  - RUM
- AWSがインターネットを監視するのに使っていたものを提供する形にしたもの

## AWS CloudWatch データ保護機能の強化

- 機密情報の検出・保護
  - パターンマッチングと機械学習を利用したデータのマキシング
- IAMによって見えたり、見えなくしたりが可能になった

## AWS Elastic Disaster Recovery automated FailBack

- もともとEndureです
- 従来は Route 53 を使ったフェイルオーバー機能は提供されていた
  - しかし、戻すのは手作業だった
- 今回のアップデートで下に戻す、フェイルバックもできるようになった

## AWS ECS Service Connect 

- ALB もしくはAppMesh を従来は使っていたが、どちらも不要でロードバランシングができるように
- AWS Cloud Map のNameSpace と連携してサービスへ接続することができる
- だいぶ設定が簡単にできるように
- いくつかのデフォルト操作を設定することができる


## AWS EFS Elastic Thoughput

- AWS のストレージは容量が増えれば触れるほど早くなる
- EFS が出た当初は1TBを超えたあたりまで行くとやっと早くなる、というのがあった
- そのあとProvisoned Throghput で事前に買っておくというのができた。
  - ワークロードのパフォーマンス要件が明確な場合はこちら
- 今回はスパイクなどある場合に有効

## AWS EFS New LifeCycle Policy

- 7,14,30,60,90 日に加えて、1日が設定可能に

## AWS EFS パフォーマンス改善

-  read 60% 遅延改善
- write 40%　遅延改善
  - ファイルサイズ64KB以下のみ

## AWS Backup -CloudFormation stack

- データ保護ポリシーにCloudFormation スタックをアタッチ可能に
- Backupがサポートするすべてのステートフルコンポーネントが同時にバックアップできるように
- CloudFormation stack が更新されても、自動でバックアップ対象も更新される

## AWS Backup - Amazon Redshift support

- 一元管理運用にRedshiftを組み込み可能になった

## AWS Organization 管理者権限の移譲

- 異なる運用ポリシーを持つ組織単位でサブ管理者を認定
- 個別ポリシーの実装などがより容易になった

## Amazon Macie Automated Data Discovery

- 従来の全バケットのフルスキャンではなく、
- バケット単位のサンプリングにより、機密情報を含むバケットを特定
- Macieの監視対応を自動でチューニング
- 入ってなさそうであれば、勝手に対象から外してみたりしてくれるように
- コストパフォーマンスが良くなりますよ

## AWS Glue Overview

- もともとはサーバレスのETLのサービス
  - 今は、半分は正解
  - もう半分はデータカタログ
    - S3の構造化データをテーブル下のように見せてあげるのがカタログ
    - このカタログをアップデートするのが、Crawlers
- 今は、他のデータ系のサービスからカタログに飛ばせるようになっている
- Glue interactive_session
  - 従来はジョブを起動する際に、ワーカーノードの数を指定する必要があった
  - ジョブが飛んできた時に、ワーカーノードを持ってくるように
- AWS Glue Streaming ETL 
  -  数秒でリアルタイム処理ができるように

## AWS Glue 4.0
- ここからが、re:Invent 
- Why 4.0？
  - オープンソースライブラリを大量に含んでいるので、後方互換性がないものが含まれる
  - ユーザが明示的にバージョンを指定できるようにしている
- 通常より2から3倍の高速化が期待できる
- Spark向けCSSプラグインに対応
- Pandas対応

## AWS Glue for Ray

- AWS Glue は、大規模なものはApache Spark 
- 小規模なものにはPythonのシングルノード
- AWS SDK for Pandas と連携
- Rayってのがある

## AWS Glue Custom Visual Transform

- Glue Studio の追加機能
- 独自のETLロジックや、Studioの入力規則などを作成し、共有することが可能
- マスターの管理者が作って、みんなが使えるように
  - フォームのバリデーションみたいな感じ

## AWS Wicker 

- chime どこいったw
- E2E encryption
- データの自動削除

## Amazon EKS Marketplace Direct Deployment

- マケプレにあるものをコンソールから選んで直接デプロイできるように

## Amazon Verified Permission

- アプリケーション向けのスケーラブルできめ細かい権限管理・認可サービス
- コードを変更することなく、パーミンションルールの変更と更新を1箇所で管理し運用を簡素化
- もともとは
  - RBAC認証
    - ロールベース
    - 人のロールというのは増えていく、、、
  - ABAC認証
    - 個人の属性をベースで
- PBAC
  - RBACとABACの合わせ技を提供した
  - 権限の移譲
    - FBだとこの人に写真見せてもいいよ。みたいなやつ


## Amazon EC2 Microsoft Office AMI

- Marketplace と連携し以下の課金体系を提供
- ユーザ単位で月額課金

## Amazon EC2 R7iz (クローズドプレビュー)

## Amazon Redshift Updates

- MERGE クエリをサポート
- ROLLUP、CUBE、GROUPING SETS　クエリをサポート
- もういっこ

## AWS Config Rules Proactive Compliance

- 従来はデプロイ後のチェックを実施（デプロイはされちゃう ）
- こっちは作成時に違反してたら、止めてくれるように

## AWS Control Tower Comprehensive Controls Management

- CloudFormation によりリソースがプロビジョニングされるタイミングでコンプライアンス違反のリソースを止めてくれる
- 上と代替一緒のCF限定みたいな


## AWS Control Tower Account Factory Customizeatin (AFC)

- 管理対象アカウント作詞したら、サービスカタログに登録しCFを実行
- 登録済みの推奨環境なんかも用意されている
- Datadogとか

## VPC Reachability Analyzer AWS Organization 経由のマルチアカウント対応

- 3月にTransit Gateway に対応

## Amazon S3 Multi-Region Access Points Failover control

- AWS Global Accelerator を活用したマルチリージョン

## Amazon Braket Algorithm Library

- さまざまなPython実装をGithub上でオープンソースとして公開
- Jupyterノートブック対応

## AWS Network Manager Real-time performance monitoring

- リージョン間、AZ間、AZ内が取れるように

## AWS CloudTrail Lake / AWS config integration

- CloudTrail Lake
  - SQL で操作ができるように
- AWS Config ルールが、CloudTrail のどの操作によって引き起こされたのかがわかるように

以上