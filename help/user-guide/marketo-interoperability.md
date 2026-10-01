---
title: Interoperability with Marketo Engage
description: Learn what Marketo Optimizer shares with Marketo Engage, including data, activities, and audiences, and how to send email from either product in your journeys.
role: User, Admin
autotag-review: '2026-10-01T18:40:01.444Z'
TQID: 'https://experienceleague.adobe.com/7TB6JG9yiUT-l0VevNW4tvwieCyFjOypZwI0SlUzmmY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---

# Interoperability with Marketo Engage

[!DNL Adobe Marketo Optimizer] and [!DNL Adobe Marketo Engage] share data, some activities, and audiences. They keep assets separate. Understand what each product shares to decide where to build and send your marketing.

## Shared between the products {#shared}

* [!DNL Marketo Engage] leads and activities flow into [!DNL Marketo Optimizer] automatically.
* Journeys can listen for [!DNL Marketo Engage] activities.
* Event based audiences can include people who perform [!DNL Marketo Engage] activities.
* Journey actions can interact with [!DNL Marketo Engage]. You can add people to or remove them from a [!DNL Marketo Engage] list and request a [!DNL Marketo Engage] campaign.
* [!UICONTROL Scoring Studio] scores people against [!DNL Marketo Engage] and [!DNL Marketo Optimizer] activities. You can use the scores in [!DNL Marketo Engage].
* Both products share IP addresses and subdomains.
* Unified conversational reporting covers both products.

## Kept separate {#separate}

* **Assets:** Emails, templates, programs, and images live in separate repositories.
* **Activities:** [!DNL Marketo Optimizer] activities are not shared back to [!DNL Marketo Engage].
* **Fields and limits:** Persona fields that [!DNL Marketo Optimizer] derives are not available in [!DNL Marketo Engage]. Communication limits are set separately in each product.

For synchronization details, see [Entity synchronization](./data-architecture.md#entity-sync).

## Send email from Marketo Engage {#send-from-marketo}

Use this approach to run journeys, wait steps, and AI decisioning in [!DNL Marketo Optimizer] while [!DNL Marketo Engage] sends every email.

1. In [!DNL Marketo Optimizer], build a journey that includes wait steps and AI decisioning.
1. For each send step, add the **[!UICONTROL Request Marketo Engage campaign]** action and select a matching [!DNL Marketo Engage] campaign.
1. Optional: Add a default, overarching program in [!DNL Marketo Engage] to aggregate success reporting across the journey.

For action details, see [Take an action node](./marketing/action-nodes.md).

[!DNL Marketo Engage] sends the email through your existing channel settings. Because [!DNL Marketo Engage] sends the email, you do not configure channels or emails in [!DNL Marketo Optimizer]. In addition:

* Sends, opens, and clicks are recorded in [!DNL Marketo Engage].
* Unsubscribe management and email governance apply in [!DNL Marketo Engage].
* Email activity feeds your existing [!DNL Marketo Engage] scoring campaigns.
* Activity triggered Salesforce sync campaigns run as expected.
* Each send maps to a [!DNL Marketo Engage] campaign, so you track program membership per email campaign and report in familiar programs.

## Send email from Marketo Optimizer {#send-from-optimizer}

Use this approach to build the journey and send email entirely in [!DNL Marketo Optimizer]. [!DNL Marketo Engage] remains the system of record for the hand-off to your customer relationship management (CRM) system.

1. Set up the email channel. Create email templates, and configure the IP address and subdomain, unsubscribe links, and landing pages. See [Email deliverability](./start/email-deliverability.md).
1. Set communication limits in [!DNL Marketo Optimizer]. Shared communication limits are not available.
1. Build the journey with audiences, AI decisioning, and next best path.
1. Send email from [!DNL Marketo Optimizer]. [!DNL Marketo Optimizer] records the activities.
1. Score people in [!UICONTROL Scoring Studio] to create one model across [!DNL Marketo Engage] and [!DNL Marketo Optimizer] activity. See [Scoring Studio](./labs/scoring-studio.md).

Unsubscribes synchronize to [!DNL Marketo Engage] automatically through shared fields. [!DNL Marketo Optimizer] email activity is not sent back to [!DNL Marketo Engage], but [!UICONTROL Scoring Studio] still uses it.

### Hand off leads to sales {#hand-off}

[!DNL Marketo Optimizer] has no direct CRM integration. Route leads through [!DNL Marketo Engage] with one of these methods:

* **Score based:** The score field appears in [!DNL Marketo Engage], and a smart campaign syncs the lead to your CRM.
* **Activity based:** A [!DNL Marketo Optimizer] journey listens for the activity and adds the lead to a [!DNL Marketo Engage] smart campaign.
* **Program membership:** The journey sits in a [!DNL Marketo Optimizer] program, so you track status from start to finish.
