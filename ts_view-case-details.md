---

copyright:

  years: 2020

lastupdated: "2021-09-13"

keywords: support center help, resolve issues on the support center, trouble support center, personalized help

subcollection: get-support

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why can't I view all cases in the account?
{: #ts_viewcasedetails}

You can't view all of the cases in the account because you don't have access to view all users in the account.
{: shortdesc}

When you try to view the support cases that are associated with the account, you can't see all open cases. You can view users that you invited to the account and users who are in your classic infrastructure user hierarchy.
{: tsSymptoms}

The account owner set the [user list visibility setting](/docs/account?topic=account-iam-user-setting#userlistview) to restricted, and you don't have the required access to view all cases in the account.

You must be assigned an IAM policy with at least the Viewer role on the User management account management service in addition to your Support Center account management service access policy. To view your current access, in the {{site.data.keyword.Bluemix_notm}} console, go to **Manage** > **Access (IAM)**, and select your name from the **Users** page. Click the **Access policies** tab.
{: tsCauses}

To resolve the issue, contact the account owner to request the appropriate access.
{: tsResolve}
