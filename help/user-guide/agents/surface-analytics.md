---
title: Generate Analytics Reports
description: Learn how to use the Surface Analytics skill in Coworker chat to generate activity, email, lead, segment, and journey reports from natural language prompts.
autotag-review: '2026-09-21T14:58:26.479Z'
TQID: 'https://experienceleague.adobe.com/BSDEihjdpz-YZjMWrYTmIuyjqtcjRHRrJdz4xPFZbHU'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Generate analytics reports

The [_Surface Analytics_ skill](./skills.md#analytics-reporting) in [!DNL Adobe Marketo Optimizer] answers natural language questions about your data. Use it in the [Coworker chat interface](./chat-interface.md) to explore activity trends, email performance, lead and account data, segment and list membership, and journey metrics. Results return as charts and tables, so you don't need to build a query or dashboard manually.

* **Skill** - `surface-analytics`
* **Invocation** - Ask a question in natural language, or use a slash command to run the Surface Analytics skill. For example: _"Show me daily activity counts for the last 30 days."_
* **Reads from** - [!DNL Marketo Optimizer] analytics data; reads [!DNL Marketo Engage] analytics data for questions that span both products

>[!NOTE]
>
>Report data refreshes every two hours. Results may not reflect activity from the last two hours.

## View activity trends {#activity-trends}

Ask about daily or weekly activity counts, and break results down by activity type or product area.

* _"Show me daily activity counts for the last 30 days."_
* _"What are the top activity types this week?"_
* _"Break down last month's activity by app area."_

## Check email performance {#email-performance}

Ask about send volume, open and click rates, bounces, and unsubscribes for your email programs.

* _"What's the email open rate by journey?"_
* _"Show me click rates for the last 90 days."_
* _"How many unsubscribes did we get last week?"_

## Analyze lead and account data {#lead-account-data}

Ask about lead score distribution, persona breakdowns, and geographic or firmographic rollups.

* _"Show me the score distribution across leads."_
* _"How many people are in each account?"_
* _"Break down leads by persona."_

## Review segment and list membership {#segment-list-membership}

Ask who belongs to a specific list or segment.

* _"How many people are in the Q1 Nurture list?"_
* _"Which segment has the most members?"_

## Explore journey metrics {#journey-metrics}

Ask about journey membership, completion rates, node traversal, and funnel analysis.

* _"What's the completion rate for the Demo Follow-up journey?"_
* _"How many people are in each node of the LeadNurtureJourney?"_

## Ask questions across products {#cross-product}

Surface Analytics can answer questions that span both [!DNL Marketo Engage] and [!DNL Marketo Optimizer] data in a single prompt.

* _"What's my top-performing email in LumaSecure and in LumaStorage?"_

## Limitations {#limitations}

| Limitation | Detail |
|---|---|
| Editing or creating records | Not supported. Surface Analytics only reads and reports on existing data. |
| Human-readable names in results | Not always available. Some reports show an internal ID, such as a journey or email ID, instead of a name. |
| Duplicate report cards | A single question can occasionally return more than one report card for the same result. |
