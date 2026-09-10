---
title: Intent Configuration
description: Learn how to configure activity weights that drive the person intent score model, from AI-suggested defaults to activating a custom weighting model.
TQID: 'https://experienceleague.adobe.com/ZL9RJqD-OZkIgFMpwJ4Cz-FW-463w6OJyEHAe5uJuec'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
---

# Intent configuration

A single standardized set of activity weights does not work across customers. What signals real buying intent varies by business. Configure and activate an intent model to specify what matters to you, for example, whether a form fill signals more than an email click, instead of inheriting one global default.

The **[!UICONTROL Intent Configuration]** panel tools control how much each lead-intent activity counts toward a person's intent score. It is the only configurable input into intent scoring. Other factors, such as content relevance, decay, and thresholds, are system-managed. It is available through the [Intent configuration skill](../agents/intent.md#configure-model).

Open the panel using one of two methods from the Coworker [chat interface](../agents/chat-interface.md): 

* Enter the `/intent-configuration` command.
* Click **[!UICONTROL +]**, select **[!UICONTROL Use an agent skill]**, select the **[!UICONTROL Intent]** tab, and then click **[!UICONTROL Intent configuration]**.

![The intent configuration panel opened from the chat interface](./assets/intent-configuration-panel.png){width="700" zoomable="yes"}

## Model list view

Landing in the panel shows **[!UICONTROL Intent score weighting]**, with the total model count below the title, a search field to filter by name, and a sortable table:

| Column | Notes |
| --- | --- |
| [!UICONTROL Name] | Sortable, default sort |
| [!UICONTROL Status] | _[!UICONTROL Active]_ (green dot), _[!UICONTROL Draft]_ (orange dot), _[!UICONTROL Archived]_ (grey dot) |
| [!UICONTROL Creation date] | Abbreviated, full date on hover |
| [!UICONTROL Last updated] | Abbreviated, full date on hover |
| [!UICONTROL Last updated by] | Truncated username, full name on hover |

Only one model can be _[!UICONTROL Active]_ at any time and it is the model driving scoring. Every other model is in a _[!UICONTROL Draft]_ (being edited, not yet live) or _[!UICONTROL Archived]_ (a former _[!UICONTROL Active]_ model, automatically demoted when a new one is activated) state.

Click a row to open the model detail view.

## Model detail view

The detail view shows the model name, status badge, last-saved timestamp, and a breadcrumb showing **[!UICONTROL Intent score weighting]** and the model name, which you can click to return to the list.

The detail view lists the buyer-intent activities and the importance level each contributes to the person's intent score. The activity catalog is fixed, and only the levels can change. These levels are independent: they do not need to add up to any total. Only one version of the weighting model can be active at a time. To make changes, duplicate the current version and edit the copy.

![The detail view for an active intent model](./assets/intent-configuration-model-detail.png){width="550" zoomable="yes"}

A search field filters activity rows by name. The table itself:

| [!UICONTROL Intent activity] | [!UICONTROL AI Suggested] | [!UICONTROL Weighting] | [!UICONTROL Reset] |
| --- | --- | --- | --- |
| For example, Add to Opportunity, Fill Out Form, Click Email, Click Link, Open Email, Unsubscribe Email, Visit Webpage, Asks questions in webinar, Asset downloads in webinar, Interesting Moment, Responded to Poll in Webinar, Update Opportunity | Read-only | Dropdown, editable on Draft models | **↺** icon: resets this row to the AI Suggested value |

**Weighting tiers** (same scale for both AI Suggested and Weighting columns):

| Tier | Value |
| ---| --- |
| [!UICONTROL No Weight] | 0 |
| [!UICONTROL Trivial] | 30 |
| [!UICONTROL Minor] | 40 |
| [!UICONTROL Normal] | 60 |
| [!UICONTROL Important] | 90 |
| [!UICONTROL Vital] | 100 |

![Changing the value for the Add to Opportunity activity in a draft intent model](./assets/intent-configuration-model-edit.png){width="550" zoomable="yes"}

Setting an activity to **[!UICONTROL No Weight]** (0) drops it from scoring entirely. The system currently excludes **[!UICONTROL Unsubscribe Email]** by default using this method.

Click  **[!UICONTROL Reset all to suggested]** above the table to restore every row to its AI Suggested value.

### Create and activate a model

To create and activate a new weighting model, follow these steps.

1. Start from an existing _[!UICONTROL Draft]_ model.

   You can also click **[!UICONTROL Duplicate]** for the current _[!UICONTROL Active]_ model to clone its weights into a new draft.

1. Adjust weights row by row to reflect what matters for your business.

   For example, downgrade a low-signal activity to **[!UICONTROL Trivial]**, or upgrade a high-signal one to **[!UICONTROL Important]** or **[!UICONTROL Vital]**.

1. Click **[!UICONTROL Save]**.

   Saving prompts you to activate the model immediately.

1. Confirm activation.

  The confirmation makes it the new _[!UICONTROL Active]_ model and automatically demotes the previously active one to _[!UICONTROL Archived]_. Only one model can be active at a time.

### AI Suggested column

The AI Suggested column is a starting point, not a trained recommendation.

* One LLM completion call handles all activities at once for a tenant, not one call per activity.

* For each activity, the model reads only its name and description, then picks a weight tier based on general knowledge of B2B buyer behavior. For example, consider what **[!UICONTROL Fill Out Form]** or **[!UICONTROL Click Email]** typically signals for a B2B buyer. It has no access to the tenant's customer data, CRM records, or historical engagement patterns, and is not tenant- or subscription-specific today.

* The output populates `SUGGESTED_WEIGHT_VALUE` in `IBG_INTENT_ACTIVITY_WEIGHT` at model creation time, and stays static afterward. It does not update as you edit the Weighting column.

* Every activity row always has a populated suggested value. None are left blank.

Review and adjust every row to reflect your own business context. The suggested values are a reasonable default, not a tuned model.

## Actions on a model

You can manage a model based on its status.

| Action | Available for | What happens |
| --- | --- | --- |
| **[!UICONTROL Duplicate]** | Active, Draft | Opens a modal titled **[!UICONTROL Duplicate]**, with a pre-populated Name field and **[!UICONTROL Cancel]** and **[!UICONTROL Duplicate]** buttons. Confirming creates a new _[!UICONTROL Draft]_ model with the same weights, which opens directly in the detail view. |
| **[!UICONTROL Activate]** | Draft only (also offered as a prompt right after Save) | Promotes the Draft to _[!UICONTROL Active]_ and automatically demotes the previously Active model to _[!UICONTROL Archived]_. |
| **[!UICONTROL Delete]** | Draft only | Prompts a confirmation dialog before permanent deletion. This action is irreversible. Active models cannot be deleted. |

Because only draft models are editable, the normal workflow is to click **[!UICONTROL Duplicate]** for the current _[!UICONTROL Active]_ model, adjust weights on the draft copy, then click **[!UICONTROL Save]**. You can activate it immediately or later using the **[!UICONTROL Activate]** button.

## Weighting calculations in intent scores

The **[!UICONTROL Weighting]** column displays the number used in daily scoring, read from the row for the currently _[!UICONTROL Active]_ model. Three things drive a lead's intent score:

1. **The weight configured here** (`WEIGHT_VALUE`) for each activity. It starts from the AI suggestion but can be overridden per tenant. Only the row tied to the _[!UICONTROL Active]_ model is used, so a weight change doesn't need a code release.

1. **Content relevance**: not configurable here. The system extracts keywords from activity-related content or assets and scores how well that content matches a keyword, product, or category from 0 to 1.

1. **Frequency**: how many times a lead has interacted with that content, factored into the averaging across a person's engagements.

Formally, per engagement: `activity weight × content relevance`, averaged into a **daily score** with a **7-day exponential decay** applied so recent activity dominates, then min-max normalized to 0 to 1 across the current population and bucketed:

| Final score | Intent level |
| --- | --- |
| &gt; 0.6 | High |
| &gt; 0.2 | Medium |
| Otherwise | Low |

### Content relevance

For web-based activities, the system inspects the asset URL and the associated company, then derives relevant keywords from that company's taxonomy. For example, a URL tied to [!DNL Intuit] surfaces keywords like _tax_ or _payroll_. A lead's actual engagement with that content, for example, viewing a [!DNL TurboTax] page or a [!DNL QuickBooks] page, is compared against those keywords to determine which specific product the interest maps to. For non-web activities such as _[!UICONTROL Interesting Moment]_ (including offline events), the model evaluates the moment's description or content, such as an offline webinar topic, rather than the activity type. The content, not the event category, determines relevance.

## Known limitations

The following limitations apply to intent configuration today.

* **No custom or tenant-defined activities today.** The activity catalog is fixed, and [!DNL Marketo Engage] is the sole source of truth. An activity must be logged in [!DNL Marketo Engage] to be scored. A future column for tenant-defined activities is being scoped.
* **No third-party intent ingestion today**, for example, from [!DNL Demandbase], [!DNL ZoomInfo], or [!DNL 6sense]. This update is planned for later releases. Until then, the workaround is to build the audience in the third-party tool and push it into [!DNL Marketo Engage] or [!DNL Marketo Optimizer] directly, bypassing intent scoring for that signal.
* **No native export** from the weighting panel or from intent reports. See [Report follow-up](../agents/intent.md#report-follow-up) for prompts that turn report results into a person list.
