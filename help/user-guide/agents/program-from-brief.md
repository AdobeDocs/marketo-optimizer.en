---
title: Create a Program from a Brief
description: Use the Program Creation skill in Marketo Optimizer to build programs, tokens, people lists, and journeys from a campaign brief.
---
# Create a program from a brief

In [!DNL Adobe Marketo Optimizer], [_program_](../marketing/programs.md) is the top-level container for journeys, people lists, tokens, and configuration within a campaign. From the [chat interface](./chat-interface.md), the Program Creation skill builds that entire structure end-to-end from your brief — the program itself, subfolders, tokens, people lists, and person journeys — in one guided conversation.

* **Skill** - `program-creation`
* **Invocation** - Upload a brief and enter _Create a program from this brief_ / _Build a program from brief_, or describe the campaign directly
* **Reads from / writes to** - [!DNL Marketo Optimizer]; also reads program-type configuration from your tenant

## Brief upload

Click the _Attach_ icon in the chat input to upload the file, and then describe what you want. The brief's text is extracted and handed to Coworker as context (you'll see a "Campaign Brief uploaded: filename (NkB)" indicator in the chat).

### Supported file types

| Format | Behavior |
|---|---|
| `.txt`, `.md` | Read directly in the browser |
| `.pdf`, `.docx`, `.xlsx`, `.json`, `.csv` | Sent to the backend text-extraction service |

A file with a name containing *brief* is automatically tagged as a campaign brief; otherwise Coworker infers it from context.

### Size limit

Brief text is truncated to approximately 30,000 characters (~7.5K tokens) before reaching Coworker. Very long briefs are cut off at that point (indicated by a `(truncated to 29KB)` note). Put essential campaign details up front.

## Recommended brief contents

The flow intake reads the brief for the following inputs — include as many as possible:

* Program name and a short description / purpose
* Program type signal (such as tradeshow, event, webinar, roadshow, conference, or nurture)
* Audience criteria for the people lists
* Journey design — count, entry criteria, touchpoints/timing, and a go-live date
* Tokens (reusable values such as event date, venue, subject line)

Coworker requests anything that is missing before building.

## Build phases

The skill runs in three phases: **INTAKE → APPROVE → BUILD**. Nothing is created until you approve.

### Intake

Coworker extracts the following from the brief and prompts for anything missing:

* Program name
* Parent folder (defaults to workspace root if unspecified)
* Description
* Program type (inferred from brief wording where possible)
* Tokens to create (name, type, value)
* People list audience criteria
* Journeys — count, entry criteria, touchpoints, go-live date

### Approve

Coworker presents a confirmation summary before proceeding:

   `I'll create {program} in folder {id}, with {N} token(s), {N} dynamic people list(s), and {N} journey(s). Shall I proceed?`

No creation tool is called until you respond with a clear go-ahead (such as _proceed_, _go ahead_, _build it_, _approved_, and _yes_).

### Build

The build steps run in a fixed order; each depends on IDs produced by the previous step.

| Step | Description | Tools | Output |
|---|---|---|---|
| **1. Folder** | Resolves the parent folder by name or uses workspace root; can create a new subfolder | `getRootTree`, `browseFolders`, `createFolder` | Folder name + ID |
| **1.5. Program type** | Looks up tenant program types and picks the match for the brief | `browseProgramTypes` | Type name + `programTypeId` |
| **2. Program** | Creates the Program under the resolved folder, bound to the chosen type | `createProgram` | Program name, ID, type |
| **3. Tokens** | Creates each `my.*` token on the program | `createProgramToken` | Token names |
| **4. People lists** | Generates attribute-based rules from audience criteria and creates the dynamic people list | `generate_ruleset`, `createSmartListWithRules` | List name + `smartListId` |
| **5. Journeys** | Creates each person journey with a person audience entry node wired to the Step 4 list | `create_journey` | Journey names, IDs |
| **6. Publish** | Publishes or schedules the journey if a go-live date is set and confirmed | `publish_journey_with_dates` | Live/scheduled journey |
| **7. QA** | Optional validation preview and full QA check | `qa_program_preview`, `qa_program` | Pass/fail/warnings report |

**_Step dependencies:_**

* The program ID (Step 2) is required before tokens, lists, or journeys can be attached.
* The `smartListId` from Step 4 is passed into `create_journey` in Step 5 — omitting it leaves the journey's audience entry node empty.
* The journey prompt always begins _Start with a Person audience node as the entry point_ to ensure a populated entry node.

## Output assets

### Program

The top-level container. Its detail view exposes the following tabs:

| Tab | Content |
|---|---|
| **Overview** | Name, description, program type, status, folder location, timestamps |
| **Attributes** | Type-defined custom fields (only if the program type enables them) |
| **Tokens** | `my.*` tokens scoped to this program |
| **Journeys** | Journeys contained within the program |

### Tokens

Reusable `my.*` values scoped to the program (e.g. `my.eventDate`). Each has a type — one of `text`, `date`, `rich text`, `score`, or `number` — and a value. They resolve inside emails and content within the program's scope.

### People List

A dynamic (smart) people list built from audience criteria via generated, attribute-based rules, created under the program.

### Journey

A person journey starting with a Person audience entry node bound to the Step 4 people list, followed by the touchpoints from the brief (for example, _send welcome email after 1 day, follow-up after 3 days_). If a go-live date is set, the journey can be published immediately or scheduled.

## Program type resolution

Programs are **permanently bound** to a tenant-defined program type at creation — this cannot be changed afterward. The flow resolves the type explicitly via `browseProgramTypes` in every case.

| Case | Behavior |
|---|---|
| **Multiple types available** | Matches brief wording to a type (such as tradeshow/booth/expo = *Tradeshow*/*Event*; webinar = *Webinar*/*Event*; nurture/drip = *Nurture*; no clear signal = *Default*). If no match is found, Coworker lists available types and asks. |
| **Default-only tenant** | Uses *Default* and notes that an admin can add custom [program types](../admin/program-types.md). |
| **No types configured** | Stops — creation would fail. Prompts an admin to provision program types before retrying. |

## Defaults

| Setting | Default |
|---|---|
| **Folder** | Workspace root (if no folder is specified) |
| **Program type** | *Default* (if no brief signal and no manual selection) |
| **Personalization attributes** | Derived Persona, Derived Intent, Engagement Tier included by default (opt-out available) |
| **Publishing** | Not automatic for future go-live dates — noted as a manual `ACTIVATE journey by {date}` step; immediate publish only when launching now and confirmed |
| **Approval gate** | No asset is created before explicit approval |

## Limitations

| Limitation | Detail |
|---|---|
| **Brief length cap** | ~30K characters; truncated briefs lose trailing content — put essentials first |
| **Immutable program type** | Cannot be changed after creation; verify the correct type before approving |
| **Required internal fields** | `parent` and `programTypeId` are always set; omitting `parent` causes access-denied; omitting type silently falls back to *Default* |
| **Journey requires people list** | The `smartListId` from Step 4 is mandatory for Step 5; the flow enforces this |
| **Async list membership** | Static (from criteria) lists populate over several minutes — not instant |
| **Error handling** | Tool failures are reported with the exact error; Coworker prompts to confirm input and retry |
| **Name collisions** | Not auto-resolved — a different name will be requested |
| **Scope** | Marketo Optimizer only; [!DNL Marketo Engage] users should use the separate program-creation / program-planning skills |


## QA check

After the build completes, Coworker offers:

> "Would you like me to run a QA check to validate everything before launch?"

Confirm to run `qa_program_preview` followed by `qa_program`. The process returns a report of checks passed, failed, and any warnings, along with recommended next steps.
