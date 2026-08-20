---
title: Forms Configuration
description: Placeholder
---
# Forms configurations

Before marketers can create and publish forms to use in their landing pages, a product administrator must create one or more dedicated presets. Each preset defines the connection endpoint used to send the form submission data, and the dataset used to store the captured data.

When data lands on the streaming endpoint, it is linked with the dataset information. Using the generated source/target connections and source flow, the data is then pushed into the dataset.

>[!BEGINSHADEBOX]

## Prerequisites

To use web forms, you must have one or more _**HTTP API streaming connections**_ defined in Adobe Experience Platform. Make sure that each connection that you want to use meets the following requirements:

* Data type must be set to XDM (not Raw data)
* Authentication must be disabled (non-authenticated connection)

For detailed information about creating a streaming source connections, refer to the [_Experience Platform documentation_](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/streaming/http).

<!-- 
permissions coming in GA

Forms channel configuration in Journey Optimizer B2B Edition requires the following [permissions](../start/user-management.md#b2b-product-permissions):

* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL View Forms Presets]_ - Required to view forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Manage Forms Presets]_ - Required to create, update, and delete forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Publish Forms Presets]_ - Required to publish forms preset configurations.
-->

>[!ENDSHADEBOX]

## Form preset configuration guidelines

When creating a preset:

* You can set up multiple presets using different combinations of datasets and streaming connections.

* You can reuse the same dataset or streaming connection across multiple presets.

* Each streaming connection automatically generates resources, such as:

   * _Source connection_ – where the data originates.
   * _Target connection_ – where the data is stored or consumed.
   * _Source flow_ – the pipeline that moves data from the source connection into Experience Platform. It handles mapping, transformation, and validation.

## Create a form preset {#create-preset}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_connection"
>title="Select the endpoint to use"
>abstract="Define the streaming endpoint where data is sent upon submitting the form."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/streaming/http" text="Create an HTTP API streaming connection"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_dataset"
>title="Select a dataset"
>abstract="Define a dataset where the form responses are stored and reflected. Enter text to search a specific dataset or select it from the list."

1. In the left navigation, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. 

1. Under _[!UICONTROL Form Settings]_ in the navigation panel, select **[!UICONTROL Form presets]**.

   <!-- ![Access the form configurations](./assets/config-channels-forms.png){width="800" zoomable="yes"} -->

1. Click **[!UICONTROL Create form preset]**.

1. Enter a unique **[!UICONTROL Name]** (required) and a **[!UICONTROL Description]** (optional) for the configuration.

   >[!NOTE]
   >
   >Names must begin with a letter (A-Z) and can only contain alphanumeric characters. You can also use underscore `_`, dot `.`, and hyphen `-` characters.

1. Select the **[!UICONTROL Streaming connection]**. 

   This connection is the streaming endpoint used to send the data when a web viewer submits a form. If the needed streaming connection does not appear in the list, verify that the requirements are met.

1. Click the _Select dataset_ ( ![Select dataset icon](../assets/do-not-localize/icon-select-data.svg) ) icon to link a dataset with the form. 

   The dataset is where the form responses are stored and reflected. You can enter a text string to search for a specific dataset or select it from the list.

   <!-- ![Select datasets dialog](./assets/config-channel-forms-select-datasets.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >Currently only Profile-enabled and Non-Profile-enabled [Adobe Experience Platform datasets](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview) are available for selection. You can select one dataset at a time. System datasets cannot be used for saving form data.

   Select the checkbox for the dataset and click **[!UICONTROL Select]**.

1. Click **[!UICONTROL Save as draft]**. 

## Publish a form preset

1. Click the form preset name to open the configuration page.

   You can make any adjustments to the draft if needed.

1. Click **[!UICONTROL Publish]**.

   When the form preset is listed with a _Published_ status, it is available to use for form creation.
