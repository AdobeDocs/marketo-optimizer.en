---
title: Email Channel Configuration
description: Create and manage email channel configurations that bind sender identity, subdomain, IP pool, email type, and URL tracking for Marketo Optimizer.
feature: Administration
role: Admin
---
# Email channel configuration

A channel configuration is the central object that ties together your sender identity, subdomain, IP pool, and tracking settings. Email actions in journeys reference a channel configuration to know how to send the message. Before you create a configuration, complete [subdomain delegation and IP pool setup](../start/email-deliverability.md).

* **Channel:** Email.
* **Email type:** Marketing or Transactional. This setting determines whether suppression rules apply (Marketing applies them; Transactional bypasses spam-complaint suppression by default for legitimate transactional messages).
* **Header parameters:** From Name, From Email, Reply-To Name, Reply-To Email, Error Email.
* **Subdomain:** The delegated subdomain used for sending. The From Email must use this subdomain.
* **IP pool:** The IP pool used to deliver the message.
* **URL tracking:** Enable or disable click and open tracking; configure the tracking domain.
* **Tags:** Tags for organization and search.

## Create an email channel configuration {#create-email-channel-configuration}

>[!PREREQUISITES]
>
>* At least one [subdomain](../start/email-deliverability.md#subdomain-delegation) must be delegated and Active.
>* At least one [IP pool](../start/email-deliverability.md#ip-pools) must be assigned to your organization.
>* You need the Administrator role.
>* Review [current limitations](../start/email-deliverability.md#limitations) — dedicated IP pools are not available at Beta.

1. In the [!DNL Adobe Marketo Optimizer] left navigation, expand **[!UICONTROL Administration]** and select **[!UICONTROL Channels]**.
1. In the panel, expand **[!UICONTROL Email settings]** and select **[!UICONTROL Channel configurations]**.
1. Click **[!UICONTROL Create channel configuration]**.
1. Enter a Name (for example, _Contoso B2B Marketing — North America_) and an optional Description.
1. Select the **[!UICONTROL Email]** channel.
1. (Optional) Select tags to categorize the configuration.
1. In the **[!UICONTROL Email type]** section, choose Marketing or Transactional.
1. In the **[!UICONTROL Subdomain]** section, select a previously delegated subdomain.
1. In the **[!UICONTROL IP pool]** section, select an Active IP pool. 

   At Beta, only the shared IP pool is available. You can hover over the IPs to view PTR records.

1. Configure the **[!UICONTROL Header parameters]**:
   * From Name (for example, "Contoso Marketing").
   * From Email — must use the selected subdomain (for example, `marketing@mail.contoso.com`).
   * Reply-To Name and Reply-To Email — defaults to _From_ if blank.
   * Error Email — address that receives non-delivery notifications.
1. Enable **[!UICONTROL URL Tracking]** and select the tracking domain.
1. Click **[!UICONTROL Submit]**.

>[!NOTE]
>
>After you submit, the system runs validation: subdomain status, MX record, SPF/DKIM/DMARC alignment, IP pool readiness, FBL registration. The configuration moves through Draft → Processing → Active.

>[!NOTE]
>
>If validation fails, the configuration moves to the **[!UICONTROL Failed]** status. Open the configuration to view the failure reason — common causes are MX record validation failure, IPs in the pool not matching the configuration, or DMARC misalignment. Resolve and resubmit.

## Edit or delete a channel configuration {#edit-channel-configuration}

You can edit channel configurations after creation, but with one important constraint: **Channel cannot be changed.** A configuration is bound to its channel.

When you edit a configuration that is in use:

* **For published journeys:** the change is applied at the next recurrence or the next execution. In-flight executions continue with the previous settings.
* **For transactional or real-time messages:** changes propagate within about five minutes.

>[!WARNING]
>
>Deleting a channel configuration is permanent. You cannot delete a configuration that an active journey references. Remove or reassign all email actions first.

To delete a configuration, first remove or update every email action that references it in [Add emails to journeys](../marketing/email-channel.md#define-email-properties). [!DNL Marketo Optimizer] does not delete a configuration that is currently used by an active journey.

## Multiple channel configurations {#multiple-channel-configurations}

Most B2B organizations use multiple channel configurations to separate brands, regions, or send types. Common patterns:

* A separate marketing configuration per business unit (for example, *BU-A Marketing*, *BU-B Marketing*).
* A dedicated transactional configuration with Email Type = Transactional for product or contract notifications.
* Region-specific configurations using region-specific subdomains (for example, `mail.eu.contoso.com`, `mail.us.contoso.com`) to align with regional ISPs and compliance.

>[!TIP]
>
>Name your configurations with a clear, structured convention — for example: *[Brand] – [Region] – [Type]*. This becomes critical once you have a dozen or more configurations.
