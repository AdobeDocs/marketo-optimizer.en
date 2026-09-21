---
title: Person Journey Individual Report
description: Learn about the Person Journey Individual report in Adobe Marketo Optimizer, which shows completion, engagement, and email metrics for one journey.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
---

# Person Journey Individual report

<!-- SPHR-39120: UX plans to move the Journey activity flow tile to the top of the report. Update the tile order in this page when that ships. -->

Use the **[!UICONTROL View Report]** button on a live or finished person journey to see how that journey is performing, including person status, engagement, email performance, and activity flow.

_To view the report:_

1. Open a **[!UICONTROL Live]** or **[!UICONTROL Finished]** person journey from the _[!UICONTROL Person journeys]_ list.
1. In the journey header, select **[!UICONTROL View Report]**.

   ![Person journey canvas with the View report button highlighted in the journey header.](./assets/reports-person-journey-view-report.png){width="600" zoomable="yes"}

You can [change the date range](./reports-overview.md#change-the-date-range) for the report.

Select **[!UICONTROL Share]** at the top of the report to download or schedule an export of the data. See [_Export a report_](./reports-overview.md#export-a-report) in the Reports overview.

![Person Journey Individual report showing journey status, completion trend, and engagement tiles.](./assets/reports-individual-journey.png){width="700" zoomable="yes"}

## Filters {#filters}

The report filters are scoped to the current journey.

* **[!UICONTROL Journey Name (Event)]** - Pre-set to the journey you opened the report from.
* **[!UICONTROL Persona (Event)]** - (_Not yet supported_) Filter the report to people who match a specific [derived persona](../audiences/personas.md#filter-by-derived-persona). Default is [!UICONTROL No filter].

Select **[!UICONTROL Reset all]** to clear the _[!UICONTROL Persona (Event)]_ filter and return to the default view.

## Person status and engagement {#person-status-and-engagement}

This section presents four tiles:

* **[!UICONTROL Status of persons in the journey]** - Breaks down persons in the journey into _[!UICONTROL Completed]_ and _[!UICONTROL In Progress]_ categories, with corresponding percentages.
* **[!UICONTROL Completed persons over time]** - A line chart that tracks the number of persons who completed the journey over the selected date range.
* **[!UICONTROL Engaged vs not engaged persons]** - Breaks down persons in the journey into _[!UICONTROL Engaged]_ and _[!UICONTROL Not engaged]_ categories, with corresponding percentages.
* **[!UICONTROL Engaged persons]** - The total number of persons who qualify as engaged in the journey.

## Email performance {#email-performance}

The [!UICONTROL Email performance] table shows delivery and engagement metrics for each email sent in the journey. For the same email metrics across all journeys, see the [Email Engagement report](./email-engagement-report.md).

![Email performance table showing sent, delivered, opened, and clicked metrics for one email.](./assets/reports-individual-journey-email-performance.png){width="700" zoomable="yes"}

[!UICONTROL Email performance] table columns:

* [!UICONTROL Email Name] - Name of the email.
* [!UICONTROL Sent] - Number of emails sent.
* [!UICONTROL Delivered] - Number of emails delivered.
* [!UICONTROL % Delivered] - Number of delivered emails divided by the number sent.
* [!UICONTROL Opened] - Number of times recipients opened the email.
* [!UICONTROL % Opened] - Number of opened emails divided by the number delivered.
* [!UICONTROL Clicked] - Number of times recipients clicked a link in the email.
* [!UICONTROL % Clicked] - Number of clicked emails divided by the number delivered.

## Journey activity flow {#journey-activity-flow}

The [!UICONTROL Journey activity flow] visualization shows the path that persons take through the journey, starting from the _[!UICONTROL Add Person to Journey]_ activity. Each node shows the number of path views for that activity.

![Journey activity flow visualization showing path views from Add Person to journey through email delivery.](./assets/reports-individual-journey-activity-flow.png){width="700" zoomable="yes"}
