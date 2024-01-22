---

copyright:

  years: 2015, 2024

lastupdated: "2024-01-22"

keywords: create case, manage case, open case, start case, ticket

subcollection: get-support

---

{{site.data.keyword.attribute-definition-list}}

# Creating support cases
{: #open-case}

If you experience problems with {{site.data.keyword.Bluemix}}, you can use the [Support Center](/unifiedsupport/supportcenter){: external} to create a support case. Users with a Basic, Advanced, or Premium [support plan](/docs/get-support?topic=get-support-support-plans) can create a technical support case by attaching a specific resource or product to ensure that the case gets to the correct support engineer faster. This allows for a more efficient and effective resolution.
{: shortdesc}

If your account is deactivated or if you don't have access to your account, you can create a support case by completing the [Create an Account, Login or Billing Request](https://watson.service-now.com/x_ibmwc_open_case_app.do#!/create) form.
{: tip}

You can also create support cases for issues that are associated with access (IAM), billing & usage, account, and invoice or sales inquiries. The types of available support depend on the support level of the account. Your support plan also determines the severity level that you can assign to support cases. For more information, see [Case severity and response time](/docs/get-support?topic=get-support-support-case-severity).

Users with a Lite account can also create support cases, but are limited to issues associated with access (IAM), billing & usage, account, and invoice or sales inquiries. Technical support for Lite accounts with free support is provided by the [{{site.data.keyword.Bluemix_notm}} docs](/docs){: external} and [Stack Overflow](https://stackoverflow.com/questions/tagged/ibm-cloud?tab=Newest){: external}.

By default, account users don't have access to create, update, search, or view cases. The account owner must provide users access by assigning an Identity and Access Management (IAM) access policy. For more information, see [Assigning user access for working with support cases](/docs/get-support?topic=get-support-access#access).
{: tip}

## Creating a support case
{: #creating-support-case}
{: ui}

Complete the following steps to create a support case:

1. From the {{site.data.keyword.cloud_notm}} console menu bar, click the **Help** icon ![Help icon](../icons/help.svg "Help") > **Support center**.
1. From the Contact support section, click **Create a case**.
1. Select the category for your issue.
1. Select the topic and the associated subtopic that is most closely related to your issue, and click **Next**.
1. Complete the required fields.

   To maintain security, do not include any personal information, sensitive data, or device or service credentials in case responses. For example, don't include passwords, API keys, secrets, or credit card information.
   {: important}

1. Optional:
   * Attach files and resources to provide more details about the issue you're experiencing.
   * If you'd like a user in you account to be updated about the case, add them by using the Contact watchlist. For more information about assigning users access to your account, see [Adding users to your case management access group](/docs/get-support?topic=get-support-access#add-user-access-group).
   * Select **Email me updates about this case** to receive support case notifications.
1. Click **Next**, review your case summary, and click **Submit case**. After you receive email verification for the case, follow the instructions for further communication on the issue.

After your support case is created, you can follow its progress on the [Manage cases page](/unifiedsupport/cases).
{: tip}


## Creating a support case by using the API
{: #create-case-api}
{: api}

You can programmatically open a support case by calling the Case Management API as shown in the following sample requests. For more information about the API, see [Case Management](/apidocs/case-management#createcase){: external}.

```curl
curl --location --request POST 'support-center.cloud.ibm.com/case-management/v1/cases' --header 'Content-Type: application/json' --header 'Content-Type: text/plain' --data-raw '{ "type": "technical",
  "subject": "Case subject",
  "description": "Case description",
  "severity":4,
   "offering": {
    "name": "Cloud Object Storage",
    "type": {
      "group": "crn_service_name",
      "key": "cloud-object-storage",
      "kind": "service",
      "id": "dff97f5c-bc5e-4455-b470-411c3edbe49c"
    }
  },
  "resources": [
    {
      "crn": "crn:v1:staging:public:cloud-object-storage:global:a/2dded3de4a4d4a098ebd0998be5cc845:723a59c4-9338-43fe-9dc4-e4a87cc78c8e::",
      "note": "Resource note"
    }
  ]
}'
```
{: codeblock}
{: curl}

```java
OfferingType offeringType = new OfferingType.Builder()
  .group(OfferingType.Group.CRN_SERVICE_NAME)
  .key("cloud-object-storage")
  .build();
Offering offeringPayload = new Offering.Builder()
  .name("Cloud Object Storage")
  .type(offeringType)
  .build();
CreateCaseOptions createCaseOptions = new CreateCaseOptions.Builder()
  .type("technical")
  .subject("Example technical case")
  .description("This is an example case description. This is where the problem would be described.")
  .offering(offeringPayload)
  .severity(4)
  .build();

Response<Case> response = service.createCase(createCaseOptions).execute();
Case xCase = response.getResult();

System.out.println(xCase);
```
{: codeblock}
{: java}

```javascript
const offeringType = {
  group: 'crn_service_name',
  key: 'cloud-object-storage',
};

const offeringPayload = {
  name: 'Cloud Object Storage',
  type: offeringType,
};

const params = {
  type: 'technical',
  subject: 'Example technical case',
  description: 'This is an example case description. This is where the problem would be described.',
  offering: offeringPayload,
  severity: 4,
};

caseManagementService.createCase(params)
  .then(res => {
    caseNumber = res.result.number
    console.log(JSON.stringify(res.result, null, 2));
  })
  .catch(err => {
    console.warn(err)
  });
```
{: codeblock}
{: javascript}

```python
offering_type = OfferingType(
  group='crn_service_name',
  key='cloud-object-storage'
)
offering_payload = Offering(
  name='Cloud Object Storage',
  type=offering_type
)

case = case_management_service.create_case(
  type='technical',
  subject='Example technical case',
  description='This is an example case description. This is where the problem would be described.',
  offering=offering_payload,
  severity=4,
).get_result()

print(json.dumps(case, indent=2))
```
{: codeblock}
{: python}

```go
offeringType, _ := caseManagementService.NewOfferingType(
  casemanagementv1.OfferingTypeGroupCRNServiceNameConst,
  "cloud-object-storage",
)
offeringPayload, _ := caseManagementService.NewOffering(
  "Cloud Object Storage",
  offeringType,
)

createCaseOptions := caseManagementService.NewCreateCaseOptions(
  "technical",
  "Example technical case",
  "This is an example case description. This is where the problem would be described.",
)
createCaseOptions.SetSeverity(4)
createCaseOptions.SetOffering(offeringPayload)

caseVar, response, err := caseManagementService.CreateCase(createCaseOptions)
if err != nil {
  panic(err)
}
b, _ := json.MarshalIndent(caseVar, "", "  ")
fmt.Println(string(b))
```
{: codeblock}
{: go}

### Adding a resource to a support case by using the API
{: #add-resource-api}
{: api}

You can programmatically add a resource to a support case by using the API as shown in the following sample request. For more information, see the [Case Management API reference](/apidocs/case-management#casemanagement-createcase){: external}.

```curl
curl -X PUT '/case-management/v1/cases/{case_number}/resources' -H 'Authorization: TOKEN' -d '{
  "crn": "296878",
  "note": "This resource does not work"
}'
```
{: codeblock}
{: curl}

```java
AddResourceOptions addResourceOptions = new AddResourceOptions.Builder()
  .caseNumber(caseNumber)
  .crn(resourceCrn)
  .note("This resource is the service that is having the problem.")
  .build();

Response<Resource> response = service.addResource(addResourceOptions).execute();
Resource resource = response.getResult();

System.out.println(resource);
```
{: codeblock}
{: java}

```javascript
const params = {
  caseNumber: caseNumber,
  crn: resourceCrn,
  note: 'This resource is the service that is having the problem.',
};

caseManagementService.addResource(params)
  .then(res => {
    console.log(JSON.stringify(res.result, null, 2));
  })
  .catch(err => {
    console.warn(err)
  });
```
{: codeblock}
{: javascript}

```python
resource = case_management_service.add_resource(
  case_number=case_number,
  crn=resource_crn,
  note='This resource is the service that is having the problem.',
).get_result()

print(json.dumps(resource, indent=2))
```
{: codeblock}
{: python}

```go
addResourceOptions := caseManagementService.NewAddResourceOptions(
  caseNumber,
)
addResourceOptions.SetCRN(resourceCRN)
addResourceOptions.SetNote("This resource is the service that is having the problem.")

resource, response, err := caseManagementService.AddResource(addResourceOptions)
if err != nil {
  panic(err)
}
b, _ := json.MarshalIndent(resource, "", "  ")
fmt.Println(string(b))
```
{: codeblock}
{: go}

## Supported file types for cases
{: #supported-file-types}

When you create a case, you can attach a file. The following file types are supported:

```text
7z, ace, ams, arm, asp, bash, history, bkp, big, bmp, bz2, ca, ca-bundle, ca-crt, cabundle, cap, cer, cert, cfg, cnf, crt, csr, csv, dat, dbs, debug, dib, dmesg, dmp, doc, docx, dotx, dump, email, eml, emz, env, eps, error, evt, evtx, fragment, gif, gz, gz_aa, gz_ab, gz_ac, har, hosts, htaccess, html, iaf, ics, id, img, info, jpb, jpe, jpeg, jpg, key, lic, log, logsm lon02, lst, lzh, mai, md5, mib, mjpg, msg, mso, odp, ods, odt, oft, openssh, out, ovf, ovpn, p7b, p7s, pages, pcap, pcf, pcx, pdb, pem, pfx, pic, pix, png, ppk, ppt, pptx, psd, psp, pspimage, pub_key, rar, raw, rdp, req, rpt, rtf, sjc03-raid-2, sjc03-raid-log-1, snag, sql, ssh, stats, sth, svg, sxc, tar, targz, tbz2, tcpdump, text, tgz, tgz-aa, tgz-ab, tgz-ac, tgz-ad, tgz-ae, tgz-af, tgz-ag, tgz-ah, tgz-ai, tgz-aj, tgz-ak, tgz-ak, tgz-al, tgz-al, tgz-am, tif, tiff, tip, trace, tsv, txt, ufo, vcf, vdx, vsdx, webarchive, wml, wps, wpz, wrf, wri, xcf, xlog, xlr, xls, xis, xism, xisx, xit, xml, xpm, xps, xslic, xz, yaml, zip, zipaa, zipx, zone
```
{: screen}
