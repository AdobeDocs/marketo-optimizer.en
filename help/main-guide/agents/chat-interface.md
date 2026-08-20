---
title: Chat interface
description: Use the AI Assistant chat panel in Marketo Optimizer to build programs, journeys, and lists using natural language or the slash (/) menu.
---
# Chat interface

The chat panel is embedded throughout [!DNL Adobe Marketo Optimizer]. It is where you interact with the AI agents using plain language to build programs and journeys, create and compare people lists, investigate leads, configure scoring, and more.

Select the _AI Assistant_ icon in the left navigation to open the panel. The panel header has four controls:

| Control | Description |
|---------|-------------|
| **New conversation** | Start a fresh chat (clears the current thread). |
| **Conversation history** | Open past conversations so you can reopen one. |
| **Swap panels** | Move the chat panel to the other side of the workspace. |
| **Collapse** | Hide the panel to give the workspace more room. |

At the bottom of the panel is the message box where you can:

* Add a message and press **Enter** to send (**Shift+Enter** inserts a newline).
* Attach a file using the _Attach_ icon (supported formats: `.txt`, `.md`, `.csv`, `.json`, `.xlsx`, `.docx`, `.pdf`). Use CSV and spreadsheet uploads to start a lead import. 

## Ask AI Assistant

There are two equally valid ways to get work done — you never have to use the slash menu.

**Natural language** — Type your request the way you'd say it to a colleague:

* _"Create a welcome journey for new trial signups."_
* _"Why didn't john@acme.com enter this journey?"_
* _"Compare my 'Q3 Webinar Attendees' and 'Enterprise Accounts' lists."_

The agent matches your wording to the right skill behind the scenes and runs the appropriate workflow.

**The forward-slash (/) menu** — Type `/` to open a browsable menu of everything the assistant can do. This is useful when you want to discover capabilities or jump straight to a known workflow.

## The slash (/) menu

Use a `/` at the start of the message box, or after a space, to open the menu. As you continue typing, the list filters by name, description, or ID — for example, `/journey` narrows to journey-related commands.

Use **/** to move through entries, **Enter** or **Tab** to select, and **Esc** to dismiss. You can also click an entry directly.

Menu entries are grouped into labelled sections:

| Section | Contains |
|---------|----------|
| **Investigate** | Diagnostic, read-only lookups (for example, lead investigation, intent queries). |
| **Validate** | QA and audit workflows. |
| **Build** | Creation workflows (programs, journeys, lists, scoring). |
| **Import** | CSV lead import. |
| **Other** | Anything that does not fall into the above categories. |

The menu also lists **connectors** (for example, _Browse Marketo_ opens a picker dialog) and **navigation shortcuts** that jump you to a workspace screen.

### Select a menu item

When you select a skill or agent from the menu, a starter prompt is inserted into the message box for you to edit — it is **not** sent automatically. For example, selecting _Plan campaigns_ drops in _"Plan a new Marketo program for [campaign name]. I'll upload the brief."_ Fill in the bracketed placeholders and press **Enter** to send.

Connectors open a modal instead of inserting text. Navigation shortcuts take you directly to that screen in the workspace.

>[!NOTE]
>
>Some commands appear greyed out and marked _Coming soon_. These are gated by feature flags and are not yet active for your account — selecting one does nothing. The available set depends on which features are enabled for you.

## Skills

A skill is a packaged workflow the agent knows how to run — the building blocks behind both the `/` menu and natural-language requests. Each skill bundles step-by-step instructions and the specific tools needed for one job (for example, "publish a journey", "compare two people lists", "build a scoring model").

See _[AI Assistant Skills](./skills.md)_ for a complete list of currently supported skills.

Key things to know about skills:

* **Skills are product-scoped.** In [!DNL Marketo Optimizer] you'll see various product-specific skills (journeys, people lists, scoring, channels, send-time optimization, and so on). A few skills are [!DNL Marketo Engage]-only and a couple work in both products (lead import, product knowledge). You only see skills relevant to where you are.
* **You don't need to memorize skill names.** Describe your goal and the agent picks the matching skill. The `/` menu is a faster, discoverable shortcut to the same workflows.
* **Some skills only read; others change things.** Investigative and report skills (for example, lead investigation, intent query, send-time report) only read data. Build and configure skills (for example, journey creation, scoring) create or change data.

## Follow-up prompts

After the assistant replies, it often shows a row of clickable follow-up prompts tailored to what you just did — for example, after creating a journey it might offer _"Publish this journey"_ or _"Add a wait step"_. Click one to continue without typing. These are suggestions only; you can always type your own next message instead.

## Tips

* **Be specific with identifiers.** When investigating or editing, include the email address, person name, journey name, or list name so the agent acts on the right asset.
* **Use `/` to explore.** If you're not sure what the assistant can do, open the `/` menu and skim the categories.
* **Edit the starter prompt.** Selecting a skill gives you a template — replace the `[bracketed]` placeholders before sending.
* **Upload first for imports.** For a lead import, attach the CSV first, then describe what you want to do with it.
* **Start a new conversation** when you switch to an unrelated task, so earlier context doesn't affect the new request.
