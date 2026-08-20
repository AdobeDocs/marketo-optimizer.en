---
title: Add Emails to Journeys
description: Add email action nodes to person journeys and create new emails for targeted communications in Marketo Optimizer.
feature: Email Authoring, Person Journeys
role: User
---
# Add emails to journeys

[!DNL Adobe Marketo Optimizer] brings a modern, enterprise-grade email authoring and delivery experience to B2B marketers.

>[!NOTE]
>
>If you are sending an email for the first time, make sure that [email deliverability](../start/email-deliverability.md) and the needed [email channel](../admin/email-channel-configuration.md) are configured.

<!-- 
* **Email channel configurations** - Manage the sender identity, reply behavior, marketing vs. transactional message types, and tracking.
* **Email deliverability controls** - Set up your email deliverability channel, including subdomain delegation (Fully Delegated and CNAME methods), DMARC, SPF/DKIM auto-configuration, and shared IP pool support.
* **Send Email action** - From a journey, add a _Send email_ action node, including personalization using profile attributes (Handlebars syntax).
* **Visual drag-and-drop email design tools** -  Design your email content with structures, content components, themes, dark-mode support, and reusable visual fragments.
* **Marketo Design Studio assets** — Choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas.
* **Reusable templates and fragments** — Save common headers, footers, CTAs, and full email layouts and reuse them across journeys.
* **Role-Based Access Control (RBAC)** — Apply granular permissions for creating, editing, approving, and sending email. 
-->

## Current limitations {#limitations}

* **Test profiles, Simulate Content, and Send Proof** are not available in this release. Litmus rendering and SpamAssassin-based spam reports are on the GA roadmap.
* **Account-level personalization and custom-object data** are not available in this release. Use profile attributes.
* **Velocity-to-Handlebars automated migration** of existing Marketo Engage templates ships at GA.
* **Comments and collaboration on emails** (inline comments, @mentions, request-review workflow) ship in an upcoming release.
* **AEM Assets, AEM Content Fragments, and Adobe Express** integrations are on the _Fast Follow-up_ roadmap.

## Key concepts {#key-concepts}

Before creating emails for person journeys and authoring email content, review these concepts:

| Concept | In [!DNL Adobe Marketo Optimizer] |
| ------- | ---------------------- |
| **_Email design space_** | The visual canvas and design tools used to compose email content. It includes drag-and-drop layout components, templates, fragments, themes, and a personalization editor. |
| **_Template_** | A reusable email layout that is available for creating a new email. It can be either a built-in sample template provided by Adobe or a custom-built template created by your team. |
| **_Visual fragment_** | A reusable block of content (such as a header, footer, CTA, legal disclaimer) that can be inserted into multiple emails. Updating a fragment propagates the change to every email that uses it. |
| **_Theme_** | A reusable styling preset (colors, typography, spacing, button styles) applied across an email. |
| **_Personalization token_** | A Handlebars expression — for example, `{{profile.firstName}}` — resolved at send time using each recipient's profile data. |
| **_Send Email action_** | The journey action node that uses a channel configuration and email content to deliver an email. |

## Add an email from a journey

To send email from a journey, [add a _Take an action_ node](action-nodes.md#add-an-action-node) and configure it to send email.

1. In the journey canvas, click the **+** icon and select **[!UICONTROL Take an action]**.

1. In the node properties on the right, set the action to **[!UICONTROL Send Email]**.

    ![Take an action - Send email](./assets/person-action-node-send-email.png){width="500"}

1. Choose the Email source:

   * **Create/edit email** - Choose this option to define the email content including the subject line, sender information, and email body in the email design space.

   * **[!UICONTROL Use an AI-personalized email]** - (_Not available for Beta_) Choose this option to refine an AI_generated email in the email design space. These emails are optimized so that AI-assisted inbox clients ground their summaries and answers in your offers and calls to action.

1. Click **[!UICONTROL Create email]**.

1. In the _[!UICONTROL Create email]_ dialog, enter a unique **[!UICONTROL Name]** (required) and a **[!UICONTROL Description]** (optional).

   ![Create email dialog](./assets/email-channel-create-email-dialog.png){width="400"}

1. Click **[!UICONTROL Create]**.

For optional [send-time optimization](email-send-time-optimization.md), configure the journey action node after you create the email.

## Define the email properties and actions {#define-email-properties}

The email page opens when you create an email for a _[!UICONTROL Send Email]_ node. You can also access this page after the email is created by clicking **[!UICONTROL Edit email]** in the node properties on the right.

1. (Optional) In the **[!UICONTROL Properties]** tab, enter any descriptive information that you want to capture for the email.

1. Select the **[!UICONTROL Actions]** tab and complete the functional settings for the email:

   * **[!UICONTROL Email]** - Select or create an **[!UICONTROL Email channel configuration]** to use. 
   
      This is the reusable set of email-delivery settings that defines the sender identity, reply-to address, subdomain, IP pool, email type (marketing or transactional), and tracking. Click the _View_ icon to review the settings for the selected configuration.

      Administrators create configurations in [Email channel configuration](../admin/email-channel-configuration.md).

   * **[!UICONTROL Business rules]** - (Optional) Apply capping or quiet hours rules to your email action by selecting a rule set.
    
      For more information about business rules and how to define and activate rule sets for channel communications, see [_Business rules_](../admin/business-rules.md). 

   * **[!UICONTROL Action tracking]** - Select the check boxes for the actions that you want to track for the email.

   ![Email channel - Actions tab](./assets/email-channel-actions-tab.png){width="600" zoomable="yes"} 

1. Click **[!UICONTROL Edit content]**, or select the **[!UICONTROL Content]** tab. 

1. Enter the **[!UICONTROL Subject line]** text that you want to display in the subject field for the email.

   Click the _Personalize_ icon ( ![Personalize icon](../assets/do-not-localize/icon-personalize.svg) ) to use a personalization token in the field.

1. (Optional) Select the **[!UICONTROL Optimize HTML size]** check box to reduce the size of your email HTML during the publishing process.

   This helps prevent email clipping in clients such as Gmail, which truncates messages exceeding 100 KB. See [_Optimize email HTML size_](#optimize-html-size) for more information.

1. Click **[!UICONTROL Edit email body]** to access the visual design tools and start [building your content](../content/email-authoring.md).

   Alternatively, you can click **[!UICONTROL Code Editor]** to code your own content in plain HTML. If you have existing HTML to reuse for your email design, you can copy and paste it into the editor.

### Check alerts {#alerts}

[!DNL Adobe Marketo Optimizer] surfaces issues in the top-right corner of the email page. Resolve all errors before activating the journey. Warnings are recommendations only.

**Errors** (prevent journey activation):

* From name is empty
* Subject line is missing
* Email content is empty

**Warnings** (recommendations):

* Opt-out link is not present in the email body
* Text version of HTML is empty
* Empty links detected
* Email exceeds 100 K

## Optimize email HTML size {#optimize-html-size}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_email_minification"
>title="Reduce HTML size"
>abstract="Enable this option to compress your email HTML during publishing by removing unnecessary whitespace, indentation, and non-essential comments. This helps prevent email clipping in clients such as Gmail, which truncates messages exceeding 100 KB."

[!DNL Marketo Optimizer] allows you to compress your email HTML version during the publishing process by removing unnecessary whitespace, indentation, and non-essential comments. Keeping HTML size small helps you:

* Avoid **email clipping** — some clients such as Gmail truncate messages larger than ~100 KB, preventing recipients from viewing the full content.
* Improve **email load time** in the recipient's inbox.
* Improve **deliverability** and reduce bandwidth usage.

This optimization is not applied automatically — you must enable it in the _[!UICONTROL Content]_ tab.

<!-- ![](assets/email-optimize-html-size.png) -->

>[!IMPORTANT]
>
> The HTML size reduction is only applied at publication time.

The optimization is email-client safe:

* It preserves MSO/Outlook conditional comments.
* It does not alter your actual content, images, or videos.

>[!NOTE]
>
>The reduction in email size depends on the original HTML structure of your email. If the content is already compact or the email payload is very large, the reduction may be minimal and may not fully prevent clipping in all cases.

<!-- 
Proof and simulate workflows are not available in this release. See [Current limitations](#limitations).

### Test HTML size optimization {#optimize-html-proof}

If you have enabled the [HTML size optimization](#optimize-html-size) option, you can evaluate its impact before publishing when sending proofs. Follow the following steps.

1. In the email design space, click the _Issues_ icon on the top right. If the rendered email size exceeds 100 KB, a message is displayed to warn you that this may cause truncation in some email clients.

1. Click **[!UICONTROL Simulate content]**.

1. To test the optimized version, click the **[!UICONTROL Send proof]** button and select the **[!UICONTROL Optimize HTML size]** option. This will send a proof with the reduced HTML size to your test recipients.

    >[!NOTE]
    >
    >This setting is independent from the email editor — the proof reflects what you select in the proof, regardless of whether the option is enabled or disabled in the email itself.

1. Select the test recipients and click **[!UICONTROL Send proof]**.

1. Back in the **[!UICONTROL Simulate]** screen, click the **[!UICONTROL View Proof]** button.

1. Click the _Information_ icon next to the status of the proof.

   The optimization details are displayed in a pop-up window, including the original HTML size, the optimized HTML size, and the size reduction percentage.
    
    Use this information to validate the optimized output and confirm the email stays within the recommended 100 KB threshold before publishing.

-->
