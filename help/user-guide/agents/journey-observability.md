---
title: Monitor and Debug Journey Progression
description: Learn how to use the Journey Observability skill in Coworker chat to debug and monitor how people and leads move through journeys, split-path decisions, and timing.
---
# Monitor and debug journey progression

The [_Journey Observability_ skill](./skills.md#journeys) in [!DNL Adobe Marketo Optimizer] answers natural language questions about how people and leads move through journeys. Use it in the [Coworker chat interface](./chat-interface.md) to trace progression, understand split-path decisions, analyze people within journey nodes, and check timing metrics. You can also ask about behavior patterns across journeys.

* **Skill** - `journey-observability`
* **Invocation** - Ask a question in natural language, or use a slash command to run the Journey Observability skill. For example: _"How did demo_lead_24@company.com move through the LeadNurtureJourney?"_
* **Reads from** - [!DNL Marketo Optimizer] journey data; reads [!DNL Marketo Engage] static lists to check list membership

## View person or lead details {#person-details}

Ask for basic, read-only details about a person or lead to establish context before you investigate their journey. Provide the person's email address, lead ID, or lead name.

* _"Give me basic info on lead demo_lead_24@company.com."_
* _"What is the job title and country for profile john.doe@company.com?"_
* _"Show me the email and role for lead_01."_

## Trace progression through a journey {#journey-progression}

Ask how a person or lead moved through a journey to see node-level entry, exit, duration, and the path they took. Provide the person's email address or lead ID, and the journey name.

* _"How did demo_lead_24@company.com move through the LeadNurtureJourney?"_
* _"Which nodes did john.doe@company.com pass through in the Product Demo journey?"_

## Understand split-path decisions {#split-path-analysis}

Ask why a person or lead took, or didn't take, a specific path at a split node. Journey Observability explains the decision using the attribute values evaluated at that point in time. Provide the person's email address or lead ID, the journey name, and the split node ID.

* _"Why did demo_lead_24@company.com go to the 'Highly engaged' path at split node c764a9?"_
* _"Why did john.doe@company.com not take the qualified path at node ab123f in LeadNurtureJourney?"_
* _"Compare why lead_01 and lead_02 took different paths at split node x99f3b."_

## Analyze people in journey nodes {#node-analysis}

Ask for person or lead counts and details within a journey node or split path. Filter results by persona, role, location, or engagement level. Provide the node ID.

* _"Give me all people currently in the 'High engagement' path of node node-459c7c."_
* _"How many leads are in the qualification node of the Demo Nurture journey?"_
* _"Show me leads in the 'Low intent' split path filtered by role: Marketing Manager."_

## Identify patterns across journeys {#pattern-recognition}

Ask Journey Observability to identify common paths, drop-off points, and repeated behaviors across a journey. Provide the journey name, and optionally a timeframe, persona, product, or account to narrow the results.

* _"What are the most common paths SDRs take in the Product Demo journey?"_
* _"Where do leads usually drop off in the LeadNurtureJourney?"_
* _"Are there any unusual delays or unexpected pathing in the Q1 Nurture journey?"_

## Check timing and operational metrics {#operational-metrics}

Ask about entry times, wait durations, transition latency, and stalled progression for a journey. Provide the journey name, and optionally a node ID or person identifier.

* _"When did john.doe@company.com enter the Demo Follow-up journey?"_
* _"How long do leads typically wait at the qualification node in LeadNurtureJourney?"_
* _"Which leads have been stalled in the Demo Follow-up journey for more than seven days?"_

## Limitations {#limitations}

| Limitation | Detail |
|---|---|
| Editing person or lead attributes | Not supported. Update person and lead records directly in [!DNL Marketo Engage] or [!DNL Marketo Optimizer]. |
| Creating, editing, pausing, or resuming journeys | Not supported. Use the [journey canvas](../marketing/person-journeys.md) or a journey-editing skill in [Coworker skills](./skills.md#journeys) instead. |
| Changing split logic or journey configuration | Not supported. Edit split paths directly in the [journey canvas](../marketing/split-merge-paths-nodes.md). |
| Buying-group composition or account-level rollups | Out of scope. Journey Observability reports at the person and lead level only. |
| Changing journey schedules or timing | Not supported. |
