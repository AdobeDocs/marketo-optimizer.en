---
title: Person Audience Journey Node
description: Configure the person audience node in Journey Optimizer B2B to specify which profiles enter a journey using dynamic people lists or event-based audiences.
TQID: 'https://experienceleague.adobe.com/WqM-yLPadt6lBFtqJOGUxDtk0fm6n6S29wQTRSWB8fY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
---
# Person audience node

The _person audience_ node specifies which person profiles enter the journey. When you [create a person journey](./person-journeys.md), the journey always starts with a person audience node that defines its input. The person audience node can have one of two audience input types: a dynamic people list or an event trigger.

If the dynamic people list that you need for the person journey does not aleady exist, [create the people list](../audiences/people-lists.md#create-a-people-list) and then configure the Person audience node.

_To configure the journey audience:_

1. Click the **[!UICONTROL Person audience]** node.

   This action displays the node properties on the right.

   ![Person audience journey node](./assets/person-audience-node-properties.png){width="600" zoomable="yes"}

1. Use one of the following audience configuration options for the person audience:

   * **[!UICONTROL Dynamic list]** - Use a dynamic, rules-based people list. The list rules are evaluated at journey runtime to qualify members of the journey. People that later disqualify for the dynamic list are not removed from the journey. See _[Dynamic lists](../audiences/people-lists.md#dynamic-lists)_.

   * **[!UICONTROL Event audience]** - Use an event audience define the journey audience based on qualifying events. Define audience members using person profile filtering and trigger journey entry using event criteria. See _[Event-based audiences](../audiences/event-based-audiences.md)_.