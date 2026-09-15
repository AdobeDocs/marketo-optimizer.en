---
title: Split and Merge Paths Nodes
description: Learn how to use split and merge paths nodes in person journeys to segment people into distinct paths based on defined conditions, then reunite them at a common point downstream.
TQID: 'https://experienceleague.adobe.com/XMN7lgb77bFlJkNXrmPf9ZSCV-GgIuybtr-O3AsqT2U'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
---
# Split and merge paths nodes

Use split and merge paths nodes in person journeys to segment people into distinct paths based on conditions you define, then merge those paths so the journey can continue. Split paths let you tailor actions and events to specific audience segments, while merge paths combine those segments at a common point.

## Split paths nodes

Use split nodes to segment people according to the conditions that you define. Create paths for the audience list according to conditions, define each path with action and event nodes for the segment, and then combine the paths and continue the journey.

A Split paths node defines one or more segmented paths based on people filters.

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_**How a split path node functions**_

* Evaluation of each path is from top to bottom. If a person matches the first and second paths, they proceed along the first path only.
* The node supports the definition of an _Other people_ path, where you can add actions or events for people that do not match one of the defined segments/paths.

### Matched person filters

For each path that you define for the node, use the following filter types to match people according to one or more conditions.

| Filters | Description |
| ------- | ----------- |
| Activity history | Activities based on conditions that are evaluated using one or more selected items |
| Brand Concierge | Activities for leads engaging with [!DNL Brand Concierge]. |
| Company attributes | Attributes from the company/account profile, including: <li>Annual revenue <li>Company name <li>Billing country <li>Industry <li>Num employees <li>SIC code <li>State |
| Intent data | Attributes based on intent data associated with the person profile. |
| Opportunities | Attributes based on the opportunities associated with the person profile. |
| Person attributes | Attributes from the B2B person profile, including: <li>City <li>Country <li>Date of birth <li>Email address <li>Email invalid <li>Email suspended <li>First name <li>Inferred state region<li>Job title <li>Last name <li>Mobile phone number <li>Person engagement score <li>Phone number <li>Postal code <li>State <li>Unsubscribed <li>Unsubscribed reason |
| Sales apps | Lead activities related to [!DNL Sales Qualifier] or [!DNL Marketo Sales Insights]. |
| Special filters | Filtering attributes that do not fall under the predefined categories, providing flexibility for custom or miscellaneous filter criteria. |

>[!BEGINSHADEBOX]

**Supported [!DNL Marketo Optimizer] activities for condition filters**

For path conditions, [!DNL Marketo Optimizer] supports activities from the [!DNL Marketo Engage] instance that is connected as the data source. 

>[!NOTE]
>
>There can be only one [!DNL Marketo Engage] instance as the data source and it is preconfigured at time of provisioning of your [!DNL Marketo Optimizer] instance.

You can build conditions around the following [!DNL Marketo Engage] activities:

* [!UICONTROL Filled Out Marketo Engage form] - Matches leads who have completed a specific [!DNL Marketo Engage] form at any point in their non-aged-out activity log.
* [!UICONTROL Visited Marketo Engage web page] - Matches leads who have viewed a specific URL on your website or [!DNL Marketo Engage] landing pages. It functions directly using the Munchkin tracking code installed on your site. 
* [!UICONTROL Clicked link on Marketo Engage web page] - Matches leads who have clicked a specific link or asset on a tracked page.
* [!UICONTROL Was sent Marketo Engage email] - Matches leads to whom [!DNL Marketo Engage] attempted to send a specific email, accounting for deployment actions prior to hard bounces or server acceptances.
* [!UICONTROL Was delivered Marketo Engage email] - Matches a lead whose mail server (MX) returned a success response (a 250 OK message) to the [!DNL Marketo Engage] sending server.
* [!UICONTROL Marketo Engage email bounced] - Matches for leads who experienced a hard bounce (permanent delivery failure) on a specific email send or within a timeframe.
* [!UICONTROL Marketo Engage email bounced soft] - Matches leads whose emails experienced a temporary delivery failure (such as a full inbox or an offline server) rather than a permanent hard bounce.
* [!UICONTROL Unsubscribed from Marketo Engage email] - Matches leads who opted out of non-operational marketing emails. When this occurs, [!DNL Marketo Engage] automatically updates the lead's `Unsubscribed` field value to `true`, suppressing them from future standard email sends.
* [!UICONTROL Opened Marketo Engage email] - Matches leads who opened a tracked [!DNL Marketo Engage] email.
* [!UICONTROL Clicked link in Marketo Engage email] - Matches leads who clicked any link (or a specific link) inside a [!DNL Marketo Engage] email.

>[!ENDSHADEBOX]

### Add a split paths node

1. Navigate to the journey canvas.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Split paths]**.

   ![Click add icon on journey path](./assets/person-journey-canvas-add-node.png){width="200"}

1. To define a condition applicable to _[!UICONTROL Path 1]_, click **[!UICONTROL Apply condition]**.

1. To define the split path, add one or more filters in the conditions editor.

   * Drag and drop any of the people filters from the left navigation and complete the match definition.

   * Click **[!UICONTROL Add constraint]** for each constraint that you want to use to refine the filter match.

      ![Split path node - matched person filter for path condition](./assets/journey-node-split-conditions-people.png){width="700" zoomable="yes"}

   * Refine your conditions by applying the **[!UICONTROL Filter logic]** at the top. You choose to match all conditions or any one condition.

   * Click **[!UICONTROL Done]**.

1. To add more paths, click **[!UICONTROL Add path]** and repeat the previous steps to add conditions applicable to the path.

   You can also label each path based on these conditions or use the default labels.

1. If needed, reorder the paths according to the priority that you want for the split.

   Path filtering is evaluated in top-down order. Each person proceeds along the first path that matches.

   Click the up and down arrows at the top right of each path card to move it higher or lower in the list of paths.

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. Enable the **[!UICONTROL Other people]** option to add a default path for people that are not a match for the defined paths. 

   When this option is not enabled, people that do not match a defined segment/path move past the split and proceed to the next step in the journey.

When you have conditions defined for each path, you can add action or event nodes that you want to apply to people on a path.

## Merge paths nodes

1. Navigate to the journey canvas and locate the split paths node with two or more paths.

   Each path should have a combination of action and event nodes.

1. Click the plus ( **+** ) icon at the end of any one of these paths and choose **[!UICONTROL Merge paths]** from the displayed options.

1. In the node properties at the right, select the paths you want to merge.

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   At this point, the paths are merged so that people from the selected paths combine to a single path that can continue to progress through the journey.

1. If needed, you can unmerge paths by navigating back to the merge paths node properties and clearing the checkbox for any paths that you want to remove.