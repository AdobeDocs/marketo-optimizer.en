---
title: Content Governance for templates
description: Use governance settings in Marketo Optimizer to lock content in email templates at the structure or component level, controlling what email authors can edit.
---

# Content governance for templates

Content locking allows template authors to define governance rules that restrict which parts of an email template can be modified when the template is used in an email. This helps brand and compliance teams protect key design elements — such as headers, logos, and legal content — while allowing marketing teams to customize the message within the approved structure.

>[!NOTE]
>
>Content locking is an editor-level governance feature. It controls what authors can edit in the email design space but does not prevent changes made through the API.

Only users with the **[!UICONTROL Manage content templates]** permission can configure governance settings.

## Enable governance {#enable}

>[!NOTE]
>
>In this Beta release, only email templates are supported.

1. Open the template in the design space.
1. In the canvas, click the **[!UICONTROL Body]** component to select it.
1. Select the _Settings_ icon for the right panel, 
1. Toggle **[!UICONTROL Governance]**.
1. For **[!UICONTROL Mode]**, select the type of governance you want to apply:

   | Mode | Description |
   | ---- | ----------- |
   | **[!UICONTROL Content locking]** | Selectively lock specific structures or components. Unlocked areas remain editable by authors. |
   | **[!UICONTROL Read only]** | Lock the entire template. Authors can apply it to an email but cannot modify any part of its content. |

1. If you selected the Content locking mode, you can further define how users can interact with the template. 

   Toggle on the Enable content addition option and choose one of the following:

   * **[!UICONTROL Allow structure & content addition]** - Users can add structures between existing ones and add content components or fragments within editable structures.

   * **[!UICONTROL Allow content addition only]** - Users can add content components or fragments within editable structures but cannot add or duplicate structures.

### Lock a structure {#lock-structure}

1. On the canvas, select the structure (column layout) you want to protect.
1. In the right rail, enable the **[!UICONTROL Lock structure]** toggle.

All content nested within a locked structure is automatically locked. To allow a specific component inside a locked structure to remain editable, select the component and enable **[!UICONTROL Editable]** in the right rail.

By default, authors cannot delete a locked structure. To permit deletion, enable the **[!UICONTROL Allow delete]** option in the right rail.

### Lock a component {#lock-component}

Within an editable structure, you can lock individual content components.

1. Select the component on the canvas.
1. In the right rail, enable the **[!UICONTROL Lock content]** toggle and choose the lock type:

   | Lock type | Description |
   | --------- | ----------- |
   | **[!UICONTROL Locked]** | Prevents both content and style modifications. Authors cannot edit text or change the component's appearance. |
   | **[!UICONTROL Editable content only]** | Allows authors to edit text and content, but prevents style changes such as colors, fonts, and spacing. |
   | **[!UICONTROL Editable]** | Permits full modifications even within a locked structure. |

By default, authors cannot delete a locked component. To permit deletion, enable the **[!UICONTROL Allow delete]** option in the right rail.

### Allow content additions {#allow-additions}

When using **[!UICONTROL Content locking]** mode, you can allow authors to add new content to the template while keeping locked elements protected:

1. Enable **[!UICONTROL Allow content addition]**.
1. Choose whether authors can add both structures and content components, or content components only.

## Identify locked elements {#identify}

The **[!UICONTROL Navigation tree]** in the left rail shows lock and pencil icons to help authors quickly identify what they can and cannot modify:

* A **lock icon** indicates an element that is locked.
* A **pencil icon** indicates an element that is editable.

To further enhance visibility, enable the **[!UICONTROL Highlight editable areas]** toggle to visually distinguish editable from locked areas in the canvas.

## Considerations

Governance settings are saved with the template. Any email created from a governed template inherits its locking configuration at the time it is applied. Updating governance settings on a template does not affect emails previously created from it.
