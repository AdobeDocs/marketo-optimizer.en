---
title: Configure and Analyze Intent
description: Learn how to configure activity weights for the intent score model and analyze lead-level intent with ranking, profile, trend, and comparison reports.
TQID: 'https://experienceleague.adobe.com/BNzbM6v6ADSKyPR6jQMj1QdWMnLQQX-j3PNk8gF6PxY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
---

# Configure and analyze intent

In [!DNL Adobe Marketo Optimizer], Coworker provides two skills in the _Intent_ category. Every customer weighs marketing activities differently, so these skills let you configure what matters to your business. You can then validate what the intent pipeline produced.

| Skill | Command | What it does |
| --- | --- | --- |
| **Intent configuration** | `/intent-configuration` (alias `/intent-config`) | Configure activity weights for the person intent score model |
| **Analyze intent** | `/analyze-intent` | Query and validate lead-level intent ranking, trend, product and keyword taxonomy, and comparison reports |

Selecting a skill inserts its description as a starter prompt in the chat input, which you can edit before sending.

## Configure the weighting model {#configure-model}

To configure activity weights for the intent score model, follow these general steps. For more information about configuration and score weighting, see [_Intent Configuration_](../audiences/intent-configuration.md).

1. Invoke the skill (`/intent-configuration`) and press **Enter**.

   Coworker opens the **[!UICONTROL Intent Configuration]** panel as a workspace tab. The panel lists every intent activity from the pipeline, showing an **[!UICONTROL AI Suggested]** score and an editable **[!UICONTROL Weighting]** score for each one. It also lists the models that already exist for your tenant. Only one model can be _[!UICONTROL Active]_ at any time: the one currently driving the scoring.

1. To make changes, open an existing _[!UICONTROL Draft]_ model, or select **[!UICONTROL Duplicate]** on the _[!UICONTROL Active]_ model to start from its current weights.

1. Adjust weights row by row.

   For example, mark a low-value activity like **[!UICONTROL Add to Opportunity]** as **[!UICONTROL Trivial]**, and raise **[!UICONTROL Click Email]** or **[!UICONTROL Click Link]** to **[!UICONTROL Important]** if those activities matter more for your business.

1. Select **[!UICONTROL Save]**.

   Saving prompts you to activate the model now. Confirming replaces the current _[!UICONTROL Active]_ model, which is demoted automatically.

## Intent scoring

The intent score for a lead considers three things:

* **The weight configured here** for each activity type.
* **Content relevance**: keywords extracted from the assets tied to each activity.
* **Frequency**: how many times the lead has interacted with that content.

For details about these metrics, including AI Suggested weight, content relevance, and limitations, see [Intent Configuration](../audiences/intent-configuration.md).

## Intent reports

To introduce the four report types it can generate, invoke `/analyze-intent` to prompt Coworker. Coworker then waits for a follow-up request naming a lead, product, or comparison. Each report opens as its own tab in the workspace panel, and Coworker also adds a summary card in the chat with an _[!UICONTROL Open report]_ button.

### Intent Ranking report

**Suggested prompt:** _"Show my top high-intent leads for &lt;product&gt;"_

Ranks leads by intent signal strength for a product or keyword. Columns include Lead, Email, Account, Industry, Products, Score, Intent level, and top activity source. The _[!UICONTROL 7-day delta]_ column shows how the intent score has moved over the last week. The _[!UICONTROL Last update]_ column shows when the lead last interacted, that is, when the score last changed. Filters for product and intent level are live dropdowns, so you aren't limited to what you typed in the prompt. Columns are sortable.

Other prompts that open the same report:

* "Rank the top 10 leads by intent score for Photoshop"
* "List leads with high intent for Photoshop"
* "Show me leads whose intent score for Photoshop jumped the most this week"
* "Which leads in the Retail industry show medium-to-high intent for Creative Cloud"
* "Find leads with intent scores contributed by asset downloads in a webinar"
* "List high-intent leads whose top activity source is email click"
* "Show leads with intent contributed by web visits only, excluding downloads or webinars"

### Intent Profile report

**Suggested prompt:** _"Show me the intent profile of &lt;lead&gt;"_

A quick snapshot of one lead: which products and keywords they show interest in, and the score for each. Use this report once a ranking report has surfaced a lead worth investigating. It helps you shape journeys, personas, and buying groups around that lead's actual product intent.

Other prompts:

* "What products is &lt;lead&gt; most interested in?"
* "What is &lt;lead&gt; interested in right now?"
* "Give me a summary of all products and keywords lead X has shown intent for"

### Intent Trend report

**Suggested prompt:** _"Show me &lt;lead's&gt; intent score history for &lt;product&gt; over the last 30 days"_

Plots one lead's intent score for one product over time. Use it to identify inflection points. For example, a score that remains constant for weeks and then drops sharply signals a change in interest, not irrelevant data. You can adjust the timeframe to 7, 30, or 100 days.

Other prompts:

* "What is the intent surge for Acrobat this week for lead X?"
* "Show me the intent trend for a lead this month"
* "Has lead X's intent for Acrobat gone up or down this month?"

### Intent Comparison report

**Suggested prompt:** _"Compare intent trends for Photoshop versus Illustrator across all leads in the last 30 days"_

Compares intent over time for two leads or two products, as a side-by-side chart plus a summary table (current score, score N days ago, delta). Timeframe is adjustable the same way as the trend report. Intent can shift daily, minute-to-minute, or hourly, so a short flat window doesn't necessarily mean nothing's happening.

Other prompts:

* "Compare Acrobat and Photoshop intent over the last quarter"
* "Compare lead X and lead Y's intent for Creative Cloud"
* "Which has higher average intent: Photoshop or Illustrator?"
* "Compare personas for Acrobat: who has the higher win rate?"
* "Show side-by-side intent for Photoshop across the Retail and Finance segments"

## Report follow-up {#report-follow-up}

Intent reports are read-only and have no standalone export option. To act on what a report shows, use other skills instead.

* Prompt with _"List the top intent leads for Creative Cloud."_ Coworker uses the `/analyze-intent` skill to produce the specified list.

* Prompt with _"Create a person list using this list."_ Coworker hands the lead set to the [audience creation skill](./audience-creation.md), which builds the person list directly. No manual export or import step is needed.
