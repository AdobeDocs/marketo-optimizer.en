---
title: High-Level Architecture
description: Learn about the data architecture connecting Marketo Optimizer and Marketo Engage, including bidirectional sync, entity latency, and tenant data isolation.
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

# High-level architecture

[!DNL Adobe Marketo Optimizer] integrates with [!DNL Adobe Marketo Engage] to deliver a 360-degree view of B2B leads. A bidirectional, trusted sync keeps [!DNL Marketo Engage] and [!DNL Marketo Optimizer] aligned, giving both platforms a single, shared view of People, Companies, Custom Objects, and Activities. High-performance, near-real-time data flow ensures records stay current and actionable, so campaigns and journeys can respond to leads the moment they engage.

## Data foundation

[!DNL Marketo Optimizer] and [!DNL Marketo Engage] share a common data foundation that keeps them synchronized while feeding downstream analytics.

![Marketo Optimizer and Marketo Engage architecture diagram that shows how the two products' services, runtimes, and data stores connect across Microsoft Azure and AWS](./assets/marketo-optimizer-architecture.svg)

At a high level:

* **[!DNL Marketo Engage] Core** is the definitive source for lead and custom object data, ensuring data integrity at the point of capture.
* A **data broker layer** coordinates how data moves between [!DNL Marketo Engage] and [!DNL Marketo Optimizer], aggregating shared and replicated data into an operational, ready-to-use environment. This entire exchange runs inside a single shared AWS Aurora instance, forming the closed-loop foundation for high-scale B2B orchestration.
* **Activities** follow a defined path: they are first written to the [!DNL Marketo Engage] database and indexed in Apache SOLR for fast in-product search, then published to the activity pipeline so [!DNL Marketo Optimizer] has instant awareness. The journey runtime processes that activity and writes it to Snowflake, transforming operational data into an analytics-ready state. From there, activity is replicated into [!DNL Adobe Experience Platform] datasets and [!DNL Adobe Customer Journey Analytics] to power reporting.
* Different entity types synchronize at different speeds and directions to balance freshness against system integrity:

| [!DNL Marketo Engage] entity | Sync direction | Latency |
| --- | --- | --- |
| Lead | Bi-directional | < 1 sec |
| Company | Bi-directional | < 1 sec |
| Custom object | Uni-directional | < 5 sec |
| Activity | Uni-directional | < 5 sec |
| Program membership | Not synchronized | — |
| Assets | Not synchronized | — |

Leads and companies update instantly in both directions without creating duplicate data copies. Custom Objects replicate within seconds, so schema updates in [!DNL Marketo Engage] are immediately actionable in an active journey. Program Membership and Assets are intentionally excluded from sync to preserve system speed and integrity.

This near-zero latency design means analytics dashboards and downstream systems are fed on a near-real-time basis, enabling live campaign optimization and fast follow-up on high-priority leads.

### Data isolation and tenancy

* Customer data is shared between [!DNL Marketo Engage], [!DNL Marketo Optimizer], and [!DNL Experience Platform] as part of the product data synchronization and analytics architecture.
* Data is logically isolated per tenant and protected by Adobe security controls.
* Data is transferred over secure, encrypted channels and stored within Adobe-managed services using industry-standard encryption and access controls.
* Depending on the data type, information may be synchronized between [!DNL Marketo Engage] and [!DNL Marketo Optimizer] or replicated to [!DNL Experience Platform] to support reporting and analytics capabilities, while maintaining security and tenant isolation.
