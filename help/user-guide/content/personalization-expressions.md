---
title: Personalization Editor
description: Learn how to use the personalization editor in Marketo Optimizer to select, arrange, customize, and validate profile-attribute tokens in emails, WhatsApp messages, landing pages, and URL fields.
feature: Content Design Tools
role: User
---
# Personalization editor

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_personalization_editor"
>title="About the personalization editor"
>abstract="The personalization editor allows you to select, arrange, customize, and validate profile attributes to create personalized content."

The personalization editor is the centerpiece of personalization in [!DNL Marketo Optimizer]. Use it wherever you need dynamic content — in emails, WhatsApp messages, landing pages, and URL fields.

In the personalization editor interface, you can select, arrange, customize, and validate profile attributes to create personalized content.

![Personalization expression editor](./assets/personalization-editor.png){width="700" zoomable="yes"}

>[!NOTE]
>
>Only profile attributes are available in the personalization editor in this Beta release. Account-level personalization and custom-object data are not available. See [Current limitations](../marketing/email-channel.md#limitations).

You can add personalization in any field with the _Personalize_ ( ![Personalize icon](../assets/do-not-localize/icon-personalize.svg) ) icon. Expand the following sections for more details.

+++Emails and WhatsApp messages

In [emails](./email-authoring.md#personalize-content) and [WhatsApp messages](./whatsapp-authoring.md#personalize-message-content), personalization can be added at different locations, such as the **[!UICONTROL Subject line]** field in an email or dynamic parameters in an approved WhatsApp template.

It can also be added in other sections of your content, including email body text, preheaders, and button URLs.

+++

+++Content design space

When editing visual content, you can add personalization in most of the text elements using the icon in the contextual tool bar.

<!-- ![](assets/perso_insert.png) -->

+++

+++URLs

[!DNL Marketo Optimizer] also allows you to personalize **URLs** in your messages. Personalized URLs take recipients to specific pages of a website, or to a personalized microsite, depending on the profile attributes.

<!-- ![](assets/perso-url.png){width="50%"} -->

>[!NOTE]
>
>URL personalization is available for these types of links: **External link**, **Unsubscription link** and **Opt-Out**.

+++

+++Email configuration

When creating an [email channel configuration](../admin/email-channel-configuration.md), you can define personalized values for subdomains, headers, and URL tracking parameters.

+++

## Add personalization {#add}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_perso_editor_autocomplete"
>title="Auto complete"
>abstract="Toggling on this option allows the system to automatically suggest and complete code as you type. This feature is available only for HTML and Text formats and supports profile attributes. If disabled via the toggle, the editor will provide native HTML code auto-completion instead."

The central workspace is where you build your personalization syntax. To use an attribute to personalize your message, locate it into the left navigation pane and click the `+` button to add it into the expression. 

<!-- ![](assets/personalization-add-attribute.png) -->

The ellipsis menu next to the `+` icon allows you to get more details for each attribute and to add your most frequently used attributes to favorites. Attributes added to favorites are accessible from the **[!UICONTROL Favorites]** menu in the navigation pane.

>[!NOTE]
>
>By default, the attributes pane shows only populated attributes. To display all attributes, select the **[!UICONTROL Settings]** button in the attributes pane and toggle off the **[!UICONTROL Show only populated attributes]** option.

Additionally, you can define default fallback text that will display if a string-type profile attribute is empty. To do this, click the ellipsis button next to the attribute and select **[!UICONTROL Insert with fallback text]**. Write the text that should display by default if the attribute's value is empty for a profile then click **[!UICONTROL Add]**.

<!-- ![](assets/attribute-details.png) -->

For example, you can greet each recipient by first name using `{{profile.firstName}}` with a fallback when the value is missing: `{{profile.firstName | default: "there"}}`.

## Options for expression editing {#options}

The central workspace provides various tools to help you write your personalization expression.

<!-- ![](assets/perso-workspace.png) -->

Available options are:

1. **[!UICONTROL Find]** / **[!UICONTROL Find and replace]**: Search through your expression and automatically replace portions of code.
1. **[!UICONTROL Undo]** / **[!UICONTROL Redo]**: Undo / Redo the last operation.
1. **[!UICONTROL Auto complete]**: Automatically suggests and completes code as you type. This feature is available only for HTML and Text formats and supports profile attributes. If disabled via the toggle, the editor will provide native HTML code auto-completion instead.

    <!-- ![](assets/perso-complete.png){width="70%" align="center" zoomable="yes"} -->

1. **[!UICONTROL HTML]** / **[!UICONTROL JSON]** / **[!UICONTROL Text]**: Identify the format of your code. This allows the system to adapt the validation and auto complete feature based on the selected language.
1. **[!UICONTROL Validate]**: Check the syntax of your expression.
1. **[!UICONTROL Font size]**: Adjusts the font size for the contents inside the editor for better readability.
1. **[!UICONTROL Word wrap]**: Enables or disables word wrapping, allowing long expressions to be displayed on a single line or wrapped within the editor. Options include:
    * **Off** (Default) - No word wrapping. Long lines extend beyond the editor view and require horizontal scrolling.
    * **On** - Wraps lines at the width of the editor.
    * **Word wrap column** - Wraps lines when a line reaches 80 characters.
    * **Bounded** - Wraps lines at either the editor width or at 80 characters, whichever is smaller.
1. **[!UICONTROL Pills]**: Display attributes as compact "pills" to improve readability by hiding long attribute paths. Click on an attribute to display its full path.

   >[!NOTE]
   >
   >This option is only available for profile attributes.

In the navigation pane, additional features are available to help you build your personalization expression.

<!-- ![](assets/perso-features.png) -->

* **[!UICONTROL Helper functions]** - Helper functions allow you to perform operations on data, such as calculations, data formatting or conversions, conditions, and manipulate them in the context of personalization.

* **[!UICONTROL Favorites]** - Attributes that you have added to favorites display in this list. This allows you to quickly access your most frequently used items. To add an attribute to your favorites, click the ellipsis menu and choose **[!UICONTROL Add to favorites]**.

The Coworker can generate Handlebars expressions from plain-language descriptions, explain existing expressions, and identify potential issues.

When your personalization expression is ready, click **[!UICONTROL Confirm]** or **[!UICONTROL Insert]** to add it to your content.

## Validation mechanisms {#validation-mechanisms}

The validation of your expression runs automatically when you click **[!UICONTROL Confirm]** or **[!UICONTROL Insert]** to close the editor. You can also click **[!UICONTROL Validate]** to check your personalization syntax before closing.

For content alerts that block journey activation, see [Validating email content](./email-authoring.md#validation).

Expand the following section to see common errors that may occur when validating personalization.

+++Common errors

* **Path "XYZ" not found**

This error occurs when you reference a field that is not defined in the schema.

In this case **firstName1** is not defined as an attribute in the profile schema:

```handlebars
{{profile.firstName1}}
```

* **Type mismatch for variable "XYZ". Expected array. Found string.**

This error occurs when you try to iterate over a string instead of an array.

In this case **jobTitle** is a string, not an array:

```handlebars
{{#each profile.jobTitle as |item|}}
  {{item}}
{{/each}}
```

* **Invalid handlebars syntax. Found `'[XYZ}}'`**

This error occurs when invalid Handlebars syntax is used.

```handlebars
{{[profile.firstName}}
```

+++