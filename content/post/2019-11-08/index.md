+++
title =  "インフラエンジニアなりたてで知らなかった単語をまとめ"
url = "2019-11-08"
date = "2019-11-08"
description = "インフラエンジニアなりたてで知らなかった単語をまとめ"
tags = [
    "AWS",
]
categories = [
    "AWS",
]
archives = "2019/11"
aliases = ["migrate-from-jekyl"]
+++

<br>
インフラの勉強をし始めて分からなくて調べた単語をまとめました。

<!-- for swiswiswift.com responsive -->
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-5587141252700968"
     data-ad-slot="1697863134"
     data-ad-format="auto"
     data-adtest="on"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>
<!-- for swiswiswift.com responsive -->


### コンソリデーティッドビリング（Consolidated Billing）
一括請求機能。AWS Organizations で利用することができ、組織の連結アカウントのすべての料金を支払者アカウントに一括請求することができる。連結アカウントのコストを追跡することが可能となる。

### ルートアカウント
AWSアカウントを作成するときに使用した Eメールアドレスとパスワードで AWSマネジメントコンソールにサインインするとルートアカウントとしてログインすることができる。
ルートアカウントはAWSアカウントのすべてのリソースへの完全かつ無制限なアクセスが可能になり、そのアクセス権限を制限することはできない。
- 普段はルートアカウントでサインインしない
- AWS アカウント（ルート）のアクセスキーを使用しない
- AWS 多要素認証（MFA）を有効にする

### IAM: Identity and Access Management
AWS リソースへのアクセスを安全にコンソールするためのウェブサービス。IAM を使用して、リソースを使用するために認証 (サインイン) され、許可された (アクセス許可を持つ) ユーザーを制御する。

### IAMユーザー
IAM ユーザーは、AWS を操作するために IAM ユーザーを使用する人物またはサービス。
IAM ユーザーは主に、ユーザーが対話型タスクを実行するために AWS マネジメントコンソールにサインインする場合や、API または CLI を使用して AWS サービスに対しプログラムによるリクエストを行う場合に使用する。
GUI用とCLI用の二種類が存在する。

### IAMグループ
IAM グループとは、IAM ユーザーの集合。
グループを使用して、ユーザーの集合に対してアクセス権限を指定でき、ユーザーのアクセス権限を容易に管理することができる。

### ポリシー
ポリシーは、ユーザーが実行できるアクションと、アクションが影響を与えることができるリソースを登録したドキュメント。
IAM ユーザーを IAM グループにまとめ、そのグループにポリシーをアタッチできる。そのグループのすべてのユーザーは、グループにアタッチされているポリシーの内容通りのアクセス許可を持っている。

### リージョン
物理的なサーバーが置いてある地理的に離れた領域。ap-northeast-1 が日本。us-west-2 がオレゴン。

### アベイラビリティゾーン
データセンターの場所。ap-northeast-1a が品川、ap-northeast-1c が埼玉にあるという噂を聞いた。

### ローリングデプロイ（Rolling Deployment）
複数の稼働中サーバーに対して一定数づつ新しいアプリケーションをデプロイ、リリースしていく方法。 In-Place Deployment と Immutable Deployment がある。

### インプレースデプロイ（In-Place Deployment）
稼働中サーバーに対して直接新しいアプリケーションを配置、再起動する方法。

### イミュータブルデプロイ（Immutable Deployment）
稼働中サーバーとは別の新しい環境に新しいアプリケーションをデプロイしてテストし、問題なければ新環境に切り替えを行い、旧環境は削除する。 ロールバックする場合も新環境に古いアプリケーションをリリースして切り替える。

### ブルーグリーンデプロイ（Blue/Green Deployment）
稼働中サーバー（ブルー）とは別のサーバー（グリーン）に対して新しいアプリケーションを展開し、動作確認を行う。

### カナリアデプロイ（Canary Deployment）
稼働中サーバーの一部だけに新しアプリケーションをデプロイ、リリースする方法。 特定のユーザーだけに新しいアプリケーションを利用してもらうことで新サービスの検証が可能。 デプロイする方法は問わず、デプロイ先の数だけに注目したデプロイ方法。

## 参考
[AWS ドキュメント](https://docs.aws.amazon.com/)  
[AWSを安全に利用するために - ルートアカウント利用禁止、IAMを使う](https://qiita.com/tonishy/items/9eb772b4a5a338ac6ee6#24-iam%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%97)  
[クラウドインフラエンジニア採用のための面談時質問シート](https://qiita.com/raki/items/4347366f78b8580d9f54)  
[近年のデプロイ手法について](https://clonos.jp/knowledge/detail14/)  