---
title: AI-Decisioning Health
description: Learn how AI-decisioning health checks lead coverage, persona classification, and signal richness in Marketo Optimizer, and flags what's missing.
---

# AI-decisioning health

AI-decisioning health checks the data that powers personalization in [!DNL Adobe Marketo Optimizer]. It reports on lead coverage, persona classification, and story richness across demographic, firmographic, technographic, and psychographic categories. Then it flags missing data to identify where to start.

Use AI-decisioning health to see what data flows in from [!DNL Marketo Engage] and where gaps exist. Closing those gaps improves how [AI decisioning](./ai-decisioning.md) scores and routes each person.

## Open AI-decisioning health {#open}

Open the report from either the home page or the Coworker chat.

* On the _Home_ page, select the **[!UICONTROL AI-decisioning health]** card in the Quick access row. The card leads the row and shows story volume and persona-classification progress, such as 929 stories, 32% persona classified.
* In the Coworker chat box, ask about your personalization data directly, or type `/` and select **[!UICONTROL AI-decisioning health]**.

![Quick access row on the home page, showing the AI-decisioning health card first, followed by Marketing, Assets, and Reports.](./assets/ai-decisioning-health-quick-access.png){width="600"}

Both paths open the report inside the Coworker workspace.

## Chat welcome and follow-up prompts {#chat-welcome}

Opening AI-decisioning health from chat displays a welcome message, _[!UICONTROL *Welcome to AI-decisioning health]_, a summary of report checks, and a card to open the full report.

Below the card, under _[!UICONTROL What would you like to do next?]_, AI-decisioning health suggests follow-up prompts based on your own data's specific gaps. For example, if 67.7% of your leads lack a persona classification, one suggested prompt reads _Why are 67.7% of leads unclassified by persona?_ Select a suggested prompt, or ask your own question, to get a direct answer without leaving chat.

![Coworker chat panel showing the welcome message for AI-decisioning health, a card that opens the report, and four suggested follow-up prompts.](./assets/ai-decisioning-health-highlights.png){width="800" zoomable="yes"}

## Report overview {#report-overview}

The workspace report opens with a **[!UICONTROL Highlights]** callout that lists the strongest and weakest areas of your data in plain language, such as _Demographic data reaches 100% of leads with strong field depth_ or _67.7% of leads remain unclassified into any persona_. A checkmark marks a healthy result, and a slashed circle marks a gap.

Next to the highlights, a radar chart plots overall **[!UICONTROL Coverage]** across six dimensions: demographic, firmographic, technographic, psychographic, persona, and intent. A larger shaded area means broader coverage.

## Persona classification {#persona-classification}

The **[!UICONTROL Persona classification]** section shows how many of your stories are classified into a persona, for example: _300 of 929 stories classified · 32.3% classified · 67.7% unclassified_. A stacked bar breaks classified stories by persona, with a legend showing the story count and percentage for each.

Select a persona segment to open a detail card with example job titles for that persona. For example, the **[!UICONTROL Other]** segment might show: _272 stories / 29.3%_, with examples such as Industry Specialist, Independent Advisor, Freelance Consultant, and Subject Matter Expert.

## Coverage {#coverage}

The **[!UICONTROL Coverage]** section lists five data categories: demographic, firmographic, technographic, psychographic, and intent and activity. Each category shows the percentage of stories with at least one available attribute in that category.

Select a category to expand it, then choose one of two tabs:

* **[!UICONTROL Attributes]** - Attributes grouped by type, such as Personal Details or Location under demographic. Each attribute shows how many stories have a value for it, for example: `firstName (906 stories)`.
* **[!UICONTROL Flags]** - Gaps specific to that category, or _No open flags on this category_ when coverage is healthy.

Use the search field above the category list to jump directly to a category or attribute by name.

![Coverage section with the Demographic category expanded, showing attribute groups such as Personal Details, Engagement Scoring, and Location.](./assets/ai-decisioning-health-coverage.png){width="800" zoomable="yes"}

## Flags {#flags}

The **[!UICONTROL Flags]** section at the bottom of the report lists every gap found across all categories, ranked by severity:

* **[!UICONTROL Critical]** - Gaps that block a capability outright, such as _Technographic coverage is 0% across all leads_.
* **[!UICONTROL Watch]** - Gaps that reduce effectiveness but don't block a capability, such as _Psychographic coverage reaches only 7.2% of leads_.

Filter the list by severity, then select a flag to expand it and read a one-sentence explanation of its business impact, for example: _Unclassified leads cannot enter persona-specific journeys or receive role-tailored messaging, reducing campaign relevance and conversion rates._

![Flags section filtered to Watch severity, showing three flags with one expanded to reveal its business-impact explanation.](./assets/ai-decisioning-health-flags.png){width="800" zoomable="yes"}

## Recently accessed {#recently-accessed}

If you open AI-decisioning health and then navigate away, it reappears under **[!UICONTROL Recently accessed]** in the empty workspace, so you can jump back into the report without returning to the home page.

![Recently accessed list showing AI-decisioning health as the most recent item, ahead of Scoring Studio.](./assets/ai-decisioning-health-recently-accessed.png){width="500"}

>[!BEGINSHADEBOX]

Planned enhancements for AI-decisioning health include:

* A dedicated entry in the Coworker skills catalog.
* Guided "ask how" actions that walk you through fixing a flag.
* A dedicated next steps tab.

>[!ENDSHADEBOX]
