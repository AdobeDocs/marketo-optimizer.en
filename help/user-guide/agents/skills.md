---
title: Coworker Skills
description: Review Coworker skills in Marketo Optimizer — packaged workflows for programs, journeys, audiences, scoring, content, and send-time optimization.
---
# Coworker skills

A _skill_ is a packaged workflow the agent knows how to run — the building blocks behind both the `/` menu and natural-language requests. Each skill bundles step-by-step instructions and the specific tools needed for one job (for example, "publish a journey", "compare two people lists", "build a scoring model"). 

>[!NOTE]
>
>Each skill is classified according to whether the skill mutates the [!DNL Marketo Optimizer] or [!DNL Marketo Engage] state (**Write**), only queries/analyzes/generates (**Read**), or has co-equal query + mutation functions (**Read+Write**).

## Programs and planning {#programs-planning}

| Skill | What it does | Access | Product surface | Impact / data flow |
|---|---|---|---|---|
| `falco-program-creation` | End-to-end [!DNL Marketo Optimizer] program creation — program, subfolders, tokens, lists, journeys. | Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer]. See _[Create a program from a brief](./program-from-brief.md)_. |
| `adapt-program` | Generate migration stories from [!DNL Marketo Engage] programs for [!DNL Marketo Optimizer] adaptation. | Read | [!DNL Marketo Optimizer] | Reads [!DNL Marketo Engage], writes [!DNL Marketo Optimizer] |
| `folder-creation` | Create organizational folders in the asset tree. | Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |
| `program-creation` *(Build Programs)* | Create Marketo programs from a campaign brief. | Write | [!DNL Marketo Engage] | Reads + writes [!DNL Marketo Engage] |
| `program-planning` *(Plan Campaigns)* | Transform briefs into setup/implementation documents. | Read | [!DNL Marketo Engage] | Reads [!DNL Marketo Engage] |
| `program-qa` *(Validate Programs)* | Validate/audit programs (rules-only, test plan, or brief). | Read | [!DNL Marketo Engage] | Reads [!DNL Marketo Engage] |

## Journeys {#journeys}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `journey-creation` | Create and edit person journeys from natural language. | Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |
| `journey-edit-dates` | Change a journey's start/end date without publishing. | Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |
| `journey-publish` | Publish/launch/schedule people journeys. | Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |
| `journey-stop` | Abort, close, stop, halt, or kill journeys. | Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |
| `journey-reentry` | Configure re-entry: allow/disallow, cooldown, max entries. | Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |
| `journey-trafficcontrol` | Run a traffic-control simulation showing profile routing. | Read | [!DNL Marketo Optimizer] | Reads [!DNL Marketo Optimizer] (simulation) |
| `journey-observability` | Debug/monitor progression — paths, timing, splits, stalls, dwell. | Read | [!DNL Marketo Optimizer] | Reads [!DNL Marketo Optimizer] + [!DNL Marketo Engage] (static-list check) |

## Audiences and people {#audiences-people}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `audience-creation` | Adapt a [!DNL Marketo Engage] smartlist, create a people list, or add/update rules. | Write | [!DNL Marketo Optimizer] | Reads [!DNL Marketo Engage] + reads/writes [!DNL Marketo Optimizer].  See _[Create audiences for programs](./audience-creation.md)_. |
| `people-list-comparison` | Compare two people lists and show overlapping members. | Read | [!DNL Marketo Optimizer] | Reads [!DNL Marketo Optimizer] |
| `import-leads` | Inspect CSV data quality and commit imports to [!DNL Marketo Engage]. | Read+Write | Both | Reads + writes [!DNL Marketo Engage] |
| `lead-investigation` *(Investigate Leads)* | Investigate a lead's activity, scoring, qualification, lifecycle. | Read | [!DNL Marketo Engage] | Reads [!DNL Marketo Engage] |

## Content and channels {#content-channels}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `content-personalization` | Browse/preview templates and edit content / generate variants. | Read+Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer]. See _[Personalize email content by persona](./personalize-content.md)_. |
| `asset-tokens` | Full token CRUD on programs/folders/journeys. | Read+Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |
| `fcs-channels` | Channel lookups and CRUD + publish/stop/delete. | Read+Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |

## Scoring and signals {#scoring-signals}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `scoring-studio` | List/get scoring models and build/publish them. | Read+Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] (scoring service); reads [!DNL Marketo Engage] lead fields/activity types. See _[Create custom scoring models](./lead-scoring-model.md)_. |
| `engagementconfiguration` | Show engagement config and edit/update weights. | Read+Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |
| `intentconfiguration` | Show intent config and set/update weights. | Read+Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |
| `intent-query` | Query and explain intent scores by person/segment/list. | Read | [!DNL Marketo Optimizer] | Reads [!DNL Marketo Optimizer] |

## Send-time optimization {#sto}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `send-time-optimization` | Check STO status and enable/disable on an email node. | Read+Write | [!DNL Marketo Optimizer] | Reads + writes [!DNL Marketo Optimizer] |
| `send-time-report` | Fetch/display the STO performance report. | Read | [!DNL Marketo Optimizer] | Reads [!DNL Marketo Optimizer] |

## Knowledge {#knowledge}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `product-knowledge` | Answer how-to/concept questions from [!DNL Marketo Optimizer] documentation on Experience League. | Read | Both | Reads external docs — no product data |

## Cross-backend {#cross-backend}

These skills span more than one backend:

- **`adapt-program`** — `gather_program_assets` reads [!DNL Marketo Engage] (`get_program`, `get_smart_campaign`, `list_emails`), then writes via `falcomcp_create_journey` — classic cross-backend.
- **`audience-creation`** — reads [!DNL Marketo Engage] smart lists (`get_smart_list` / `get_smart_campaign`), then writes [!DNL Marketo Optimizer] people lists.
- **`journey-observability`** — [!DNL Marketo Optimizer] reads plus a `check_lead_in_marketo_static_list` [!DNL Marketo Engage] read.
- **`scoring-studio`** — reads [!DNL Marketo Engage] lead fields/activity types alongside [!DNL Marketo Optimizer] scoring service.

All `falco-mcp_*` and journey/token/scoring/STO/FCS tools hit [!DNL Marketo Optimizer] services; CSV/program/lead tools hit [!DNL Marketo Engage].

