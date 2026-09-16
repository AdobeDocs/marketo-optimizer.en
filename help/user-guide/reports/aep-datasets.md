---
title: Experience Platform Datasets
description: Learn about the datasets that Marketo Optimizer writes to Adobe Experience Platform to power Customer Journey Analytics reporting and ad hoc querying.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
---

# Experience Platform datasets

[!DNL Adobe Marketo Optimizer] replicates lead, journey, and activity data into [!DNL Adobe Experience Platform] datasets. These datasets power the [!UICONTROL Reports] page and its embedded [!DNL Adobe Customer Journey Analytics] report experience, and you can also query them directly with [!DNL Query Service] for ad hoc analysis.

The datasets are system-managed. A connection in [!DNL Customer Journey Analytics] links them into the data view that [!DNL Marketo Optimizer] reports use, so you do not need to build this connection yourself. This connection is the same connection you reach when you select **[!UICONTROL Analyze in CJA]** on a report section. See [Analyze a report in Customer Journey Analytics](./reports-overview.md#analyze-a-report-in-cja). 

## Available datasets {#available-datasets}

The following datasets are populated for every [!DNL Marketo Optimizer] instance.

>[!NOTE]
>
>Each dataset name uses the prefix `AJOB2B`, which indicates the system name for [!DNL Marketo Optimizer]. This behavior is expected, and you can use these names to locate the datasets in your [!DNL Experience Platform] sandbox.

| Dataset | Schema | Description |
| --- | --- | --- |
| `AJOB2B - Person` | Person | Standard lead attributes. |
| `AJOB2B - PersonActivity` | Person Activity | Activity events associated with a person. |
| `AJOB2B - PersonActivityType` | Person Activity Type | Activity types associated with a person. |
| `AJOB2B - PersonActivityTypeEngagementMapping` | Person Activity Type Engagement Mapping | Maps activity types to their engagement classification, channel event, and directionality. |
| `AJOB2B - Journey` | Journey | List of journeys and their lifecycle metadata. |
| `AJOB2B - JourneyNode` | Journey Node | List of nodes within a journey and their associated metadata. |
| `AJOB2B - EngagementAsset` | Engagement Asset | Unified lookup of engagement asset IDs and display names across engagement asset types. |

## Query datasets with Query Service {#query-service}

Use [!DNL Query Service] to run ad hoc SQL queries against these datasets when you need analysis outside of [!DNL Customer Journey Analytics] reports. Query access requires the appropriate [!DNL Experience Platform] permissions for your sandbox. For general query syntax and setup, see [Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home){target="_blank"}.

>[!NOTE]
>
>These datasets are read-only. To change what data [!DNL Marketo Optimizer] captures, update the source data in [!DNL Marketo Optimizer] or [!DNL Marketo Engage] instead of editing a dataset directly.
