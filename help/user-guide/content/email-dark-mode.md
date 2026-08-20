---
title: Dark Mode for Email Content
description: Learn about dark mode email design in Marketo Optimizer. Preview rendering, customize settings, and test across email clients.
---
# Dark mode for email content {#dark-mode}

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode"
>title="Switch to dark mode"
>abstract="Switch to dark mode to preview rendering and define custom settings. <br>Rendering depends on the recipient's email client. Not all email clients support custom dark mode."

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode_preview"
>title="Switch to dark mode"
>abstract="Switch to dark mode to preview rendering on supporting email clients. <br>The final rendering depends on the recipient's email client. Note that not all email clients support dark mode."

_Dark mode_ allows a supporting email client or app to display emails with darker backgrounds and lighter colors for text, buttons, and other visual elements. This type of display can reduce eye strain, save battery life, and improve readability in low-light environments for a more comfortable viewing experience. As a growing trend across major operating systems and apps, it is now an important consideration in modern email design to ensure that content remains legible and visually appealing for all users.

As you [create your email content](./email-authoring.md) in the [!DNL Marketo Optimizer] visual design space, you can switch to the _**[!UICONTROL Dark mode]**_ view. In this view, you can also define specific custom settings for supporting email clients when their dark mode is enabled.

## Email client considerations {#email-client-considerations}

There is significant variance in the way that different email clients and apps apply dark mode. For this reason, consider the expectations for dark mode rendering with caution. Before you use dark mode in the email design space, consider the following email client use cases:

+++Clients that do not support dark mode

Some email clients do not support this feature at all, such as:

* [!DNL Yahoo! Mail]
* [!DNL AOL]

If you define dark mode custom settings in the email design, these email clients cannot display any dark mode rendering.

+++

+++Clients applying their own dark mode

Some email clients systematically apply their own default dark mode to all received emails. They automatically adjust colors, backgrounds, images, and other elements according to their dark mode settings, and external settings are not possible. These clients include:

* Gmail (Desktop Webmail, iOS, Android&trade;, Mobile Webmail)
* Outlook Windows
* Outlook Windows Mail

In this case, the client dark mode settings override the custom dark mode settings that you define in [!DNL Marketo Optimizer].

+++

+++Clients that support custom dark mode

Many of the most popular email clients support custom dark mode rendering with the `@media (prefers-color-scheme: dark)` query, which is the method used by the [!DNL Marketo Optimizer] email styles. This list of clients includes:

* Apple Mail macOS
* Apple Mail iOS
* Outlook macOS
* Outlook.com
* Outlook iOS
* Outlook Android&trade;

In this case, the specific settings you define in [!DNL Marketo Optimizer] are rendered. However, some restrictions can apply according to each email client. For example, some clients (such as Apple Mail 16 (macOS 13)) do not generate dark mode if images are present in the email content.

For optimal results, test your content with the email clients that you are targeting.

+++

## Design for dark mode

The [!DNL Marketo Optimizer] visual design space provides two types of tools for styling your email content in dark mode:

* Use the [preview function](#preview-dark-mode) to review the default dark mode rendering for most supporting email clients.

* If you want to override the default settings of supporting email clients, define and apply [custom dark mode settings](#custom-dark-mode) to your email content.

### Preview default dark mode {#preview-dark-mode}

1. Open the email content in the email design space.

   At the top right of the canvas, there is a light-dark selector that toggles the content display between light (default) and dark mode.

   ![Email design canvas showing the light mode selector in the top right corner](assets/email-color-mode-light-selector.png){width="700" zoomable="yes"}

1. Change the selector to _Dark mode_ ( ![Dark mode icon](../assets/do-not-localize/icon-content-dark-mode.svg) ).

   The canvas displays the content using the default dark mode preview.

   By default, the dark mode preview applies the `full color invert` color scheme to all elements except images and icons. This color scheme detects areas with light and dark elements and inverts them. Light backgrounds become dark and dark text becomes light, or dark backgrounds become light and light text becomes dark.

   ![Email design canvas showing the dark mode selector and email content displayed in dark mode](assets/email-color-mode-dark-selector.png){width="700" zoomable="yes"}

>[!CAUTION]
>
>The final rendering could vary according to the recipient's email client. To see a simulation that comes as close as possible to the final result for each email client, use the Litmus email rendering integration available through **[!UICONTROL Simulate Content]** in the email design space.

### Define custom dark mode settings {#custom-dark-mode}

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode_image"
>title="Use a specific image for dark mode"
>abstract="Select another image for dark mode. <br>Adding a specific image does not guarantee correct rendering in all email clients. Not all email clients support custom dark mode."

After switching to dark mode, you can edit specific styling elements of your content that are displayed only when dark mode is enabled in the recipient's email client (provided it supports that feature).

>[!NOTE]
>
>The dark mode final rendering depends on each email client, so results can vary from one to another. Review the [email client considerations](#email-client-considerations) for more information.

The custom dark mode styling uses the `@media (prefers-color-scheme: dark)` CSS query to detect if the email client is set to dark mode and apply your defined dark-themed design.

_To define custom dark mode settings:_

1. If needed, move the selector to _Dark mode_ ( ![Dark mode icon](../assets/do-not-localize/icon-content-dark-mode.svg) ) at the top right of the design canvas.

1. Edit any styling color attributes, such as text, backgrounds, or buttons.

 ![Dark mode text styling settings panel showing color and font options](assets/email-color-mode-dark-text-settings.png){width="700" zoomable="yes"}

1. For images and icons, define specific assets for dark mode only.

   You cannot change the colors of images and icons, but you can define alternative assets to be used for dark mode. You can experiment with different color combinations for your icons or make adjustments for color and saturation for photographic images.

   ![Icons with different color combinations](../assets/do-not-localize/color-contrast-images-diagram.svg){width="80%"}

   Select any image and switch to **[!UICONTROL Dark mode]** using the dedicated toggle in the **[!UICONTROL Settings]** pane. Then, select a different image asset from the Marketo Design Studio asset picker.

   See [Insert an image from Marketo Design Studio](./email-authoring.md#insert-image) for more information about selecting an image asset.

1. At any point during your design changes, select **[!UICONTROL Switch to live view]** to check how your content might render on various device sizes.

   From this view, change the selector to _Dark mode_ ( ![Dark mode icon](../assets/do-not-localize/icon-content-dark-mode.svg) ) to preview the dark mode version of your content across different devices.

   ![Live view panel showing email content in dark mode across different device sizes](assets/email-color-mode-dark-live-view.png){width="800" zoomable="yes"}

   >[!CAUTION]
   >
   >The live view is a generic preview designed to compare how the rendering might look across various device sizes. The final rendering could vary depending on the recipient's email client.

1. When your dark mode changes are complete, click **[!UICONTROL Simulate Content]** to use the preview and proofing tools to test your email design.

1. If you have a Litmus Enterprise account, select **[!UICONTROL Render email]** to see the final dark mode rendering for various email clients in the Litmus integration.

   >[!CAUTION]
   >
   >While simulation closely approximates how emails appear in dark mode, actual rendering could differ due to variations in email service providers or device-level settings.

## Best practices {#best-practices}

As dark mode adoption increases across major email clients, it is essential to consider how your emails render in both light and dark environments—whether you are using [custom dark mode](#custom-dark-mode) or not.

Dark mode can alter colors, backgrounds, and images — sometimes overriding design choices. To ensure visual consistency, accessibility, and brand integrity, follow these best practices:

| Practice |            |
| -------- | ---------- |
| Optimize your images and logos | Checklist:<ul><li>Save logos and icons as PNG files with transparent backgrounds to avoid visible white boxes in dark mode. <li>Avoid images with hardcoded white or light backgrounds. <li>If transparency is not an option, place images on a solid background in your design to prevent awkward color inversions. |
| Watch your backgrounds | Checklist:<ul><li>Ensure sufficient contrast between text and background colors for readability in both light and dark modes. <li>Avoid relying on background colors alone for critical content. Some clients override background colors in dark mode, so ensure that key information is still visible. |
| Design accessible content in dark mode | Checklist:<ul><li>Use color combinations easy to distinguish for people with color blindness. <li>Use a midtone palette to ensure contrast against both light and dark backgrounds. <li>Use accessible color combinations with high contrast to improve readability and meet [!DNL Web Content Accessibility Guidelines (WCAG)] standards. Use tools like [!DNL WebAIM Contrast Checker] to verify color contrast. <li>Avoid thin fonts as they can impact readability. If your brand requires a thin font, bold it in dark mode. <li>Skip pure white on pure black, which can cause eye strain and could be inverted automatically in some email clients. <li>Provide accessible fallback styling if dark mode is not supported. |
| Test your emails in a dark mode environment | Checklist:<ul><li>Use the [dark mode preview](#preview-dark-mode) in the email design space, which uses inverted color schemes to spot issues early. <li>If you have a Litmus Enterprise account, use the **[!UICONTROL Render email]** option to simulate your designs across major email clients (such as Apple Mail, Gmail, and Outlook) and see how colors and images behave in dark mode. |

