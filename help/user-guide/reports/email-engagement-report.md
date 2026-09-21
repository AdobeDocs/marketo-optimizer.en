---
title: Email Engagement Report
description: Learn about the Email Engagement report in Adobe Marketo Optimizer, which shows email deliverability and engagement metrics by email and journey.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
---

# Email Engagement report

<!-- SPHR-32511: Filter by Program, Filter by Audience, and the program data point for the email performance table are not documented here pending delivery. -->

Use the [!UICONTROL Email Engagement] report to review email deliverability and engagement performance across your instance, broken down by email and journey.

_To view the report:_

1. In the left navigation, select **[!UICONTROL Reports]**.
1. Click the _List_ icon ( ![List icon](../assets/do-not-localize/icon-table-of-contents.svg) ) and select **[!UICONTROL Email Engagement]** in the _[!UICONTROL Table of contents]_ panel.

![Email Engagement report with Journey Name and Persona filters, a Last 30 days date range, and a table of email activity metrics.](./assets/reports-email-engagement.png){width="700" zoomable="yes"}

You can [change the date range](./reports-overview.md#change-the-date-range) using the same date range picker available on other report sections.

Select **[!UICONTROL Share]** at the top of the report to download or schedule an export of all report data. See [_Export a report_](./reports-overview.md#export-a-report) in the Reports overview.

## Report table {#report-table}

The [!UICONTROL Email Engagement] report shows one row for each email, with the following row dimensions.

* **[!UICONTROL Email Name]** - The name of the email.
* **[!UICONTROL Journey Name]** - The name of the journey that sent the email.

Metric columns are grouped under **[!UICONTROL Email Activities]**.

| Column | Description |
| --- | --- |
| [!UICONTROL Sent] | Number of emails sent. |
| [!UICONTROL Delivered] | Number of emails delivered. |
| [!UICONTROL % Delivered] | Percentage of sent emails that were delivered. |
| [!UICONTROL Hard Bounced] | Number of emails that permanently failed to deliver. |
| [!UICONTROL Soft Bounced] | Number of emails that temporarily failed to deliver. |
| [!UICONTROL Opened] | Number of times recipients opened the email. |
| [!UICONTROL % Opened] | Percentage of delivered emails that were opened. |
| [!UICONTROL Clicked] | Number of times recipients clicked a link in the email. |
| [!UICONTROL % Clicked] | Percentage of delivered emails that received a click. |
| [!UICONTROL Click to Open Ratio] | Percentage of opened emails that received a click. |
| [!UICONTROL Unsubscribed] | Number of recipients who unsubscribed from the email. |
| [!UICONTROL % Unsubscribed] | Percentage of delivered emails that resulted in an unsubscribe. |

## Filters {#filters}

Use filters to narrow the report to a specific journey or persona. Select **[!UICONTROL Reset all]** to clear every filter and return to the default view.

* **[!UICONTROL Journey Name (Event)]** - Filter by the journey that sent the email. Default is [!UICONTROL No filter].
* **[!UICONTROL Persona (Event)]** - Filter by the persona associated with the email. Default is [!UICONTROL No filter].