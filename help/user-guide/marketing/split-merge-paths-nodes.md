---
title: Split and Merge Paths Nodes
description: Learn how to use split and merge paths nodes in person journeys to segment people into distinct paths based on defined conditions, then reunite them at a common point downstream.
---
# Split and merge paths nodes

Use split and merge paths nodes in person journeys to segment people into distinct paths based on conditions you define, then bring those paths back together so the journey can continue. Split paths let you tailor actions and events to specific audience segments, while merge paths reunite those segments at a common point downstream.

## Split paths nodes

Use split nodes to segment people according to the conditions that you define. Create paths for the audience list according to conditions, define each path with action and event nodes for the segment, and then combine the paths and continue the journey.

A Split paths node defines one or more segmented paths based on people filters.

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_**How a split path by people node works**_ 

* Evaluation of each path is from top to bottom. If a person matches for the first and second paths, they proceed along the first path only.
* The node supports the definition of an _Other people_ path, where you can add actions or events for people that do not match one of the defined segments/paths.

### Matching filters

For each path that you define for the node, use the following filter types to match people according to one or more conditions:

* Activity history - You can define a path according to the person's activity related to:

   * Email messages
   * Change in data value

* Person attributes - Define a condition according to a person's attributes, such as country, job title, dervived persona, or list membership.

### Add a split paths node

1. Navigate to the journey canvas.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Split paths]**.

   ![Click add icon on journey path](./assets/person-journey-canvas-add-node.png){width="200"}

1. To define a condition applicable to _[!UICONTROL Path 1]_, click **[!UICONTROL Apply condition]**.

1. In the conditions editor, add one or more filters to define the split path.

   * Drag and drop any of the people filters from the left navigation and complete the match definition.

   * Fine tune your conditions by applying the **[!UICONTROL Filter logic]** at the top. You choose to match all conditions or any one condition.

      <!-- ![Split path node - conditions person filter logic](./assets/node-split-conditions-people.png){width="700" zoomable="yes"} -->

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

   Each path should have a combination of actions and events on each path.

1. Click the plus ( **+** ) icon at the end of any one of these paths and choose **[!UICONTROL Merge paths]** from the displayed options.

1. In the node properties at the right, select the paths you want to merge.

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   At this point, the paths are merged so that people from the selected paths combine to a single path that can continue to progress through the journey.

1. If needed, you can unmerge paths by navigating back to the merge paths node properties and clearing the checkbox for any paths that you want to remove.