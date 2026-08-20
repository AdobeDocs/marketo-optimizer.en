---
title: Webinar Promotion and Follow-up Journeys
description: Build promotion, delivery-day, and post-webinar nurture journeys around a webinar in Marketo Optimizer, and personalize the content with webinar tokens.
keywords: 
role: User
feature: Person Journeys
---

# Webinar promotion and follow-up journeys

After you add a webinar to a program, build one or more [journeys](./person-journeys.md) inside that same program to invite people, remind them, deliver the session, and follow up afterward.

>[!NOTE]
>
>This page covers building these journeys by hand. To have the AI Assistant build the same journeys for you from a template, see [Create webinars with AI Assistant](../agents/webinar-creation.md).

## Build a promotion journey {#build-promotion-journey}

A typical promotion journey invites people, tracks their registration, and reminds them as the webinar approaches.

1. [Create the person journey](./person-journeys.md#create-a-person-journey). 

1. [Select an audience for the journey](./person-audience-node.md).

1. Add a **[!UICONTROL Send Email]** node with an invitation email. 

   Use webinar tokens such as _Title_ and _Start Datetime_ in the content, and link to the webinar registration page.

1. Add a **[!UICONTROL Take an action]** node, select the **[!UICONTROL Change webinar member status]** action, select the webinar, and set the status to _Invited_.

   Place it immediately after the invitation **[!UICONTROL Send Email]** node.

   >[!NOTE]
   >
   >Typically, you only set _Invited_ and _Registered_ from a promotion journey. [!DNL Adobe Connect] normally sets _Attended_, _No-Show_, and _Attended on Demand_ automatically. The same action can override these later statuses from a journey if needed, but only forward, matching the linear progression described in [_Webinar status_](webinars-overview.md#webinar-status).

1. Host the registration form on a [landing page](../content/landing-pages.md).

1. Add a **[!UICONTROL Take an action]** node, select the **[!UICONTROL Change webinar member status]** action, select the webinar, and set the status to _Registered_ (triggered by the form submission).

    Moving someone to _Registered_ does two things automatically:

    * [!DNL Adobe Connect] generates that person's individual Joining URL.
    * It sends the confirmation email, if you've configured one, containing the _Joining URL_ token.

1. Build a reminder cadence using **[!UICONTROL Wait]** nodes timed relative to the webinar _Start Datetime_ token.

   For example, set it to one week before, one day before, and one hour before.

1. Add a **[!UICONTROL Wait]** node timed to the webinar _End Datetime_ token, so the journey pauses until the live session is over.

   Continue to [Build a post-webinar journey](#build-post-webinar-journey) from here.

   >[!NOTE]
   >
   >Webinar status changes aren't currently available as a **[!UICONTROL Listen for an event]** trigger. Use a timed **[!UICONTROL Wait]** node followed by a **[!UICONTROL Split paths]** node on webinar status instead, as shown below, rather than listening for the status change itself.

## Personalize emails

Webinar tokens render in email content: subject, body, preheader, and sender. See [Webinar tokens](webinars-overview.md#webinar-tokens) for the full list.

>[!NOTE]
>
>Webinar tokens are not currently available on the registration landing page or in forms. Personalize those with standard program tokens instead, and reserve webinar-specific personalization (like the Joining URL and Recording URL) for email.

>[!IMPORTANT]
>
>The **_Joining URL_** token only resolves for people whose webinar status is _Registered_ or later. The **_Recording URL_** token only resolves after the recording is published. Both resolve to an empty value beforehand rather than an error, so double-check that your emails render acceptably either way before you publish.

## Deliver the webinar {#deliver-webinar}

At the scheduled time, the webinar runs in [!DNL Adobe Connect]:

* Presenters and co-hosts join using their individual link in the **Webinar team** section of the webinar.
* Attendees join using their personal **Joining URL** token.
* [!DNL Adobe Connect] captures in-session activity (questions, poll responses, link clicks, asset downloads, and hand-raises) and sends it back to [!DNL Marketo Optimizer] as [webinar activities](webinars-overview.md#webinar-activities), available to any listening journey.

If the webinar is set to **Simulated Live**, pre-recorded content plays automatically at the scheduled time while presenters engage live through chat, polls, and Q&A.

## Build a post-webinar journey {#build-post-webinar-journey}

After the live session ends, [!DNL Adobe Connect] sets each person's webinar status to _Attended_ or _No-Show_. When the journey **[!UICONTROL Wait]** node releases, branch using that status with a **[!UICONTROL Split paths]** node.

1. Add a **[!UICONTROL Split paths]** node with a condition on the webinar status, such as _Has attended webinar_.

1. On the _Attended_ path, send a thank-you email. 

   For example, send a replay and resources follow-up. Then use a **[!UICONTROL Wait]** node and a next-step call-to-action email.

1. On the _No-Show_ path, send a _we missed you_ email.

   In the email content, invite them to watch the recording. Then use a **[!UICONTROL Wait]** node and a follow-up email summarizing the key takeaways.

1. Personalize either path further using other webinar activities.

   For example, branch or personalize based on _Responds to a poll_ with a specific answer.

1. Use the **_Recording URL_** token in either path after it is resolvable, so people can watch on demand.

   **_On-demand engagement_** (watch duration, playback link clicks, and downloads) is ingested as the same webinar activities, tagged with a mode of _On-Demand_. Unlike those activities, on-demand viewing also moves a _No-Show_ person to the _Attended on Demand_ webinar status. As a result, a _No-Show_ journey path can end up reaching people who watch the recording later. Split further on webinar status, or re-check it after a delay, if you want different treatment for people who watch on demand.
