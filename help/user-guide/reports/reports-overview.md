---
title: Reports
description: Understand the Reports tab in Adobe Marketo Optimizer, including its report sections, export and scheduling options, and how to change the date range.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
---

# Reports

The [!UICONTROL Reports] tab gives you performance insights across [!DNL Adobe Marketo Optimizer], including journey engagement, email performance, and web activity. On the left navigation, select **[!UICONTROL Reports]** to open it.

Each report is built on [!DNL Adobe Customer Journey Analytics] and embedded directly in [!DNL Marketo Optimizer]. Click the _List_ icon ( ![List icon](../assets/do-not-localize/icon-table-of-contents.svg) ) to use the **[!UICONTROL Table of contents]** panel on the left to jump between sections. 

![Reports page listing Person Journey Overview, Engagement, Email Engagement, and Web Engagement sections](./assets/reports-table-of-contents.png){width="800" zoomable="yes"}

## Report sections {#report-sections}

The [!UICONTROL Reports] tab organizes pre-built reports into four sections. Each section has one or more downloadable items, and its own documentation page with details about its metrics and visualizations.

| Section | Downloadable items | Report page |
| --- | --- | --- |
| [!UICONTROL Person Journey Overview] | Number of active journeys | [Person Journey Overview report](./person-journey-overview-report.md) |
| [!UICONTROL Engagement] | Engagement by people, Person engagement over time | [Engagement report](./engagement-report.md) |
| [!UICONTROL Email Engagement] | Email Engagement | [Email Engagement report](./email-engagement-report.md) |
| [!UICONTROL Web Engagement] | Top page views | [Web Engagement report](./web-engagement-report.md) |

## Individual-record reports {#individual-record-reports}

Some reports focus on a single record instead of a section-wide view and are accessed from a different area in the application.

* For email send-time optimization performance, open the report from the [!UICONTROL Coworker] chat interface. For steps, see [Email send-time optimization](../marketing/email-send-time-optimization.md#reporting).
* For a person's progress through a single journey, open the report from within that journey.

## Export a report {#export-a-report}

Select **[!UICONTROL Share]** at the top of the report page to export or schedule delivery of its data.

![Share menu with Download CSV, Download PDF, Schedule export, and Manage schedules options](./assets/reports-share-menu.png){width="500"}

* **[!UICONTROL Download CSV]** - Export the report data as plain-text values.

* **[!UICONTROL Download PDF]** - Export all visible tables and visualizations in the report as a PDF file.

* **[!UICONTROL Schedule export]** - Set up a recurring export of the report, delivered weekly or monthly as a CSV or PDF file.

* **[!UICONTROL Manage schedules]** - Review and manage existing scheduled exports. The option shows a running count, such as `3/10`, of schedules used against your organization's limit.

>[!NOTE]
>
>Your organization can have a maximum of 10 scheduled exports across all reports, on a weekly or monthly frequency. If you are not an administrator, you can manage only your own scheduled exports. Administrators can view and manage every scheduled export in the organization.

## Analyze a report in CJA {#analyze-a-report-in-cja}

>[!AVAILABILITY]
>
>This function is available if your organization is licensed for [!DNL Adobe Customer Journey Analytics] and you are assigned the product profile.

Select **[!UICONTROL Analyze in CJA]** on any report section to open it in [!DNL Adobe Customer Journey Analytics] Workspace, where you can create custom visualizations in addition to what's available in the embedded report.

## Change the date range {#change-the-date-range}

Each report section shows data for a specific date range, displayed in the top-right corner of the section. Click in the date range fields to display the date selection tools and select the date range. You can choose a different preset or define a custom range.

![Date range picker with a two-month calendar, start and end date fields, and preset options](./assets/reports-date-range.png){width="600"}
