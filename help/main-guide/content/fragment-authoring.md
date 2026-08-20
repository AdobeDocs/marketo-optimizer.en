---
title: Fragment Authoring
description: Author reusable content fragments with visual design tools - add structure, assets, personalization, conditional content, and linked URL tracking for emails and templates in Marketo Optimizer.
---
# Fragment authoring

After you [create a fragment](./fragments.md#create-fragments), use the visual design space to author the structure and content components in your fragment.

## Add structure and content {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## Add assets {#add-assets}

In the visual design space, select the _Assets_ ( ![Assets icon](../assets/do-not-localize/icon-assets-me.svg) ) icon in the left navigation bar to browse and select image assets from the [!DNL Marketo Optimizer] asset library.

For steps to select, replace, or upload image assets, see [Use assets for content authoring](./digital-asset-management.md#assets-authoring).

## Navigate the layers, settings, and styles {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## Personalize content {#personalize-content}

[!DNL Marketo Optimizer] uses Handlebars syntax for personalization. Tokens are replaced at send time with values from each recipient's profile data.

_To add personalization:_

1. Select the text component and click the _Add personalization_ ( ![Personalize icon](../assets/do-not-localize/icon-personalize.svg) ) icon in the toolbar.
1. In the personalization dialog, browse the schema tree on the left and select a profile attribute. The editor inserts the corresponding Handlebars expression — for example, `{{profile.firstName}}`.
1. Add a fallback value to handle missing data, if needed — for example, `{{profile.firstName | default: "there"}}`.
1. Click **[!UICONTROL Confirm]** or **[!UICONTROL Insert]**. The expression appears inline in the field.

For details about expression editor tools and syntax, see [Personalization editor](./personalization-expressions.md).

## Edit linked URL tracking {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
