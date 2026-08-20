---
title: Create and Design a Webinar
description: "Add a webinar asset to a program, design it in [!DNL Adobe Connect], add co-hosts and presenters, run a test session, and edit a live webinar in [!DNL Marketo Optimizer]."
keywords: 
role: User
feature: Channels
---

# Create and design a webinar

Add a webinar to a program, design its registration and room experience, and staff it with co-hosts and presenters from within [!DNL Marketo Optimizer]. Before you start, review [Interactive webinars overview](webinars-overview.md) for the concepts behind webinar states, tokens, and roles, and confirm you have the **Create and manage webinars** role.

## Add a webinar to a program

1. Locate the program in the _[!UICONTROL Programs]_ tree structure or [create a program](./programs.md#create-program) first.

1. Click the _More menu_ ( **...** ) icon next to the program name and select **[!UICONTROL Create Webinar]**.

1. In the dialog, enter the core webinar details:

    * **Title** and **Description**.
    * **Schedule** - start date and time, time zone, and duration.
    * **Maximum audience** - the webinar license capacity to use for this session.

   ![The Schedule Webinar dialog with fields for the parent program, name, duration, time zone, start time, and maximum audience, plus Cancel and Create buttons.](assets/webinar-create-schedule-dialog.png){width="500" zoomable="yes"}

   >[!NOTE]
   >
   >Single-session versus recurring delivery, and audio/video options, are not currently configurable. Every webinar is a single, video-enabled session.

1. Add **Co-hosts** and **Presenters**.

   >[!NOTE]
   >
   >In the current release, you add everyone as an external contact by name and email, whether or not they have a role-eligible Adobe SSO account.<!-- See [Permissions](./webinars-overview.md#permissions) for what each role governs. --> For the full steps, see [_Add co-hosts and presenters_](#add-co-hosts-and-presenters).

1. (Optional) Customize the room template, branding, and layout.

   These options are managed in [!DNL Adobe Connect] and can also be refined later from the design surface. See [Design the webinar](#design-the-webinar).

1. Click **[!UICONTROL Save]**.

    Saving registers the webinar in the program and makes its tokens, attributes, and activities available to every journey and asset in that program.

>[!NOTE]
>
>Webinar authoring is equivalent to _Interactive Webinars_ in [!DNL Marketo Engage], so the fields are familiar if you have done this through that application.

## Design the webinar {#design-the-webinar}

To open the [!DNL Adobe Connect] design surface, embedded directly in [!DNL Marketo Optimizer], where you configure the room, registration page, and layouts, use _[!UICONTROL Design your webinar]_.

1. On the webinar page, click **Design your webinar**.

1. Choose a **Delivery mode**:

    - **Live** - Presenters host the session in real time.
    - **Simulated Live** - Pre-recorded content plays at the scheduled time, alongside live chat, polls, and Q&A.

1. Choose a **Webinar room**.

   Create a new room, or reuse an existing one.

1. Select a **Template**, **Language**, and **Theme**, then preview the layout.

1. Add and arrange pods as needed.

   Available pods include Share, Notes, Video, Chat, Attendee List, Files, Web Links, Polls, Q&A, and Survey.

1. Enter the room to review the experience, then exit when complete.

1. Save your changes. 

   A confirmation is displayed to indicate that the webinar was successfully designed.

>[!TIP]
>
>Design the webinar before you add co-hosts and presenters, so their access and controls apply to the finished room.

Room customization such as logo, colors, and virtual backgrounds is handled directly in [!DNL Adobe Connect].

## Add co-hosts and presenters {#add-co-hosts-and-presenters}

1. On the webinar page, go to the **Webinar team** section.

1. Click **Add co-host** or **Add presenter**.

1. In the dialog, enter the person's **[!UICONTROL First name]**, **[!UICONTROL Last name]**, and **[!UICONTROL Email address]**, then click **[!UICONTROL Add]**.

   >[!NOTE]
   >
   >In the current release, everyone is added the same way, by name and email, whether or not they have an Adobe SSO account. See [Permissions](webinars-overview.md#permissions) for what the **Webinar co-host** and **Webinar presenter** roles govern once someone is added.

    A confirmation appears after the person is added, and they're listed under **Co-hosts** or **Presenters** in the Webinar team section.

## Test the webinar {#test-the-webinar}

Before you promote the webinar, run a test session to confirm the room, pods, and presenter access all function as expected.

>[!NOTE]
>
>Test mode does not affect any person's webinar member status. You can run a test as many times as you need without registering or inviting anyone.

## Edit a live webinar {#edit-a-live-webinar}

You can edit a webinar after registrations have started, but do so with care:

- Editing the schedule can trigger update notifications to already-registered people. The ability to edit scheduled webinars is configurable.
- Fields referenced by tokens in live emails require explicit confirmation for removal since doing so breaks content that's already scheduled to send.
