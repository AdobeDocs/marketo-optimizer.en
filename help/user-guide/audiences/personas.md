---
title: Derived Personas
description: Use derived personas in Marketo Optimizer to target people lists and journey paths. Learn default persona mappings and the Derived Persona filter.
---
# Derived personas

Persona classification transforms raw customer data into semantic buyer understanding that AI can use to generate context and drive personalized decisions across every channel and journey. This unified profile empowers:

* _Journey branching_ – Split paths route leads by persona, engagement depth, and role
* _Journey arbitration_ – Determines which nurture journey a lead belongs to right now, avoiding message collisions across concurrent programs
* _Content personalization_ – Content that is role-specific narratives ("for an executive" or "for a practitioner")
* _Sales Qualifier context_ – Business development representatives (BDRs) receive a one-screen summary showing the individual's identity, their interests, and their current stage in the buyer journey

## Default personas {#default-ersonas}

For the Beta release of Marketo Optimizer, the following default personas are defined according to the job title attribute:

| Persona | Job titles |
| ------- | ---------- |
| [!UICONTROL CXO / EVP] | CEO, CIO, CTO, CMO, CFO, Executive Vice President of Strategy |
| [!UICONTROL SVP / VP] | SVP of Marketing, VP of Sales, SVP of Operations, VP of Product, VP of IT |
| [!UICONTROL Senior Manager / Manager] | Senior Marketing Manager, IT Manager, Operations Manager, Sales Manager, HR Manager |
| [!UICONTROL Individual Contributor] | Account Executive, Software Engineer, Marketing Specialist, Customer Success Representative |
| [!UICONTROL Analyst] | Business Analyst, Data Analyst, Market Research Analyst, Financial Analyst, Operations Analyst |
| [!UICONTROL Developer] | Front-End Developer, Back-End Developer, Full-Stack Developer, Mobile App Developer, DevOps Engineer |
| [!UICONTROL Professional Staff] | HR Specialist, Legal Counsel, Compliance Officer, Project Manager, Procurement Specialist |
| [!UICONTROL Consultant] | Management Consultant, IT Consultant, Business Process Consultant, Marketing Consultant |
| [!UICONTROL Other] | Industry Specialist, Independent Advisor, Freelance Consultant, Subject Matter Expert |

>[!NOTE]
>
>In the upcoming General Availability release, you can edit any of these default personas according to the needs of your organization. It will also support custom persona definitions and mapping.

## Filter by derived persona {#derived-persona-filter}

[!DNL Marketo Optimizer] derives a persona for each person record by evaluating the record attributes against the defined personas. You can use the inferred result — the _Derived Persona_ — as a filter when defining the audience for a people list or for segmenting in a person journey.

The _[!UICONTROL Derived Persona]_ filter appears in the filter panel under the **[!UICONTROL Person attributes]** category.

### People lists {#people-lists}

When managing members in a [static people list](./people-lists.md#static-lists) or defining rules for a [dynamic people list](./people-lists.md#dynamic-lists), you can filter by _Derived Persona_ to target all people whose attributes match a specific configured persona.

![Derived persona filtering for a people list](./assets/derived-persona-filter-people-list.png){width="750" zoomable="yes"}

**Static list — Add members**

1. Open the static list and click **[!UICONTROL Add people]** at the top right.

1. In the filter dialog, expand **[!UICONTROL People attributes]** and drag **[!UICONTROL Derived Persona]** onto the canvas.

1. In the filter condition, choose **[!UICONTROL is]** and select one or more personas from the list.

1. Click **[!UICONTROL Done]** to apply the filter and qualify matching people into the list.

**Dynamic list — Set membership rules**

1. Open the dynamic list and select the **[!UICONTROL Rules]** tab.

1. Click **[!UICONTROL Edit rules]**.

1. In the filter dialog, expand **[!UICONTROL People attributes]** and drag **[!UICONTROL Derived Persona]** onto the canvas.

1. In the filter condition, choose **[!UICONTROL is]** and select one or more personas from the list.

1. Click **[!UICONTROL Done]** to save the rule.

   Membership is updated automatically as person records are evaluated against the rule.

### Person journeys {#person-journeys}

When you configure segmentation for a person journey in a [_Split paths_ node](../marketing/split-merge-paths-nodes.md), you can use a derived persona as a person profile filter to control which people enter the journey path.

![Derived persona filtering for a split path condition](./assets/derived-persona-filter-split-path.png){width="750" zoomable="yes"}

1. Click the **[!UICONTROL Split paths]** node in the journey canvas.

1. In the node properties panel on the right, click **[!UICONTROL Apply condition]** or **[!UICONTROL Edit condition]** for a path.

1. In the filter dialog, expand **[!UICONTROL People attributes]** and drag **[!UICONTROL Derived Persona]** onto the canvas.

1. In the filter condition, choose **[!UICONTROL is]** and select one or more personas from the list.

1. Click **[!UICONTROL Done]** to save the filter for the path.

