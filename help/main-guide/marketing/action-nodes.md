---
title: Take an Action Node
description: Configure a Take an action node in Marketo Optimizer to add, remove, or update people, lists, programs, and destinations, or to send messages, when they reach the node in a person journey.
---
# Take an action node

In a person journey, use an action on people when you want to apply a change to all people on the node path.

## Actions and constraints {#actions}

| Action | Constraints |
| ------ | ----------- |
| **[!UICONTROL Activate to destination]** | <li>Select or create a static list <li>If the list does not have an activated destination, activate the list to one or more destinations |
| **[!UICONTROL Add person to journey]** | <li>Select a scheduled or live journey <li>Audience criteria of the target journey are not applied |
| **[!UICONTROL Add to list]** | <li>Create a new static list or select an existing one |
| **[!UICONTROL Add to Marketo Engage list]** | <li>Select a static list in Marketo Engage |
| **[!UICONTROL Change data value]** | <li>Select person attribute <li>Set new value |
| **[!UICONTROL Change status in program]** | <li>Select program<li>Select new status |
| **[!UICONTROL Change webinar member status]** | <li>Select program<li>Select new status |
| **[!UICONTROL Remove from list]** | <li>Select Static List <li>Skips person if not currently a member |
| **[!UICONTROL Remove from Marketo Engage list]** | <li>Select a static list in Marketo Engage <li>Skips person if not currently a member |
| **[!UICONTROL Remove person from journey]** | <li>Select a live journey <li>Skips person if not currently a member of the target journey |
| **[!UICONTROL Request Marketo Engage campaign]** | <li>Select a Marketo Engage campaign |
| **[!UICONTROL Send Email]** | <li>Create, edit, or use an AI-personalized email <li>Send-time optimization (optional) |
| **[!UICONTROL Send WhatsApp]** | <li>Select a WhatsApp message |

<!-- 
removed? | **[!UICONTROL Change Program Data]** | <li>Select program attribute <li>Set new value | 
-->

## Add an action node {#add-an-action-node}

1. Navigate to the journey canvas.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Take an action]**.

   ![Click add icon on journey path](./assets/person-journey-canvas-add-node.png){width="200"}

1. In the node properties on the right, select an action from the list and set any values for the action.

+++Activate to destination

Use this action to add people to a static list and activate that list to a destination directly from your journey. You can use an existing static list, or create one specifically for the journey.

>[!PREREQUISITES]
>
>You must have one or more [configured destinations](../audiences/destinations.md) for your [!DNL Marketo Optimizer] sandbox before you set up an _Activate to destination_ journey node.

![Take an action - Activate to destination](./assets/person-action-node-activate-to-destination.png){width="450"}

Under **[!UICONTROL Add to list]**, choose one of the following options:

* **[!UICONTROL Create]** — Create a new static list and add people to it. The list is immediately available under **[!UICONTROL People lists]**.

   Select a parent program for the list and enter a **[!UICONTROL Name]** (required) and **[!UICONTROL Description]** (optional). Click **[!UICONTROL Create]** to add the new list for the node.

   ![Create a static list to use for the journey node](./assets/person-action-node-destination-create-list.png){width="375"}
  
* **[!UICONTROL Select]** — Select an existing static list where you want to add people who reach the node.

   Select the checkbox for the existing static list and click **[!UICONTROL Save]**.

   ![Select a static list to use for the journey node](./assets/person-action-node-destination-select-list.png){width="700" zoomable="yes"}

Anyone who reaches the node is added to the selected static list, but the action is not complete until the list is activated to a destination:

* If the selected list is already activated, its destinations appear under **[!UICONTROL Destinations]** and the action is ready.
* Otherwise, an _At least one destination is required_ message appears. Click **[!UICONTROL Activate list to destination]**, select the destination, and click **[!UICONTROL Save]**. Click **[!UICONTROL Activate]** in the confirmation dialog.

![Configured destinations available for activation](../audiences/assets/static-list-activate-destination-select.png){width="600" zoomable="yes"}

When activation completes, the destination appears under **[!UICONTROL Destinations]** and the action is ready. You can activate the list to additional destinations if needed.

Anyone who reaches the node is added to the selected static list, which is activated to the chosen destination, so they are added to that destination audience and, in turn, to any campaign that the audience feeds.

+++

+++[!UICONTROL Add person to journey]

Use this action to add people to other scheduled or live journeys. People added through this action are immediately added to the audience of the target journey; the audience criteria of the target journey are not applied.

![Take an action - Add person to journey](./assets/person-action-node-add-to-journey.png){width="450"}

+++

+++[!UICONTROL Add to list]

Use this action to add people to a static list in Marketo Optimizer.

![Take an action - Add to list](./assets/person-action-node-add-to-list.png){width="450"}

Choose one of the following options:

* **[!UICONTROL Create]** — Create a new static list asset and add people to it. The list is immediately available for use by other assets in Marketo Optimizer.
* **[!UICONTROL Select]** — Select an existing static list asset where you want to add people who reach the node.

+++

+++[!UICONTROL Add to Marketo Engage list]

Use this action to add people to a static list in Marketo Engage.

![Take an action - Add to Marketo list](./assets/person-action-node-add-to-marketo-list.png){width="450"}

+++

+++[!UICONTROL Change data value]

Use this action to update the value of an attribute on a person record. Select the attribute and set the new value.

>[!TIP]
>
>To clear the value of an attribute, set the value to `NULL`.

![Take an action - Change data value](./assets/person-action-node-change-data-value.png){width="450"}

+++

+++[!UICONTROL Change status in program]

Use this action to change the status of a person in a Marketo Engage program. Select the program and then select the new status.

![Take an action - Change program status](./assets/person-action-node-change-status-program.png){width="450"}

+++

+++[!UICONTROL Change webinar member status]

Use this action to change the status of a person in relation to an interactive webinar. Select the webinar and then select the new status.

![Take an action - Change program status](./assets/person-action-node-change-webinar-status.png){width="450"}

+++

+++[!UICONTROL Remove from list]

Use this action to remove people from a static list in Marketo Optimizer. If a person is not currently a member of the list, the action is skipped for that person.

![Take an action - Remove from list](./assets/person-action-node-remove-from-list.png){width="450"}

+++

+++[!UICONTROL Remove from Marketo Engage list]

Use this action to remove people from a static list in Marketo Engage. If a person is not currently a member of the list, the action is skipped for that person.

![Take an action - Remove from Marketo list](./assets/person-action-node-remove-from-marketo-list.png){width="450"}

+++

+++[!UICONTROL Remove person from journey]

Use this action to remove people from other live person journeys. The person is immediately removed from the target journey and no further actions are taken on them. If a person is not currently a member of the target journey, the action is skipped for that person.

![Take an action - Remove person from journey](./assets/person-action-node-remove-from-journey.png){width="450"}

+++

+++[!UICONTROL Request Marketo Engage campaign]

Use this action to add people to a request campaign in a connected Marketo Engage instance. Select the Marketo Engage campaign to request.

![Take an action - Request Marketo campaign](./assets/person-action-node-request-marketo-campaign.png){width="450"}

+++

+++[!UICONTROL Send Email]

Use this action to send an email to opted-in people. People who are unsubscribed, block listed, email suspended, or marketing suspended skip this action.

![Take an action - Send email](./assets/person-action-node-send-email.png){width="450"}

You can create an email, edit an existing email, or use an AI-personalized email. For information about creating and editing emails, see [Email channel](./email-channel.md). To generate persona-based variants for an existing email, see [Personalize email content by persona](../agents/personalize-content.md).

You can use [Send-time optimization](./email-send-time-optimization.md) to personalize email delivery timing by predicting when each profile is most likely to engage.

+++

+++[!UICONTROL Send WhatsApp]

Use this action to send a WhatsApp message. You can create, personalize, and preview WhatsApp messages in the visual design space (see [WhatsApp authoring](../content/whatsapp-authoring.md)).

![Take an action - Send WhatsApp](./assets/person-action-node-send-whatsapp.png){width="450"}

+++
