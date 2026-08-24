---
title: Privacy Management
description: Learn how to comply with GDPR, CCPA, and other privacy regulations in Marketo Optimizer, and submit requests using Adobe Privacy Service.
feature: Setup
role: Admin
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---

# Privacy management {#privacy-management}

[Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/home){target="_blank"} provides a RESTful API and user interface to help you manage customer data requests. With [!DNL Adobe Privacy Service], you can submit requests to access and delete personal customer data from Adobe CX Enterprise applications, facilitating automated compliance with legal and organizational privacy regulations.

[!DNL Adobe Marketo Optimizer] provides these privacy tools so that you can meet global data protection requirements. Use [!DNL Privacy Service] to submit and manage access and delete requests for data that [!DNL Marketo Optimizer] collects and stores.

You can submit individual requests to access and delete consumer data from [!DNL Adobe Marketo Optimizer] in two ways:

* The [!DNL Privacy Service] UI
* The [!DNL Privacy Service] API

## Supported privacy regulations {#regulations}

[!DNL Marketo Optimizer] privacy tools help you comply with the regulations through [!DNL Privacy Service]. Each regulation applies if you hold data for people who reside in the associated region.

For an up-to-date list of the supported regulations, see [_Privacy regulations overview_](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/regulations/overview){target="_blank"} in the Privacy Service documentation.

## Request types {#access-and-delete-requests}

[!DNL Marketo Optimizer] supports two privacy request types:

* **Data access** - A person can request confirmation that their personal data is being processed, and receive a free electronic copy of that data.
* **Data delete** - Also called the _right to be forgotten_, a person can request that you erase their personal data and stop further processing.

## View and manage privacy requests {#view-manage-requests}

>[!BEGINSHADEBOX]

![AEP Permissions icon](../assets/do-not-localize/icon_permissions-outline.svg) These steps require the [!DNL Privacy Service] product profile and the following [permissions for your assigned user role in Experience Platform](../start/user-management.md#permissions):

* **[!UICONTROL Privacy Service Permissions]** - `Privacy Read Permission` and `Privacy Write Permission`
* **[!UICONTROL Data Governance]** - `View Privacy Console`

See [_Manage permissions for Privacy Service_](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/permissions){target="_blank"} in the [!DNL Privacy Service] Guide for more detailed information.

>[!ENDSHADEBOX]

To view privacy request jobs in [!DNL Marketo Optimizer], expand **[!UICONTROL Privacy]** and select **[!UICONTROL Requests]**.

Use the **[!UICONTROL Regulation Type]** option at the top right to change the displayed page for the regulation that you want to manage jobs or submit requests.

![Privacy request jobs, select the regulation type](./assets/privacy-requests.png){width="800" zoomable="yes"}

### Submit a request {#submit-a-request}

1. Click **[!UICONTROL Create Request]**.

1. For the **[!UICONTROL Job Type]**, select the request type:

   * **[!UICONTROL Access]**

      When you submit an **_access_** request that includes [!DNL Marketo Optimizer], [!DNL Privacy Service] returns:

      * [!DNL Marketo Engage] activity associated with the lead.
      * [!DNL Marketo Optimizer] activity associated with the person or account.

   * **[!UICONTROL Delete]**

      When you submit a **delete** request for [!DNL Marketo Engage] and [!DNL Marketo Optimizer], the following records are removed:

      * The associated lead in [!DNL Marketo Engage].
      * Person and account records created in [!DNL Marketo Optimizer].
      * Coworker conversation history that references the person's personal information.

1. For **[!UICONTROL Products]**, select **[!UICONTROL Marketo]**.

   ![Create GDPR access privacy request for Marketo Engage and Marketo Optimizer](./assets/privacy-request-create-gdpr.png){width="450" zoomable="yes"}

   This selection includes data from both [!DNL Marketo Optimizer] and your [!DNL Marketo Engage] instance.

1. Scroll to the bottom of the dialog and enter the email address of the person whose data you want to access or delete.

1. To submit the request, click **[!UICONTROL Create]**.

   [!DNL Privacy Service] returns a request ID that you can use to check the status of your request.

### API requests {#api-requests}

You can also submit privacy requests using the [!DNL Privacy Service] API. For general API reference, see the [Privacy Service API documentation](https://developer.adobe.com/experience-platform-apis/references/privacy-service){target="_blank"}.

>[!PREREQUISITES]
>
>Gather the following information before submitting a request:
>
>* The IMS Org ID for your organization (a 24-character alphanumeric string that ends in `@AdobeOrg`). Contact Adobe Support at `gdprsupport@adobe.com` if you do not know your IMS Org ID.
>* The email address of the person whose data you want to access or delete.

Use the following field values in your request:

| Field | Value |
|---|---|
| `companyContexts.namespace` | `imsOrgID` |
| `companyContexts.value` | Your IMS Org ID |
| `users.action` | `access` or `delete` |
| `users.userIDs.namespace` | `Email` |
| `include` | `marketo` to include both [!DNL Marketo Optimizer] and [!DNL Marketo Engage] data |
| `regulation` | Example: `ccpa` <br/>Some regulation values are changing to include a state abbreviation (for example, `ucpa_ut_usa`). Older values remain valid for a transition period. See the [Privacy regulations overview](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/regulations/overview){target="_blank"} for the current list before you build integrations against these values. |

The following example submits a GDPR delete request that includes [!DNL Marketo Optimizer] data.

```json
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": ["delete"],
      "userIDs": [
        {
          "namespace": "Email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": ["marketo"],
  "regulation": "gdpr"
}
```

[!DNL Privacy Service] returns a response similar to the following.

```json
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": ["delete"],
          "userIDs": [
            {
              "namespace": "Email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
