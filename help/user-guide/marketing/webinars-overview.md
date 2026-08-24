---
title: Interactive Webinars
description: Learn the concepts behind Interactive Webinars in Marketo Optimizer, including the webinar asset model, member states, tokens, and activities.
keywords: 
role: User
feature: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
---

# Interactive webinars

Interactive webinars let you plan, promote, deliver, and follow up on a live or simulated-live webinar without leaving [!DNL Adobe Marketo Optimizer]. Delivery runs on [!DNL Adobe Connect] automatically, so you never have to switch products to design a registration page, host the live session, or pull attendance data.

>[!NOTE]
>
>This feature requires a license and is subject to additional terms and conditions. To inquire about the additional terms and conditions, review your contract or contact Adobe.

You can create a webinar two ways:

* **Conversation experience** - Ask the Coworker to schedule, promote, and report on a webinar in natural language. See [Create webinars with Coworker](../agents/webinar-creation.md).

* **Point-and-click** - Use the _[!UICONTROL Programs]_ workspace to add a webinar asset, design it, add co-hosts and presenters, build promotion and follow-up journeys, and review reporting. See [Create and design a webinar](create-webinar.md) and [Webinar promotion and follow-up journeys](webinar-journeys.md).

## Webinar as an asset

A webinar is an asset owned by a [program](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/marketing-management/programs/programs), the same way an email or a landing page is. Adding a webinar to a program registers it there, and makes its tokens, attributes, and activities available to every journey and asset in that program.

>[!IMPORTANT]
>
>A program can currently own one webinar asset. Support for multiple webinars per program is planned for a future release.

## Member states

For any person who is a member of a program that contains a webinar, three independent states apply at the same time. Each can be referenced separately in audiences and journey conditions.

| State | Owner | Values |
|---|---|---|
| Program member status | Program | Configurable per [program type](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/admin/program-types) |
| Webinar state | Webinar asset | Invited, Registered, Attended, No-Show, Attended on Demand |
| Journey state | Journey | Current node, paused, completed, and other journey runtime states |

### Webinar status

The webinar status has five values. [!DNL Adobe Connect] normally sets the value automatically, but you can also set the status with a journey action if you need to override it. To reflect attendance recorded in another system, for example, you can set the status in your journey.

| Status | How it is set | Source |
|---|---|---|
| Invited | A _Take an Action_ journey node, typically when the invitation email sends | Author-controlled |
| Registered | A _Take an Action_ journey node when the person registers. This also triggers [!DNL Adobe Connect] to generate the person's joining URL | Author-controlled |
| Attended | An event from [!DNL Adobe Connect] after the live webinar runs | System-controlled, with author override available through a journey |
| No-Show | An event from [!DNL Adobe Connect] after the live webinar runs | System-controlled, with author override available through a journey |
| Attended on Demand | An event from [!DNL Adobe Connect] when a person who didn't attend live later watches the recording | System-controlled, with author override available through a journey |

>[!IMPORTANT]
>
>Whether set automatically or set from a journey, webinar status only moves in one direction, the same way [program status](./programs.md#statuses) does. A person can move to a later state (for example, _Registered_ to _Attended_), but not back to an earlier one. Plan any author override with this linear progression in mind.

To move a person between states from a journey, use the **[!UICONTROL Change webinar member status]** action. See [Webinar promotion and follow-up journeys](webinar-journeys.md).

## Webinar tokens

Webinar tokens are available anywhere you personalize email content (subject, body, preheader, and sender). Find them in the personalization editor under **_Context > Webinar_**.

Asset-level tokens sit directly in the webinar folder:

- Title
- Description
- Start datetime, end datetime
- Duration
- Time zone
- Presenters
- Recording URL

>[!NOTE]
>
>Co-hosts are displayed in the Webinar team section of the webinar page, but are not available as a personalization token.

Per-recipient tokens live in a **Member** sub-folder:

- **Status** - The recipient's current webinar status (Invited, Registered, Attended, No-Show, or Attended on Demand). See [Webinar status](#webinar-status).
- **Joining URL** - The recipient's personal [!DNL Adobe Connect] link. This resolves only after the recipient's webinar state is Registered or later. It resolves empty for anyone at an earlier stage.
- **Recording URL** - Resolves after the recording is published after the live session, and stays empty until then. Use it conditionally in post-webinar emails so a link doesn't appear before there's a recording to show.

>[!NOTE]
>
>Webinar tokens currently render in email content only (subject, body, preheader, and sender). Support for webinar tokens in landing pages and forms is planned for a future release.
>
>Because these tokens resolve as empty rather than throwing an error, an email or page referencing them renders safely at any point in the webinar lifecycle. Preview content before and after the values are available to confirm the layout looks right either way.

## Webinar activities

Every webinar automatically reports activities that you can use as _Listen for Event_ triggers, _Split path_ conditions, audience filters, and reporting metrics:

* Asks a question
* Responds to a poll
* Clicks a link
* Downloads an asset
* Raises a hand

>[!NOTE]
>
>Webinar status changes (Invited, Registered, Attended, No-Show, Attended on Demand) are not currently available as their own _Listen for Event_ trigger or activity filter. To branch a journey on webinar status, use a _Split path_ condition on webinar state directly (described in [_Build a post-webinar journey_](webinar-journeys.md#build-post-webinar-journey)) rather than listening for a state-change activity.

Engagement from people who watch the recording after the live event is ingested as the same activities, tagged with a mode of On-Demand. Unlike the activities, on-demand engagement does create a separate webinar state: a person who didn't attend live and later watches the recording moves from **No-Show** to **Attended on Demand**.

## Prerequisites

Before you start building a webinar, make sure the following are in place.

| Prerequisite | Details |
|---|---|
| A program | The webinar is added inside an existing program. A marketing operations analyst typically creates the program first. |
| Webinar license (capacity) | A webinar license, also called a capacity entitlement, must be available before you can schedule a webinar. You choose a capacity at setup time, and higher-capacity add-ons may be available. To increase your available capacity, contact your Adobe account team. |
| [!DNL Adobe Connect] | Delivery runs in [!DNL Adobe Connect]. Provisioning happens automatically in the background. You do not need to leave [!DNL Marketo Optimizer] to author or host a webinar. |

### Permissions

Access to webinar features depends on your assigned permissions for webinars. 

| Role | What it grants |
|---|---|
| View B2B Webinars | View the webinars list, and a webinar configuration, details, and reports. The create, design, edit, and enter controls are not available through this permission, and you cannot be assigned to a webinar as a co-host or presenter. |

<!-- 
| Manage B2B webinars | Full lifecycle access: create, design, configure, schedule, edit, deliver, host, and delete a webinar. The Create, Design, Edit, and Manage controls are available only for users with this role. |
| Webinar co-host | After you are added as a co-host, this permission enables you to design and enter that webinar with co-host controls. |
| Webinar presenter | After you are added as a presenter, this permission enables you to view and enter that webinar with presenter capabilities. It grants no authoring or design access on its own. |

>[!NOTE]
>
>Co-hosts and presenters are currently defined by entering a name and email rather than selected from a picker of role-eligible users — see [Add co-hosts and presenters](create-webinar.md#add-co-hosts-and-presenters). The _Webinar co-host_ and _Webinar presenter_**_ roles still govern what that person can do when they are added as a co-host or presenter.

-->
