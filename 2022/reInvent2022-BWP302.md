# How Alloy synced Amazon data in real time

## description

Buy with Prime, one of Amazon’s newest services, allows online retailers to take advantage of the benefits of Amazon’s massive fulfillment service. In this session, dive deep into how Amazon and Alloy worked together to create a data backfilling and synchronization system using Amazon EventBridge, AWS Lambda, Amazon API Gateway, and the Alloy Automation platform.

## memo

### What is Buy with Prime

- Buy with Prime 
  - D2C を提供するもの
    - Shopify みたいなやつ？
  - Merchants
    - Gentle Living
    - Bossy Cosmetics
- オンラインストアとPrimeとどっちを見たらいいのか、わからなくなっちゃうのが問題
- Buy with Prime の構成要素
  - EventBridge から Alloy（3rd Party) にニアリアルタイムで通知している
  - AppSyncで構成

### Collaboration with Alloy

- What is Alloy?
  - EC向けの自動化サービスを提供している
  - shopify に繋げたり
- Key terminology
  - Buy with Prime のトリガーから　Alloy で設定したワークフローで他のD2Cに繋いでいる
- これを、ノーコードで実装できるのが Alloy のサービス

### アーキテクチャ



## スケーラビリティ

- EKS のクラスタのお話
  - k8s はよくわからんです


#### 