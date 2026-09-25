---
title: Persona Mapping
description: Learn how to set up persona mapping in Marketo Optimizer. Map person attributes to define personas and use Derived Persona filtering in people lists and person journeys.
TQID: 'https://experienceleague.adobe.com/JCBtJN4DgQZROVDamM4eKuCiGTwJQPQY3wMxmBPFj74'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Persona mapping

Personas are a key aspect in an account-based marketing (ABM) approach because they help marketers adjust their strategies to the specific needs, preferences, and pain points of individuals within target accounts. Marketers can create detailed profiles for each persona, including their background, responsibilities, pain points, and preferred communication channels. With these definitions, administrators can configure personas according to person attributes in [!DNL Adobe Marketo Optimizer] so that people lists and person journeys can use streamlined and consistent filtering that captures these personas.

In [!DNL Marketo Optimizer], persona mapping provides an additional capability beyond role template conditions: you can filter [people lists](../audiences/people-lists.md) and [person journeys](../marketing/person-journeys.md) using **[!UICONTROL Derived Persona]** as a filter criterion. A _derived persona_ is the persona that the system infers for a person record by evaluating their attributes against all configured persona definitions.

Persona definition and usage limitations:

* You can have up to 20 personas defined in the _[!UICONTROL Persona mapping]_ list.
* Each persona can include up to five attributes in its definition.
* Across all defined personas, you can use up to ten different person attributes.

>[!BEGINSHADEBOX]

**Use case: job title variations**

Many marketing and sales teams use job titles as a way to identify different personas within an account. But titles for contacts can be inconsistent and use numerous variations for similar roles. When building people list filters or person journey audience conditions, you may need to define every possible related job title for a given role. You can simplify these definitions and group people with similar job titles under one inferred persona, which you can then target by filtering on _Derived Persona is Leadership_ instead of matching individual job title values.

>[!ENDSHADEBOX]

## Access the configured personas {#access}

Open the _Persona mapping_ panel from the Coworker [chat interface](../agents/chat-interface.md).

1. In the chat panel, type `/persona-mapping` and press **Enter**.

   This command is a navigation shortcut, listed under **[!UICONTROL Open a page]** in the slash menu.

   ![Screenshot of the chat interface slash menu showing the /persona-mapping command under Open a page.](assets/persona-mapping-open-chat.png){width="800" zoomable="yes"}

1. Coworker opens the **[!UICONTROL Persona mapping]** panel as a workspace tab, showing the list of personas.

   From this panel, you can [create](#create-a-persona), [edit](#edit-a-persona), or [delete](#delete-a-persona) personas.

   The persona list is organized as a table showing each persona name, creation date, and last modified date. <!-- You can customize the displayed table by clicking the _Column settings_ ( ![Column settings](../assets/do-not-localize/icon-column-settings.svg) ) icon in the top-right corner and selecting or clearing the column checkboxes. --> You can minimize the chat panel to increase the size of the _Persona mapping_ panel.

   ![The Persona mapping panel showing a table of default personas and a Create persona button.](assets/persona-mapping-list.png){width="700" zoomable="yes"}

1. To access the details for a persona, click the name.

### Default personas

The _Persona mapping_ list includes ten default personas that are defined according to the job title attribute. You can edit any of these default personas according to the needs of your organization:

| Persona | Job titles |
| ------- | ---------- |
| CXO / EVP | CEO, CIO, CTO, CMO, CFO, Executive Vice President of Strategy |
| SVP / VP | SVP of Marketing, VP of Sales, SVP of Operations, VP of Product, VP of IT |
| Senior Director / Director | Director of Engineering, Senior Director of Product, Director of Finance, Director of Customer Success |
| Senior Manager / Manager | Senior Marketing Manager, IT Manager, Operations Manager, Sales Manager, HR Manager |
| Individual Contributor | Account Executive, Software Engineer, Marketing Specialist, Customer Success Representative |
| Analyst | Business Analyst, Data Analyst, Market Research Analyst, Financial Analyst, Operations Analyst |
| Developer | Front-End Developer, Back-End Developer, Full-Stack Developer, Mobile App Developer, DevOps Engineer |
| Professional Staff | HR Specialist, Legal Counsel, Compliance Officer, Project Manager, Procurement Specialist |
| Consultant | Management Consultant, IT Consultant, Business Process Consultant, Marketing Consultant |
| Other | Industry Specialist, Independent Advisor, Freelance Consultant, Subject Matter Expert |

### List filtering

To locate the persona that you want, enter a text string into the search bar to match personas by name.

![Search field filtering the persona list by name, showing two matching results.](assets/configuration-persona-mapping-search.png){width="680" zoomable="yes"}

## Create a persona {#create-a-persona}

1. Click **[!UICONTROL Create persona]**.

1. Enter a unique **[!UICONTROL Name]** and **[!UICONTROL Description]** (optional) for the persona.

   ![Create persona panel with Name and Description fields and a Rules section for selecting attributes.](assets/configuration-persona-mapping-new.png){width="680" zoomable="yes"}

1. For **[!UICONTROL Rules]**, select the attributes to use for matching the persona.

   * Click **[!UICONTROL Edit rules]**.

   * In the dialog, select the checkbox for each attribute that you want to map (a maximum of five).

      You can customize the displayed table by clicking the _Column settings_ ( ![Column settings](../assets/do-not-localize/icon-column-settings.svg) ) icon in the top-right corner.

      To filter the attribute list by name, enter a text string into the search bar. You can also click the _Filter_ ( ![Filter icon](../assets/do-not-localize/icon-filter.svg) ) icon at the top left to filter the displayed list by type, _Standard_ or _Custom_.

      ![Dialog listing person attributes with checkboxes, usage status, and attribute type columns.](assets/configuration-persona-mapping-select-attributes.png){width="450" zoomable="yes"}

   * Click **[!UICONTROL Done]**.

     The selected attributes are populated in the _[!UICONTROL Persona attributes]_ section.

   * For each attribute, enter the comma-separated values that you want to match for the attribute.

1. Click **[!UICONTROL Create persona]**.

## Edit a persona {#edit-a-persona}

Click the persona name to access and edit the details for the persona.

You can change the name or description, add attributes, or update the attribute values. Click **[!UICONTROL Submit]** when your changes are complete.

## Delete a persona {#delete-a-persona}

Deleting a persona removes it from the _Persona mapping_ list and it is no longer available as a derived persona filter in people lists or person journeys.

1. On the _[!UICONTROL Persona mapping]_ page, locate the persona that you want to delete.

1. Next to the name, click the ellipses (**...**) icon and choose **[!UICONTROL Delete]**.

1. In the confirmation dialog, click **[!UICONTROL Delete]**.

## Filter by Derived Persona {#derived-persona-filter}

After personas are configured, [!DNL Marketo Optimizer] derives a persona for each person record by evaluating the record's attributes against the defined persona mappings. You can use the inferred result — the _Derived Persona_ — as a filter when defining the audience for a people list or a person journey.

The Derived Persona filter appears in the filter panel under the **[!UICONTROL Person attributes]** category alongside other inferred attributes such as journey membership.

### People lists

To target people matching a specific configured persona when managing people lists, you can filter by Derived Persona.

**Static list — Add members**

1. Open the static list and click **[!UICONTROL Add people]** at the top right.

1. In the filter dialog, expand **[!UICONTROL Person attributes]** and drag **[!UICONTROL Derived Persona]** onto the canvas.

   You can also enter the filter name in the search field to locate it quickly.

   ![Derived Persona filter added to the people list filter canvas with persona options to select.](assets/persona-mapping-derived-persona-filter.png){width="680" zoomable="yes"}

1. In the filter condition, choose **[!UICONTROL is]** and select one or more personas from the list.

1. Click **[!UICONTROL Done]** to apply the filter and qualify matching people into the list.

**Dynamic list — Set membership rules**

1. Open the dynamic list and select the **[!UICONTROL Rules]** tab.

1. Click **[!UICONTROL Edit rules]**.

1. In the filter dialog, expand **[!UICONTROL Person attributes]** and drag **[!UICONTROL Derived Persona]** onto the canvas.

   You can also enter the filter name in the search field to locate it quickly.

1. In the filter condition, choose **[!UICONTROL is]** and select one or more personas from the list.

1. Click **[!UICONTROL Done]** to save the rule.

   Membership is updated automatically as person records are evaluated against the rule.

### Person journeys

When you configure the audience for a person journey using an event audience, you can use Derived Persona as a person profile filter to control which people enter the journey.

1. Click the **[!UICONTROL Person audience]** node in the journey canvas.

1. In the node properties panel, select **[!UICONTROL Event audience]** as the audience type.

1. Under **[!UICONTROL Person profile filters]**, click **[!UICONTROL Add filter]**.

1. Expand **[!UICONTROL Person attributes]** and drag **[!UICONTROL Derived Persona]** onto the filter canvas.

   You can also enter the filter name in the search field to locate it quickly.

   ![Derived Persona filter added to a person journey event audience filter canvas.](assets/persona-mapping-derived-persona-event-filter.png){width="680" zoomable="yes"}

1. In the filter condition, choose **[!UICONTROL is]** and select one or more personas from the list.

   Only people whose derived persona matches the selected values are eligible to enter the journey.

1. Click **[!UICONTROL Save]** to save the event criteria.
