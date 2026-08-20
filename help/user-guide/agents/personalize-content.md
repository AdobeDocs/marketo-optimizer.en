---
title: Personalize Email Content by Persona
description: Use the Content Personalization skill in Marketo Optimizer to turn an email into persona-based, data-informed variants. Personalize or analyze emails.
---

# Personalize email content by persona

The _Content Personalization_ skill turns one email into persona-based, data-informed variants, so you do not have to build a separate email for each audience. Instead of sending one message after an event, the skill resolves your audience into [derived persona](../audiences/personas.md) cohorts, surfaces insights, and generates personalized variants. Every variant is saved as conditional content inside a single email, so each person automatically receives the version that matches their persona when a journey sends it.

* **Skill** - `content-personalization`
* **Invocation** - From the [chat interface](./chat-interface.md), describe a target audience for a new email, or select **[!UICONTROL Personalize this email]** or **[!UICONTROL Analyze this Email]** on an existing email in a [Send Email node](../marketing/action-nodes.md)
* **Reads from / writes to** - [!DNL Marketo Optimizer]

## Key concepts {#key-concepts}

| Term | Definition |
|---|---|
| **Persona cohort** | A group of people who share a [derived persona](../audiences/personas.md), such as _CXO/EVP_ or _Individual Contributor_. |
| **Segment** | A group of people defined by any criteria, such as persona, industry, or engagement tier. A persona cohort is a segment defined specifically by shared derived persona. |
| **Target group** | The audience you describe in natural language. The skill resolves it into matching persona cohorts. |
| **Insight** | A data-informed finding about the messaging, positioning, or tone that performs best for a persona cohort, drawn from your own data. |
| **Variant** | A personalized version of the email sections you chose to personalize, generated for one persona cohort. |
| **AI Personalized Email** | The single saved email that bundles every variant as [conditional content](../content/conditional-content.md) blocks. |
| **Email audit** | A review of an existing email against each of your target-group segments, showing what resonates and what to improve for every persona before you personalize. |

## Prerequisites {#prerequisites}

* Access to [!DNL Marketo Optimizer] with AI Assistant enabled.
* [Derived personas](../audiences/personas.md) resolved in your data. The skill relies on these classifications to build persona cohorts. Custom persona support is planned for a future release.
* Enough historical data for insights. If insights are not available for a persona cohort, the skill tells you that data is insufficient and falls back to general best practices for that persona.
* An [email template](../content/templates.md) or an existing email referenced by a [_Send Email_ action node](../marketing/action-nodes.md).
* A [person journey](../marketing/person-journeys.md) that contains the _Send Email_ action node used to deliver the personalized email.

## Create and personalize an email from a template {#create-personalize-from-template}

This flow authors a new email and personalizes it in the same conversation.

1. **Provide the content.** Upload a content brief, or describe the content you want in natural language.

1. **Select a [template](../content/templates.md)** from your template library.

1. **Review the draft.**

   AI Assistant maps your content to the template and produces a draft email. You can make basic text edits inline.

   >[!WARNING]
   >
   >Only basic text edits are available inline during authoring. For advanced edits, save the email and open it in the [visual design space](../content/email-authoring.md).

1. **Describe the target group** in natural language.

1. **Review the resolved persona cohorts**.

   AI Assistant inspects your data and returns the persona cohorts that match your description, with a count for each. Revise the target-group description and try again if needed.

1. **Confirm the target group**.

   Then AI Assistant retrieves insights for each resolved persona cohort.

1. **Select the sections to personalize**, such as the subject line or a body section, and review the generated variants.

   Regenerate a variant if it does not fit. The number of persona cohorts is not fixed. It depends on your target group and your data.

1. **Save the email**.

   All variants are stored in one AI Personalized Email, not as separate emails.

<!-- screenshot: AI Assistant chat panel showing the resolved persona cohorts with counts, and the "Personalized variants" review grid -->

## Analyze an existing email {#analyze-existing-email}

On a journey [_Send Email_ node](../marketing/action-nodes.md) that references an existing email, the **[!UICONTROL Take an action]** panel shows the email name with two options: **[!UICONTROL Personalize this email]** and **[!UICONTROL Analyze this Email]**.

<!-- screenshot: Send Email node "Take an action" panel showing the email name and the Personalize this email / Analyze this Email options -->

Select **[!UICONTROL Analyze this Email]** to run an email audit:

1. **Describe the target group** you want to personalize for, in terms of their persona.

   For example _People in Marketing roles_ or _People in Leadership functions_.

1. **Review the email audit.**

   AI Assistant resolves your description into persona segments and shows an **Email audit** card listing each segment, then reviews the email against each one to highlight what resonates and what to improve.

1. AI Assistant asks what to do next, including **[!UICONTROL See section-by-section audit]** and **[!UICONTROL Personalize this email]**.

1. Select **[!UICONTROL See section-by-section audit]** to open an **_Email analysis_** view with a persona selector and specific recommendations for each section.

    Each section shows how many changes are recommended, and each persona shows a recommendation count, such as `4 recommendations for SVP/VP`. You can also apply the recommendations directly by entering _personalize_ in the chat.

1. From the audit, select **[!UICONTROL Personalize this email]** to apply the insights and generate variants.

   See the following section, [_Personalize an existing email_](#personalize-existing-email).

<!-- screenshot: Email analysis view with persona selector, per-section "N changes" badges, and "what needs work" recommendations -->

## Personalize an existing email {#personalize-existing-email}

Select **[!UICONTROL Personalize this email]** on a _Send Email_ action node, or continue from an [email audit](#analyze-existing-email), to personalize an email you already built.

1. **Review the resolved persona cohorts.**

   AI Assistant inspects your data and returns the persona cohorts that match your description, with a count for each. Revise the target-group description and try again if needed.

   If you arrived at this step from an email audit, AI Assistant continues directly from the audit insights.

1. **Select the sections to personalize** in the email preview, such as the subject line and specific content sections, and confirm.

1. **Review the generated variants.**

   In addition to persona, variants can also vary by industry, for example a CXO in healthcare compared with a CXO in financial services. AI Assistant presents a **[!UICONTROL Personalized variants]** grid, one card per persona cohort, each with a subject line, headline, body, and a **[!UICONTROL Preview]** option. 
   
   Select the _Information_ icon on a card to see the insight behind that variant (the persona it's based on and the engagement insight that shaped it) and regenerate a variant if needed.

   You can filter the grid by persona.

1. **Save the set.**

   Click **[!UICONTROL Save]** and confirm. AI Assistant confirms the email is now available in the AI Library, then asks whether to apply the changes to the original email also, which updates it in place.

<!-- screenshot: "Personalized variants" grid showing persona cards with subject, headline, body, Preview, and the info-icon insight tooltip -->

## Saved output and use in a journey {#saved-output}

Whichever flow you start from, personalization produces a single **AI Personalized Email** stored in the AI Library. The email contains [conditional content](../content/conditional-content.md) blocks keyed by persona. To edit sections, open it in the [visual design space](../content/email-authoring.md), and to preview how each persona-keyed block resolves, use **[!UICONTROL Simulate Content]**.

To use the email in a journey, add a [Send Email node](../marketing/action-nodes.md) and select **[!UICONTROL AI Personalized Emails]** instead of **[!UICONTROL Create an email]**, then pick the saved email. Apply your configuration and business rules to the node as usual.

<!-- screenshot: Send Email node configuration with "AI Personalized Emails" selected and the saved email applied -->

## Run-time behavior {#run-time-behavior}

You select the single AI personalized email in the journey, not one variant per audience. When the journey runs, the email automatically resolves to the variant that matches each recipient's persona. You do not choose a variant per recipient.

## Limitations {#limitations}

| Limitation | Detail |
|---|---|
| **Custom personas** | Not yet supported. The skill classifies persona cohorts from out-of-the-box [derived personas](../audiences/personas.md) only. |
| **Insufficient data for insights** | If your data does not support an insight for a persona cohort, the skill states this and falls back to general best practices for that persona. |
| **Inline editing during authoring** | Only basic text edits are available inline when you [create and personalize an email from a template](#create-personalize-from-template). Advanced edits require the [visual design space](../content/email-authoring.md). |
| **Starting point required** | Personalizing an email requires either a template or an existing email referenced by a Send Email node. |
