---
title: Coworker Skills
description: Review Coworker skills in Marketo Optimizer for journeys, audiences, programs, content, analytics, and AI decisioning. Learn what each skill can do for you.
autotag-review: '2026-09-22T14:02:17.516Z'
TQID: 'https://experienceleague.adobe.com/nNFB9UEghfqVvnBrNtTDnpnLUKKKMAU2nY1Pqt0KkUQ'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
---

# Coworker skills

A _skill_ is a packaged workflow that Coworker can execute. Skills are the components behind both the `/` menu and natural-language requests. Each skill bundles step-by-step instructions and the specific tools needed for one task, such as publishing a journey, comparing two people lists, or building a scoring model.



The classification for each skill reflects the kind of action it performs:

* _Search_ skills look up or list existing records.
* _Analyze_ skills review, compare, or report on data without changing it.
* _View_ skills display a read-only report or metric.
* _Edit_ skills change an existing object's settings or content.
* _Create_ skills create a new object.

## Journeys {#journeys}

These skills create, publish, debug, and manage person journeys.

| Skill | What it does | Type |
| --- | --- | --- |
| **Journey Observability** | Debug and monitor person movement through a journey, including paths, timing, splits, stalls, and dwell time. See _[Debug and monitor journey progression](./journey-observability.md)_. | Analyze |
| **Journey Traffic Control** | Simulate how profiles distribute across all active journeys. | Analyze |
| **Journey Publish** | Publish, launch, or schedule a journey, including start mode, dates, and confirmation. | Edit |
| **Journey Stop** | Abort a running journey to stop it immediately, or close it to wind it down gracefully. | Edit |
| **Journey Edit Dates** | Change the start or end date on a draft, scheduled, or live journey without republishing it. | Edit |
| **Journey Reentry** | Configure re-entry settings for a journey, including whether re-entry is allowed, the cooldown delay, and the maximum entry count. | Edit |
| **Journey Creation** | Create and edit person journeys using natural-language requests. | Create |
| **Webinar to Journey** | Set up a promotional journey before a webinar and a follow-up journey after it. | Create |

## Audience and people lists {#audience-people-lists}

These skills build and manage people lists and audience definitions.

| Skill | What it does | Type |
| --- | --- | --- |
| **Browse Dynamic List Members** | Browse and filter the members of a dynamic or static people list. | Search |
| **People List Comparison** | Compare two people lists and show overlapping members. | Analyze |
| **Remove from Static List** | Remove members that match natural-language criteria from a static list. | Edit |
| **Audience Creation** | Adapt a [!DNL Marketo Engage] smart list, create a people list, or add or update its rules. See _[Create audiences for programs](./audience-creation.md)_. | Create |

## Programs, folders, and channels {#programs-folders-channels}

These skills manage program structure, tokens, and channel configuration.

| Skill | What it does | Type |
| --- | --- | --- |
| **Create Program** | Create programs from a campaign brief. See _[Create a program from a brief](./program-from-brief.md)_. | Analyze |
| **Adapt Program** | Generate migration stories from [!DNL Marketo Engage] programs for [!DNL Marketo Optimizer] adaptation. | Analyze |
| **Asset Tokens** | Create and manage `{{my.token}}` values on programs, folders, and journeys. | Edit |
| **FCS Channels** | Create, publish, stop, and clone channels in the Channels Service, including XDM schemas and provisioning. | Edit |
| **Folder Creation** | Create organizational folders in the asset tree. | Create |
| **WhatsApp Inline Campaign** | Create and publish a [!DNL WhatsApp] inline campaign on a journey node. | Create |
| **Marketing Program Creation** | Create a full program, including subfolders, tokens, people lists, and journeys. | Create |
| **Program and Journey Batch Creation** | Create multiple program and journey pairs in a single batch request. | Create |

## Email and landing pages {#email-landing-pages}

These skills create and manage emails, forms, and landing pages.

| Skill | What it does | Type |
| --- | --- | --- |
| **List Forms** | List forms and view their details and fields. | Search |
| **List Landing Pages** | List landing pages, view their details, and manage their draft or published state. | Search |
| **Email Audit** | Audit an email against its target group, including persona inference and a brief plus section-by-section review. | Analyze |
| **Email Authoring** | Create or update a journey email node, including composing from a brief or PDF, linking it to a node, and writing content. | Edit |
| **Form Authoring** | Create or update a standalone lead-capture form, publish it, and optionally embed it in a landing page. | Create |
| **Landing Page Authoring** | Create or update a landing page from a brief, including content planning, template selection, filling slots, and adding a form, then publish it. Also attach a published landing page as a call-to-action link on an email. | Create |
| **Email Rendering Check** | Check an email for [!DNL Microsoft Outlook] rendering issues and automatically fix what it can. | Edit |

## Content personalization {#content-personalization}

This skill browses templates and personalizes email content for different personas.

| Skill | What it does | Type |
| --- | --- | --- |
| **Content Personalization** | Browse and preview templates, then edit content or generate variants. See _[Personalize email content by persona](./personalize-content.md)_. | Create |

## Analytics and optimization {#analytics-optimization}

These skills report on performance and configure send-time optimization and scoring models.

| Skill | What it does | Type |
| --- | --- | --- |
| **Surface Analytics** | Generate analytics reports from natural-language requests, covering activity trends, email performance, lead and account data, segment and list membership, and journey metrics. Report data refreshes every two hours. See _[Generate analytics reports](./surface-analytics.md)_. | Analyze |
| **Send Time Report** | View the send-time optimization (STO) performance report at the journey level or for an individual email node. | Analyze |
| **Email STO Simulation** | Preview the predicted send time, audience quality, and engagement heatmap for an email node before enabling STO. | Analyze |
| **Send Time Optimization** | Enable or disable STO on a journey email node. | Edit |
| **Engagement Configuration** | Show and edit the activity weights for the person engagement score model. | Edit |
| **Scoring Studio** | List and view scoring models, then build and publish new ones. See _[Create custom scoring models](./lead-scoring-model.md)_. | Create |

## AI decisioning and intent {#ai-decisioning-intent}

These skills assess data readiness for AI decisioning and configure intent scoring.

| Skill | What it does | Type |
| --- | --- | --- |
| **AI Decisioning Health** | Report whether an organization's data is ready for AI decisioning, including lead availability, persona distribution, story richness, and intent. | Analyze |
| **Analyze Intent** | Query and validate lead-level intent ranking, trends, and the product and keyword taxonomy. | Analyze |
| **Intent Configuration** | Show and edit the activity weights for the person intent score model. | Edit |

## Knowledge and skill management {#knowledge-skill-management}

These skills answer product questions and let you build new custom skills.

| Skill | What it does | Type |
| --- | --- | --- |
| **Product Knowledge** | Answer how-to and conceptual questions using [!DNL Marketo Optimizer] documentation published on Experience League. | Search |
| **Skill Creation** | Create, test, and refine new custom skills. | Create |
