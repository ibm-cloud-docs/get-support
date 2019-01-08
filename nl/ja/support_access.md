---

copyright:

  years: 2018

lastupdated: "2018-11-28"

---


{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:important: .important}
{:new_window: target="_blank"}

# サポート Case を処理するためのユーザー・アクセスの割り当て
{: #access}

デフォルトでは、アカウント内のユーザーは、Case を作成、更新、検索、表示するためのアクセス権限はいずれも持っていません。 アカウント所有者は、Identity and Access Management (IAM) アクセス・ポリシーを割り当てることによって、ユーザーにアクセス権限を提供する必要があります。 サポート・センターのアカウント管理サービスを使用して、サポート Case を処理するためのアクセス権限をユーザーに割り当てます。
{:shortdesc}

サポート・センターのアクセス・ポリシーは、ユーザーにサポート Case を処理するためのアクセス権限を提供します。 ただし、これらのアクセス・ポリシーは、ユーザーにアカウント内の他のユーザーを表示するアクセス権限を提供するわけではありません。 したがって、アカウント所有者が[**「ユーザー・リストの表示可能設定 (user list visibility setting)」**](/docs/iam/userlist.html#userlistview)を**「制限付き表示 (Restricted view)」**に設定した場合、 Case を管理するアクセス権限を持つユーザーが、他のユーザーまたはアカウント所有者に割り当てられた Case にアクセスできないことがあります。 ユーザーがすべての Case を確実に表示できるようにするには、ビューアー役割が割り当てられた、ユーザー管理のアカウント管理サービスの IAM アクセス・ポリシーをさらに割り当てることによって、追加のアクセス権限を提供する必要があります。 

IAM アクセス・ポリシーを使用して、すべての Case へのアクセス権限ではなく、アカウント内の特定の Case への全アクセス権限を特定のユーザーに付与するには、 Case の作成時にそれらのユーザーの E メールを入力することで、ユーザーを Case に追加します。 作成した Case にユーザーを追加すると、そのユーザーは、アカウント内のその Case のみを表示、編集、および更新するためのアクセス権限を持ちます。 さらに、 Case に対する更新があった場合に、そのユーザーは通知を受け取ります。

以前に、サポート Case のアクセス権限の割り当てにクラシック・インフラストラクチャー許可を使用していたクラシック・インフラストラクチャー・ユーザーの場合、これらの許可は現在、[マイグレーション済みクラシック・インフラストラクチャー許可アクセス・グループ (migrated classic infrastructure permission access groups)](/docs/iam/infrastructureaccess.html#predefined) で使用可能です。マイグレーション済み許可アクセス・グループには、ビューアー役割が割り当てられた、ユーザー管理サービスの IAM ポリシーが含まれます。

サポート・センター・サービスやユーザー管理サービスなどのアカウント管理サービスの IAM アクセス・ポリシーをユーザーに割り当てるには、以下の手順を実行します。

1. メニュー・バーで**「管理」** &gt; **「アクセス (IAM) (Access (IAM))」**をクリックし、**「ユーザー」**を選択します。
2. リストからユーザーを選択します。
3. **「アクセス・ポリシー」**をクリックします。
4. **「アクセス権限の割り当て (Assign access)」**をクリックします。
5. **「アカウント管理サービスへのアクセス権限の割り当て」**を選択します。
6. リストからサービスを選択します。 
5. 対象のアクセス権限を割り当てる役割を選択します。

以下の表を確認して、各役割に含まれる許可を正確に理解してください。

| 役割 | アクション | 
|--------|---------------|
|ビューアー  | Case の表示と検索 |
|管理者 | Case の表示、検索、作成、および更新|
{: caption="表 1. サポート・センター・サービスの役割とアクション" caption-side="top"}
