---
title: Create Audiences for Programs
description: Use the Audience Creation skill in Marketo Optimizer to create people lists, adapt Marketo Engage Smart Lists, and edit list rules in chat.
---
# Create audiences for programs

In [!DNL Adobe Marketo Optimizer], [_people lists_](../audiences/people-lists.md) define the audience for person journeys — either as dynamic filter-based lists that update automatically, or static lists with fixed membership. From the [chat interface](./chat-interface.md), the _Audience Creation_ [skill](./skills.md) builds, adapts, and edits people lists through a guided conversation.

* **Skills** - `audience-creation` and `people-list-comparison`
* **Invocation** - Describe audience criteria directly, upload a [!DNL Marketo Engage] Smart List, or name an existing list to edit
* **Reads from / writes to** - [!DNL Marketo Optimizer]; reads [!DNL Marketo Engage] when adapting Smart Lists

## Supported workflows {#workflows}

Coworker supports three audience creation workflows and determines which one applies from your request. If your intent is ambiguous, it asks before proceeding.

| Workflow | When to use it | Example prompt |
|---|---|---|
| **Create from scratch** | You want a new people list defined by criteria or membership. | _"Create a dynamic list of VPs of Marketing at SaaS companies in North America."_ |
| **Adapt a [!DNL Marketo Engage] Smart List** | You have an existing [!DNL Marketo Engage] Smart List or Smart Campaign and want an equivalent people list. | _"Adapt this Marketo smart list into a people list."_ (attach the asset) |
| **Edit an existing list** | You want to add to or replace the rules on a list you already have. | _"Add a rule to my 'Enterprise Trials' list for lead score over 50."_ |

## Create a people list from scratch {#create-from-scratch}

Before generating anything, Coworker confirms all four of the following. It asks for any that are missing — in a single message.

1. **Rules / criteria** — A plain-language description of who belongs in the list.
1. **Name** — What to call the list.
1. **Location** — Which program the list should live in. Provide a program name and Coworker finds it; if there are multiple matches it asks you to pick.
1. **Type** — Dynamic (filter-based, auto-updating) or static (fixed membership). This is required — Coworker will not guess; if you don't specify, it asks.

### Dynamic lists {#dynamic-lists}

For dynamic lists, Coworker proactively suggests including personalization attributes to make targeting richer. These attributes are **_included by default — you opt out, not in_**:

| Attribute | Why it helps |
|---|---|
| **Derived Persona** | AI-inferred buyer persona for persona-based content targeting. |
| **Derived Intent** | Inferred purchase-intent signals that surface in-market accounts. |
| **Engagement Tier** | Calculated engagement level that prioritizes engaged contacts. |

Tell Coworker if you want to remove any of these before it proceeds.

### Static lists {#static-lists}

* **Static, no criteria** — The list is created empty, ready for you to add members manually.
* **Static from criteria (a snapshot)** — Coworker builds the matching set and copies those people in. Population is asynchronous — Coworker confirms the list was created but notes that it may take a few minutes for people to appear. It will not claim the list is ready immediately.

## Review card {#review-card}

Nothing is created until you approve it. After you describe your criteria, Coworker presents an interactive _People List Creation Review_ card (for adaptations from [!DNL Marketo Engage] lists, the card is titled _People List Conversion Review_).

Each row in the card represents one condition:

| Column | Meaning |
|---|---|
| **Requirements** (or the [!DNL Marketo Engage] list name for adaptations) | Your original request or the source Marketo filter. |
| **(rule)** | The actual attribute-based rule generated for that condition. |
| **Include** | A checkbox to keep or drop that rule. |

**Confidence levels:**

* **High confidence** rows are matched cleanly and checked by default.
* **Low confidence** rows (approximate mappings or anything flagged) are shown with a notice indicator and are unchecked by default.
* Rows the system could not map show **"No equivalent found"** — these have no rule and remain unchecked.

A _Conversion Summary_ tallies _N High Confidence_ and _N Low Confidence_, with a hint: low-confidence rules are unchecked by default; check them to include, or describe the change you want in chat.

**Card actions:**

* **Proceed** — Creates the list using only the checked rules.
* **Describe the changes you want in chat** — Pre-fills the input with _"I want to change: "_ so you can refine; Coworker regenerates and shows a fresh card, keeping rules you had already approved.

You can also type a follow-up at any point (for example, _"also restrict to companies over 500 employees"_) and Coworker regenerates the card.

## Attribute mapping {#attribute-mapping}

When you describe criteria, Coworker translates each condition into a real, known person-level attribute. Three outcomes can appear on the Review card:

1. **Matched (high confidence)** — Your condition maps directly to an attribute (for example, _"email is acme.com"_ maps to the `email` attribute). Checked by default.
1. **Approximate (low confidence)** — The closest available attribute differs in name or data model (for example, a Marketo _Amount_ filter approximated as _Lead Score_). Shown with a note explaining the difference; unchecked by default.
1. **Not found** — The condition couldn't be mapped to any known attribute. Shown as _"No equivalent found"_; no rule is generated.

This is why a list you describe might come back with fewer rules than conditions you specified — unmatched conditions are surfaced explicitly rather than silently dropped. If important criteria land as "not found," rephrase them using the attribute's real name and Coworker re-tries.

>[!NOTE]
>
>If you're mapping spreadsheet columns to fields (a Field Mapping card with _Source Column_, _Target Field_, a confidence percentage, and an _Unmapped Columns_ list), that is the lead import flow, not audience creation. See the [import-leads skill](./skills.md#audiences-people).

## Edit rules for an existing list {#edit-rules}

When you ask to change rules on a list you already have, Coworker establishes which list and which edit mode:

* **Add / append** (default for _"add rules"_, _"add more rules"_) — new rules are merged with the existing ones.
* **Replace** (default for _"replace rules"_, _"change rules to"_) — new rules replace all existing rules on the list.

Coworker summarizes what will be applied and clearly states whether it's adding or replacing, then asks you to confirm before it commits. After applying, it reports the total rule count and how many were added or replaced.

>[!NOTE]
>
>Edits use a merge-aware path so an "add" operation never silently overwrites your existing rules.

## Audience overlap {#overlap}

Ask Coworker to compare two people lists (for example, _"Show me the overlap between 'Q3 Webinar' and 'Enterprise Accounts'"_) and it renders a _People List Overlap_ card:

* A header badge showing the count: **"{N} in common."**
* A stats row with each list's total member count and the overlap as **"X% of A · Y% of B."**
* A member table of the people in both lists, with a **Name** column and a second column you can steer — **Email** (default), **Company**, or **Job Title** depending on what you asked.
* Click any name to open that person in the workspace.
* If there is no overlap, the card says so clearly: _"No members in common between these two lists."_

**Limitations:**

| Limit | Detail |
|---|---|
| **Table size** | Shows up to 200 members; beyond that it notes _"Showing 200 of N — ask me to refine the query to narrow results."_ |
| **Overlap computation** | Computed on email address; people without an email are excluded from the intersection. |
| **List size** | Reads up to approximately the first ~1,000 members of each list. For larger lists Coworker tells you results are partial. |
| **Draft dynamic lists** | Can't be compared — a list that hasn't been published has no live segment. Coworker asks you to publish it first or use a static list instead. |

## QA validation {#qa-validation}

After creating or updating a list, Coworker offers: _"Would you like me to verify the list is correctly configured?"_ If you accept, it re-fetches the list and reports the following checks:

| Check | Result |
|---|---|
| List found under the correct Program/Folder | Pass / fail |
| Filter count matches what was applied | _N_ filters / mismatch |
| Personalization attributes present (if included) | Present / missing |
| List name matches what you requested | Pass / fail |
| Estimated member count | _count_ or N/A |

## Limitations {#limitations}

| Limitation | Detail |
|---|---|
| **Static-list adaptation from [!DNL Marketo Engage]** | You can't adapt a [!DNL Marketo Engage] static list (or an email or other non-filter asset) into a people list. Static lists are explicit member IDs and can't be expressed as filters; Coworker asks for a Smart List or Smart Campaign instead. |
| **Activity- and membership-based filters** | When adapting from [!DNL Marketo Engage], filters like _Email Was Opened_, _Visited Web Page_, _Form Was Filled Out_, _Member of List_, and _Member of Smart Campaign_ have no people-list equivalent and come back as "No equivalent found." |
| **Company-level conditions** | Translated to the nearest person-level attribute where possible (people lists operate on person attributes) and flagged low-confidence when the fit is loose. |
| **Deeply nested AND/OR logic** | Complex nested logic may collapse to a top-level AND/OR; Coworker notes this when it happens. |
| **Name collisions** | Not auto-resolved — if the name is taken, Coworker asks you for a different one rather than silently appending a suffix. |
| **Approval required** | Coworker will not create or modify a list until you click **[!UICONTROL Proceed]**, confirm, or give a clear go-ahead (_"approved"_, _"looks good"_, _"build it"_). |
| **Static snapshot population** | Membership in static lists created from criteria fills in over a few minutes — not instantly. |

