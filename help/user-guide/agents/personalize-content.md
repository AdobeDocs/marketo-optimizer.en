---
title: Personalize Email Content by Persona
description: Use the Content Personalization skill in Marketo Optimizer to turn an email into persona-based, data-informed variants. Personalize or analyze emails.
TQID: 'https://experienceleague.adobe.com/9fa1wfsHH6h46jJ-slLxMpB6fud1VHgmiWxbao-bWvo'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---

# Personalize email content by persona

The _Content Personalization_ skill transforms an email into persona-based, data-informed variants, so you do not have to build a separate email for each audience. Instead of sending one message after an event, the skill resolves your audience into [derived persona](../audiences/personas.md) cohorts, surfaces insights, and generates personalized variants. Every variant is saved as conditional content inside a single email, so each person automatically receives the version that matches their persona when a journey sends it.

* **Skill** - `content-personalization`
* **Invocation** - From the [chat interface](./chat-interface.md), describe a target audience for a new email, or select **[!UICONTROL Personalize email]** or **[!UICONTROL Analyze email]** from the _More_ menu of a draft [email in the programs tree](../marketing/email-channel.md#personalize-analyze)
* **Reads from / writes to** - [!DNL Marketo Optimizer]

## Key concepts {#key-concepts}

| Term | Definition |
| --- | --- |
| **Persona cohort** | A group of people who share a [derived persona](../audiences/personas.md), such as _CXO/EVP_ or _Individual Contributor_. |
| **Segment** | A group of people defined by any criteria, such as persona, industry, or engagement tier. A persona cohort is a segment defined specifically by shared derived persona. |
| **Target group** | The audience you describe in natural language. The skill resolves it into matching persona cohorts. |
| **Insight** | A data-informed finding about the messaging, positioning, or tone that performs best for a persona cohort, drawn from your own data. |
| **Variant** | A personalized version of the email sections you chose to personalize, generated for one persona cohort. |
| **AI Personalized Email** | The single saved email that bundles every variant as [conditional content](../content/conditional-content.md) blocks. |
| **Email audit** | A review of an existing email against each of your target-group segments, showing what resonates and what to improve for every persona before you personalize. |

## Prerequisites {#prerequisites}

* Access to [!DNL Marketo Optimizer] with [!DNL CX Coworker] enabled.
* [Derived personas](../audiences/personas.md) resolved in your data. The skill relies on these classifications to build persona cohorts. Custom persona support is planned for a future release.
* Enough historical data for insights. If insights are not available for a persona cohort, the skill tells you that data is insufficient and falls back to general best practices for that persona.
* An [email template](../content/templates.md) or an existing draft [email](../marketing/email-channel.md) in a program.
* A [person journey](../marketing/person-journeys.md) that contains the _Send Email_ action node used to deliver the personalized email.

## Create and personalize an email from a template {#create-personalize-from-template}

This flow authors a new email and personalizes it in the same conversation.

1. **Invoke the `/content-personalization` skill** in the [!DNL Coworker] chat interface.

1. **Provide the content.**

   Upload a content brief, or describe the content you want in natural language.

1. **Select a template** from your [template](../content/templates.md) library.

1. **Review the draft.**

   [!DNL Coworker] maps your content to the template and produces a draft email. You can make basic text edits inline.

   >[!WARNING]
   >
   >Only basic text edits are available inline during authoring. For advanced edits, save the email and open it in the [visual design space](../content/email-authoring.md).

1. **Describe the target group** in natural language.

1. **Review the resolved persona cohorts**.

   [!DNL Coworker] inspects your data and returns the persona cohorts that match your description, with a count for each. Revise the target-group description and try again if needed.

1. **Confirm the target group**.

   Then [!DNL Coworker] retrieves insights for each resolved persona cohort.

1. **Select the sections to personalize**, such as the subject line or a body section, and review the generated variants.

   Regenerate a variant if it does not fit. The number of persona cohorts is not fixed. It depends on your target group and your data.

1. **Save the email**.

   All variants are stored in one AI Personalized Email, not as separate emails.

<!-- screenshot: Coworker chat panel showing the resolved persona cohorts with counts, and the "Personalized variants" review grid -->

## Analyze an existing email {#analyze-existing-email}

The _Analyze_ tool is available only for draft emails. After an email is published, it cannot be changed. In the programs tree, click the _More_ icon (**...**) next to a draft [email](../marketing/email-channel.md#manage-emails) and choose **[!UICONTROL Analyze email]**.

![Programs tree email More menu](../marketing/assets/email-tree-more-menu.png){width="400"}

To run an email audit:

1. **Describe the target group** you want to personalize for, in terms of their persona.

   For example _People in Marketing roles_ or _People in Leadership functions_.

1. **Review the email audit.**

   [!DNL Coworker] resolves your description into persona segments and shows an **Email audit** card listing each segment, then reviews the email against each one to highlight what resonates and what to improve.

1. [!DNL Coworker] asks what to do next, including **[!UICONTROL See section-by-section audit]** and **[!UICONTROL Personalize this email]**.

1. Select **[!UICONTROL See section-by-section audit]** to open an **_Email analysis_** view with a persona selector and specific recommendations for each section.

    Each section shows how many changes are recommended, and each persona shows a recommendation count, such as `4 recommendations for SVP/VP`. You can also apply the recommendations directly by entering _personalize_ in the chat.

1. From the audit, select **[!UICONTROL Personalize this email]** to apply the insights and generate variants.

   See the following section, [_Personalize an existing email_](#personalize-existing-email).

<!-- screenshot: Email analysis view with persona selector, per-section "N changes" badges, and "what needs work" recommendations -->

## Personalize an existing email {#personalize-existing-email}

Select **[!UICONTROL Personalize email]** from the _More_ menu of a draft email in the programs tree, or continue from an [email audit](#analyze-existing-email), to personalize an email you already built.

1. **Review the resolved persona cohorts.**

   [!DNL Coworker] inspects your data and returns the persona cohorts that match your description, with a count for each. Revise the target-group description and try again if needed.

   If you arrived at this step from an email audit, [!DNL Coworker] continues directly from the audit insights.

1. **Select the sections to personalize** in the email preview, such as the subject line and specific content sections, and confirm.

1. **Review the generated variants.**

   Variants can also vary by industry, such as a CXO in healthcare versus financial services. [!DNL Coworker] presents a **[!UICONTROL Personalized variants]** grid, one card per persona cohort, with a subject line, headline, body, and a **[!UICONTROL Preview]** option.
   
   Select the _Information_ icon on a card to see the insight for that variant (the persona it's based on and the engagement insight that informed it) and regenerate a variant if needed.

   You can filter the grid by persona.

1. **Save the set.**

   Click **[!UICONTROL Save]** and confirm. [!DNL Coworker] confirms the email is now available in the AI Library, then asks whether to apply the changes to the original email also, which updates it in place.

<!-- screenshot: "Personalized variants" grid showing persona cards with subject, headline, body, Preview, and the info-icon insight tooltip -->

## Saved output and use in a journey {#saved-output}

Whichever flow you start from, personalization produces a single _AI-personalized email_ stored in the AI Library. The email contains [conditional content](../content/conditional-content.md) blocks keyed by persona. To edit sections, open it in the [visual design space](../content/email-authoring.md), and to preview how each persona-keyed block resolves, use **[!UICONTROL Simulate Content]**.

To use the email in a journey, add a [Send Email node](../marketing/action-nodes.md) and select **[!UICONTROL Use an AI-personalized email]**.

![Take an action - Send email - Use an AI-personalized email](../marketing/assets/person-action-node-email-source-personalized.png){width="450"}

Then choose the saved email. Apply your configuration and business rules to the node as usual.

## Run-time behavior {#run-time-behavior}

You select the single AI personalized email in the journey, not one variant per audience. When the journey runs, the email automatically resolves to the variant that matches each recipient's persona. You do not choose a variant per recipient.

## Limitations {#limitations}

| Limitation | Detail |
| --- | --- |
| **Custom personas** | Not yet supported. The skill classifies persona cohorts from out-of-the-box [derived personas](../audiences/personas.md) only. |
| **Insufficient data for insights** | If your data does not support an insight for a persona cohort, the skill states this and falls back to general best practices for that persona. |
| **Inline editing during authoring** | Only basic text edits are available inline when you [create and personalize an email from a template](#create-personalize-from-template). Advanced edits require the [visual design space](../content/email-authoring.md). |
| **Starting point required** | Personalizing an email requires either a template or an existing draft email in a program. |
