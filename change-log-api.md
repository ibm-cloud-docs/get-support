---

copyright:

  years: 2021

lastupdated: "2021-09-13"

keywords: support api change log, api change log

subcollection: get-support

---

{{site.data.keyword.attribute-definition-list}}


# API change log
{: #change-log}

Staging only

In this change log, you can learn about the latest changes, improvements, and updates for the Case Management API. The change log lists changes that have been made, ordered by the date they were released. Changes to existing API versions are designed to be compatible with existing client applications.


For instructions on how to update to the latest version of this API, see [Updating to the latest version of the _service_ API](/docs/url).

## API versioning
{: #api-versioning}


API requests require a version parameter that takes the date in the format `version=YYYY-MM-DD`. Send the version parameter with every API request.

When the API is changed in a way that is not compatible with previous versions, a new minor version is released. To take advantage of the changes in a new version, change the value of the version parameter to the new date. If you're not ready to update to that version, don't change your version date.


### Active version dates
{: #active-version-dates}

The following table shows the service behavior changes for each version date. Switching to a later version date will activate all changes introduced in earlier versions.

| Version date | Summary of changes |
|---|---|
|`2021-07-04`| New English entities model with improved accuracy and confidence scores.|
|`2021-02-14`| Version 2 Italian entity type system. |
|`2020-12-25`| Version 2 French and German entity type system. |
|`2020-10-31`| Base version.|
{: caption="Table 1. Version" caption-side="top"}


## 31 August 2021
{: #31-aug-2021}

The `auto_delete` property of flow log collectors can now be set to `false` in a `PATCH/v1/flow_log_collectors/{id}` request.

## 4 July 2021
{: #4-jul-2021}

The following changes are activated when you use the version date `2019-07-12` or later.

- New English entities model with improved accuracy.
- Confidence scores are returned in English entities results.

## 15 March 2021
{: #15-mar-2021}

Entity confidence score is now returned for entities requests that use custom machine learning models.

## DD Month YYYY
{: #unique-date-id}

A description of new functionality, changes, and fixes included in this API version.
