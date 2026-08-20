---
title: Create email templates
description: Learn how to create email templates in Marketo Optimizer — create new, save an email from a journey as a template, or convert a design image to an email template.
---

# Create email templates

You can create an email template in [!DNL Adobe Marketo Optimizer] in three ways:

* **Build a new template** — Create a template in the template library using the visual email design space.
* **Save from a journey email** — Save an email you have authored in a journey as a reusable template.
* **Convert an image** — Upload a design image and use generative AI to convert it into an editable email template.

## Build a new template {#build-new}

1. In the left navigation, expand **[!UICONTROL Content Management]** and select **[!UICONTROL Templates]**.
1. Click **[!UICONTROL Create template]**.
1. Enter a **[!UICONTROL Template name]** and optional **[!UICONTROL Description]**.
1. Set the **[!UICONTROL Channel]** (type) for the template.

   >[!NOTE]
   >
   >In this Beta release, only email templates are supported.

   <!-- 1. Optionally add **[!UICONTROL Tags]** to categorize the template. -->

1. Click **[!UICONTROL Create]** to open the email design space.

1. Click **[!UICONTROL Edit email body]** to access the content design space. 

   See [Email authoring](email-authoring.md) for detailed information about content design.

1. Optionally enable **[!UICONTROL Governance]** and configure [content locking](template-content-governance.md) to restrict which parts of the template authors can edit when applying the template.

1. Click **[!UICONTROL Save]**.

## Save an email as a template {#save-as-template}

When you open the email conetnt that you want to reuse, save it directly to the template library from within the email content page.

1. Click **[!UICONTROL Content template]** at the top of the page.
1. Select **[!UICONTROL Save as content template]**.
1. Enter a **[!UICONTROL Name]** and optional **[!UICONTROL Description]**.
1. Optionally add **[!UICONTROL Tags]**.
1. Click **[!UICONTROL Create]**.

The original journey email is unaffected. The saved template is available in the template library for all users in the sandbox. You can update the created template to optimize reuse:

* Edit text and add [personalization](email-authoring.md#personalize-content) tokens.
* Update or replace images and add links.
* Configure [content locking](template-content-governance.md).

## Convert an image to a template {#image-to-template}

[!DNL Adobe Marketo Optimizer] can convert a static image — such as a mockup from Figma or Photoshop — into an editable email template using generative AI. This eliminates the need to manually rebuild layouts from design files, and is ideal for migrating existing email designs from other platforms. This feature is available for email content templates only.

>[!BEGINSHADEBOX]

### Prerequisites

Before you begin:

* Your organization must have signed the Generative AI addendum with Adobe.
* You must have the **[!UICONTROL Generate Content]** permission in addition to **[!UICONTROL Manage content templates]**.
* The image file must meet these specifications:
  * Format: JPEG (.jpg, .jpeg) or PNG (.png)
  * Maximum file size: 10 MB
  * Recommended width: 600–800 pixels
  * Clear, high-quality image with readable text and distinct visual elements

>[!IMPORTANT]
>
>The image must not contain personally identifiable information (PII) or sensitive data.

>[!ENDSHADEBOX]

### Create the template

1. In the left navigation, expand **[!UICONTROL Content Management]** and select **[!UICONTROL Templates]**.
1. Click **[!UICONTROL Create template]**.
1. Enter a **[!UICONTROL Template name]** and optional **[!UICONTROL Description]**.
1. Set the **[!UICONTROL Channel]** to Email.

   <!--  Optionally add **[!UICONTROL Tags]** to categorize the template. -->

1. Click **[!UICONTROL Create]**.

### Generate the template content

1. In the **[!UICONTROL Convert image to template]** section:

   * Optionally select a **[!UICONTROL Brand theme]** to apply your brand's colors, fonts, and spacing to the generated output.
   * Select the acknowledgment check box to confirm that your image contains no personally identifiable information (PII) or other sensitive data.
   * Click **[!UICONTROL Upload image]** and select your image file.

   >[!CAUTION]
   >
   >Uploading an image deletes any content currently in the email and replaces it with the generated template.

1. If prompted, review and accept the Adobe Generative AI User Guidelines.

1. Click **[!UICONTROL Open]** to start the conversion process.

   Conversion typically completes within about five minutes. Complex or large images may take up to ten minutes. The conversion runs in the background — you can navigate away and the draft template auto-saves when conversion is complete.

1. Refresh the page to see the completed template.

   >[!NOTE]
   >
   >The result is not displayed automatically. Refresh the page or return to the template library to see the completed template.

1. Optionally, use the **[!UICONTROL Image to template converter feedback]** section to share suggestions with Adobe.

1. Click **[!UICONTROL Edit email body]** to open the converted template in the email design space for editing.

1. Click **[!UICONTROL Save]**.

### Edit the converted content

The converted template content opens in the design space as a fully editable email template. Use the standard content design tools to:

* Edit text and add [personalization](email-authoring.md#personalize-content) tokens.
* Update or replace images and add links.
* Adjust colors, fonts, and spacing.
* Add, remove, or rearrange content components.
* Enable governance and configure [content locking](template-content-governance.md).

>[!IMPORTANT]
>
>The generative AI produces static HTML based on the visual image. Review all text for accuracy and add personalization, dynamic content, and tracking manually after conversion.

The converted template is automatically saved to the template library when conversion is complete.

### Tips for best results

Use the following guidelines to get the best results from image-to-template conversion:

**Before conversion:**

* Use the highest-resolution version of your design file.
* Design at standard email widths (600–800 pixels) and include the complete layout — header through footer — in a single image.
* Ensure sufficient contrast between text and backgrounds, and use readable font sizes.

**Design for accurate conversion:**

* Use simple, well-structured layouts with clear separation between sections.
* Follow standard email patterns — header, body, calls to action, footer — rather than complex multi-layered designs.
* Keep visual elements distinct so the AI can correctly identify structural boundaries.

**After conversion:**

* Test rendering across email clients and devices before using the template in a journey.
* Verify alignment with brand colors, fonts, and style guidelines.
* Review and enhance accessibility, including image alt text.
