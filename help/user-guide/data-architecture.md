---
title: Data Architecture
description: Learn how Marketo Optimizer and Marketo Engage share data, including entity sync direction and latency, activity data flow, and sandbox based data isolation.
role: User, Admin
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---

# Data architecture

[!DNL Adobe Marketo Optimizer] integrates with [!DNL Adobe Marketo Engage] to deliver a comprehensive view of B2B leads. A bidirectional, trusted sync keeps both products aligned, so they share one view of people, companies, custom objects, and activities. [!DNL Marketo Engage] remains the authoritative source for person data. Each [!DNL Marketo Optimizer] instance is paired with one [!DNL Marketo Engage] instance.

## Data foundation {#data-foundation}

[!DNL Marketo Optimizer] and [!DNL Marketo Engage] share a common data foundation that keeps them synchronized while feeding downstream analytics.

![Marketo Optimizer and Marketo Engage architecture diagram that shows how the two products' services, runtimes, and data stores connect across Microsoft Azure and AWS](./assets/marketo-optimizer-architecture.svg)

At a high level:

* **[!DNL Marketo Engage]** is the definitive source for lead and custom object data, which ensures data integrity at the point of capture.
* A **data broker layer** coordinates how data moves between the two products. It aggregates shared and replicated data into an operational database that is ready to use. The entire exchange runs inside a single Aurora MySQL cluster.
* **[!DNL Marketo Optimizer]** is the authoritative source for the journey activities that it runs.

## Entity synchronization {#entity-sync}

Each entity type synchronizes in the direction and at the speed that best protects data integrity.

| [!DNL Marketo Engage] entity | Sync direction | Latency |
| --- | --- | --- |
| Lead | Bidirectional | Under 1 second |
| Company | Bidirectional | Under 1 second |
| Custom object | Unidirectional | Under 5 seconds |
| Activity | Unidirectional | Under 5 seconds |
| Program membership | Not synchronized | Not applicable |
| Assets | Not synchronized | Not applicable |

Synchronization works in two ways:

* **Leads, companies, and standard objects:** [!DNL Marketo Engage] owns the person table and shares it through read and write database views. Updates in one product appear in the other right away, and no duplicate copies are created.
* **Custom objects:** Data replicates from [!DNL Marketo Engage] within seconds. Schema updates in [!DNL Marketo Engage] are immediately available to active journeys.

[!DNL Marketo Engage] and [!DNL Marketo Optimizer] do not synchronize program membership or assets. This exclusion preserves system speed and integrity.

>[!NOTE]
>
>Data synchronized to [!DNL Marketo Optimizer] and to the data warehouse is eventually consistent. Timing depends on the underlying change data capture, batch, or stream mechanism.

This near real-time design gives you current data in journeys and reports. You can follow up quickly on high priority leads. You can also use B2B context data, such as product usage and intent, in journey decisions as it changes.

## Activity data flow {#activity-flow}

Activities follow a separate path from other entities. Each activity moves through five stages:

1. **Primary capture:** [!DNL Marketo Engage] writes the activity to its shared database and indexes it in Apache SOLR for fast search within [!DNL Marketo Engage].
1. **Cross-product awareness:** [!DNL Marketo Engage] publishes the activity to the activity pipeline, so [!DNL Marketo Optimizer] receives it immediately.
1. **Analytical transformation:** The journey runtime processes the activity and writes it to Snowflake, which turns operational data into analytics-ready data. All stages so far run in Amazon Web Services (AWS).
1. **Downstream destination:** [!DNL Marketo Optimizer] replicates the activity into [!DNL Adobe Experience Platform] datasets.
1. **Reporting:** The datasets feed embedded [!DNL Adobe Customer Journey Analytics] reports. [!DNL Customer Journey Analytics] can be hosted on Microsoft Azure or AWS. You can also query the datasets with [!DNL Query Service]. See [Experience Platform datasets](./reports/aep-datasets.md).

Journeys and event audiences can use both [!DNL Marketo Optimizer] activities and a subset of [!DNL Marketo Engage] activities. You use both sets in the same way. [!DNL Marketo Optimizer] activities are not sent back to [!DNL Marketo Engage].

Use activities such as form fills, web visits, and email engagement to trigger, filter, and branch person journeys:

* [Event triggers for the Listen for an event node](./marketing/listen-for-event-nodes.md#event-triggers)
* [Event filters for the Listen for an event node](./marketing/listen-for-event-nodes.md#event-filters)
* [Matched person filters for split paths nodes](./marketing/split-merge-paths-nodes.md#matched-person-filters)
* [Event based audiences](./audiences/event-based-audiences.md)

## Data isolation and sandboxes {#data-isolation}

[!DNL Marketo Engage], [!DNL Marketo Optimizer], and [!DNL Experience Platform] share customer data as part of this architecture. Adobe logically isolates your data from other tenants by using [!DNL Experience Platform] sandboxes. Data moves over secure, encrypted channels. Adobe stores it in Adobe Managed Services with industry standard encryption and access controls.

Each [!DNL Marketo Optimizer] instance has a dedicated product card in the [!DNL Adobe Admin Console] and a dedicated sandbox. Adobe provisions both automatically, so you do not create a sandbox. The sandbox name uses the pattern `mktoaep<prefix>`, where the prefix is your [!DNL Marketo Engage] prefix. If you use [!DNL Marketo Optimizer] with more than one [!DNL Marketo Engage] instance, each instance has its own product card and sandbox.

[!DNL Marketo Optimizer] is available only in this sandbox, even if your organization has other sandboxes.

Provisioning does not assign sandbox access. Roles typically have access to the default `prod` sandbox, but [!DNL Marketo Optimizer] does not use it. Explicitly assign the dedicated sandbox to each [!DNL Experience Platform] role, or users cannot work in [!DNL Marketo Optimizer]. Use user groups to add and remove users without repeating role setup. For the full procedure, see [User access and permissions](./start/user-management.md).

[!DNL Marketo Optimizer] also uses [!DNL Experience Platform] services in the background. These include the schema registry, destinations for paid media export, access control, and [!DNL Customer Journey Analytics]. You do not set up schemas or namespaces. [!DNL Marketo Optimizer] does not require [!DNL Real-Time Customer Data Platform], Real-Time Customer Profile, or segmentation.

>[!WARNING]
>
>Do not delete the dedicated [!DNL Marketo Optimizer] sandbox. Deletion is permanent and cannot be undone. Reprovision [!DNL Marketo Optimizer] to recover.
