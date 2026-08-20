---
title: Add Custom CSS for Your Content
description: Add custom CSS to emails and landing pages for advanced styling and precise design control beyond standard components in Marketo Optimizer.
feature: Content Design Tools, Email Authoring, Landing Pages
role: User
---
# Add custom CSS for your content

You can add your own custom CSS directly within the email or landing page design space. Use custom CSS to apply advanced and specific styling, for greater flexibility and control over the appearance of your content.

The custom CSS is appended to the `<head>` section within a `<style>` tag using the `data-name="global-custom"` attribute. This structure ensures that the custom styles are applied globally to the content.

+++ Example implementation

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="content-version" content="3.3.31">
    <meta name="x-apple-disable-message-reformatting">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <style data-name="default" type="text/css">
      td { padding: 0; }
      th { font-weight: normal; }
    </style>
    <style data-name="grid" type="text/css">
      .acr-grid-table { width: 100%; }
    </style>
    <style data-name="acr-theme" type="text/css" data-theme="default" data-variant="0">
      body { margin: 0; font-family: Arial; }
    </style>
    <style data-name="media-default-max-width-500px" type="text/css">
      @media screen and (max-width: 500px) {
        body { width: 100% !important; }
      }
    </style>
    <style data-name="global-custom" type="text/css">
      /* Add you custom CSS here */
    </style>
  </head>
  <body>
    <!-- Minimal content -->
  </body>
</html>
```

+++

>[!NOTE]
>
>The custom CSS is not reflected or validated in the _[!UICONTROL Styles]_ panel for a selected component. It is entirely independent and can be modified only through the [!UICONTROL Add Custom CSS] option at the Body component level. 

## Add your custom CSS

1. With at least one content component added in the canvas, select the **[!UICONTROL Body]** component in the left navigation.

1. Select the _Styles_ tab on the right and click **[!UICONTROL Add custom CSS]**. 

   ![Access the body styles](assets/email-body-styles.png){width="800" zoomable="yes"}

    >[!NOTE]
    >
    >The _[!UICONTROL Add custom CSS]_ button is available only when the _[!UICONTROL Body]_ component is selected. However, you can apply custom CSS styles to all the components within it.

    The _[!UICONTROL Add custom CSS]_ pop-up editor is displayed with placeholder code comments.

1. Enter your CSS code in the editor.

   Make sure that the custom CSS is valid and follows the proper syntax. If the entered CSS is invalid, an error message is displayed and the CSS cannot be saved. To learn more, see [CSS validity](#css-validity).

   ![Enter custom CSS in the editor](assets/content-design-add-custom-css.png){width="450"}

1. Click **[!UICONTROL Save]** to save the custom CSS.

   The custom style sheet is applied to the existing content. You can check that your custom CSS is applied according to your needs. For information about how to make changes and adjust the style sheet application, see [Troubleshooting](#troubleshooting).

   ![Custom CSS applied to content](assets/email-body-custom-css-applied.png){width="600" zoomable="yes"}

## CSS validity {#css-validity}

>[!CAUTION]
>
>Users are responsible for the security of their custom CSS. Ensure that your CSS does not introduce vulnerabilities or conflicts with the existing content. 
>
>Avoid using CSS that could unintentionally break the layout or functionality of the content.

+++ Examples of valid CSS

```css
.acr-component[data-component-id="form"] {
  display: flex;
  justify-content: center;
  background: none;
}

.acr-Form {
  width: 100%;
  padding: 20px 100px;
  border-spacing: 0px 8px;
  box-sizing: border-box;
  margin: 0;
}

.acr-Form .spectrum-FieldLabel {
  width: 20%;
}

.acr-Form.spectrum-Form--labelsAbove .spectrum-FieldLabel,
.acr-Form [data-form-item="checkbox"] .spectrum-FieldLabel {
  width: auto;
}

.acr-Form .spectrum-Textfield {
  width: 100%;
}

#acr-form-error,
#acr-form-confirmation {
  width: 100%;
  padding: var(--spectrum-global-dimension-static-size-500);
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  gap: var(--spectrum-global-dimension-static-size-200);
}

.spectrum-Form-item.is-required .spectrum-FieldLabel:after{
  content: '*';
  font-size: 1.25rem;
  margin-left: 5px;
  position: absolute;
}

/* Error field placeholder */
.spectrum-HelpText {
  display: none !important;
}

.spectrum-HelpText.is-invalid,
.is-invalid ~ .spectrum-HelpText {
  display: flex !important;
}
```

```css
@media only screen and (min-width: 600px) {
  .acr-paragraph-1 {
    width: 100% !important;
  }
}
```

+++

+++ Examples of invalid CSS

Using `<style>` tags is not accepted:

```html
<style type="text/css">
  .acr-Form {
    width: 100%;
    padding: 20px 100px;
    border-spacing: 0px 8px;
    box-sizing: border-box;
    margin: 0;
  }
</style>

```
 
Invalid syntax such as missing braces is not accepted:

```css
body {
  background: red;
```

+++

## CSS in imported content {#imported-content}

If you want to use custom CSS with content imported into the email or landing page design space, consider the following:

* If you import external HTML content including CSS, it is populated in [!UICONTROL Compatibility mode] and the [!UICONTROL CSS styles] section is not available.

* If you import content that was originally created in the email or landing page design space with the [!UICONTROL Add custom CSS] option, the applied CSS is visible and editable from the same option.

## Troubleshooting {#troubleshooting}

If your custom CSS is not applied as expected, use the browser developer tools to inspect the content and verify that your CSS is targeting the correct selectors. As you review the styling code, consider the following:

* Check that your CSS is valid and free of syntax errors (such as missing braces, incorrect property names).

* Check that your CSS added to the `<style>` tag with the `data-name="global-custom"` attribute.

* Check if the `global-custom` style tag has the attribute `data-disabled` set to true, such as:

   `<style data-name="global-custom" type="text/css" data-disabled="true"> body: { color: red; } </style>`

* Check that your CSS is not overridden somewhere in the content, such as applied inline styling.

* Add `!important` to your declarations to ensure that they take precedence, such as:

   ```
   .acr-Form {
   background: red !important;
   }
   ```
