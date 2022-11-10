---

copyright:

  years: 2015, 2022

lastupdated: "2022-11-10"

keywords: cloud status, view cloud status, planned maintenance, RSS feed, unfied notifications, iaas notifications, classic infrastructure notifications, incident reports

subcollection: get-support

---

{{site.data.keyword.attribute-definition-list}}

# Viewing cloud status
{: #viewing-cloud-status}

The {{site.data.keyword.Bluemix_notm}} [Status page](/status){: external} is the central place to find details about major incidents that affect the {{site.data.keyword.Bluemix}} platform and services. Other incidents, planned maintenance, announcements, release notes, and security bulletins are posted on the Notifications page, where you can easily view them. 
{: shortdesc}

To get notified about key events that are specifically affecting your account, go to the [Notifications page](/notifications){: external}. You can easily update your preferences by clicking **Manage email preferences**.
{: tip}

To view the Status page, complete the following steps:

1. In the {{site.data.keyword.Bluemix_notm}} console, click the **Notifications** icon ![Notifications icon "Notifications"](../icons/Notification.svg) in the menu bar.
1. Click **View cloud status**.
1. From the side navigation pane, you can select to view planned maintenance, security bulletins, announcements, release notes, and history.

   To view planned maintenance and report outages for your account, you must be logged in to your authorized account.
   {: note}

   * Click **Planned maintenance** to see any upcoming scheduled maintenance. 
   * Click **Security bulletins** to view a list of security bulletins that might affect various {{site.data.keyword.Bluemix_notm}} services or the platform.
   * Click **Announcements** to view a list of announcements that might be of general interest to you. 
   * Click **Release notes** to view release entries for the last year. 
   * Click **History** to view a list of completed events from the past year. 

   If any issue occurs with the Status page, contact [{{site.data.keyword.cloud_notm}} Support](/unifiedsupport/supportcenter){: external}.
   {: note}

1. You can filter the lists by selecting specific components, locations, dates, types of ongoing events, or by using keyword searches. Click each item to get more details about the changes and why, and how they impact your environment.

You can build URL search values by using query parameters from outside the console. For more information, see [Advanced status search](/docs/get-support?topic=get-support-adv-search).
{: tip}


## Subscribing to an RSS feed
{: #subscribing-rss-feed}

You can stay up to date about the events by subscribing to the RSS feed for the Status page. Ongoing incidents or planned maintenance windows that impact a finite set of accounts do not display on the Status page. 

{{site.data.keyword.Bluemix_notm}} typically has approximately 50 updates per month.
{: note}

To subscribe to the RSS feed, complete the following steps:

1. Access your favorite RSS readers. Many browsers have built-in RSS capabilities or extensions available. Several third-party RSS reader products are also available. 
1. Use your reader to subscribe to the feed with one of the following methods:
   * Drag the RSS icon ![RSS-24px](../icons/RSS-24px.svg) into your RSS reader.
   * Right-click the RSS icon, select **Copy link address**, and paste the URL into your RSS reader.

For more information, see your reader's **Help** section.

## Checking incident reports
{: #status-incident-report}

The {{site.data.keyword.Bluemix_notm}} [Incident reports page](/status/incident-reports){: external} provides a way for you to review technical details of major outages for {{site.data.keyword.Bluemix_notm}} services. These Customer Incident Reports (CIR) provide Root Cause Analysis (RCA), which is a problem-solving process that is used for identifying the root causes of an incident and describing the problem. They are publicly available for all major outages.

You can view and download the incident reports from the service health dashboard about any events that affect {{site.data.keyword.Bluemix_notm}} availability. 

The downloadable reports are in PDF file formats. These reports are available for 5 years starting from the date when the event occurred.
{: note}

The events can be region-specific, global, or they might have an unspecified location. 

To view the Incident reports page and check RCAs, complete the following steps:

1. In the {{site.data.keyword.Bluemix_notm}} console, click the **Notifications** icon ![Notifications icon "Notifications"](../icons/Notification.svg) in the menu bar.
1. Click **View cloud status**. 
1. Select **Incident reports**.
1. See the table for the incident reports and click the **Download** icon ![Download icon](../icons/download.svg "Download") to download each report. 
