---
title: AI Decisioning
description: Understand AI decisioning in Marketo Optimizer, the intelligence layer behind journey traffic control, next best path, send-time optimization, and other capabilities that replace static rules with outcome-driven automation.
---

# AI decisioning

AI decisioning is the intelligence layer behind Adobe Marketo Optimizer. Instead of pre-building every branch as a static rule, AI decisioning continuously evaluates the context of a profile, including journey membership, engagement history, intent scores, and real-time behavior, to determine the next best action or path for that person.

This continuous evaluation moves orchestration from static rules toward outcome-driven automation: rather than defining every condition in advance, you describe the outcome you want, and the system determines how to get there for each person.

## Capabilities {#capabilities}

AI decisioning is made up of the following capabilities:

| Capability | What it decides |
|---|---|
| [Journey traffic control](../marketing/journey-traffic-control.md) | Which journey a person should be in right now. When a person qualifies for more than one journey, journey traffic control re-routes them the moment their profile or behavior changes, rather than leaving them on a path that no longer fits. |
| [Next best path](../marketing/next-best-path.md) | The best-fit path for a person within a journey. Instead of hardcoding filter conditions, you describe intent in natural language, and the system routes each person to the best-matching path at the right moment. |
| [Send-time optimization](../marketing/email-send-time-optimization.md) | The best send window for each recipient, based on historical engagement, rather than one fixed schedule for everyone. |
| Contextual content | Persona-tailored email variants generated automatically from a content brief, for use as a single personalized email asset within journeys. _Coming soon._ |
| [Brand Concierge](https://experienceleague.adobe.com/en/docs/brand-concierge/content/home){target="_blank"} | Real-time conversational routing and response, such as chat and live assist. Brand Concierge requires additiona product entitlements. |

Some of these capabilities solve different problems within the same journey. Journey traffic control decides which journey wins priority when several journeys are competing to engage the same person at the same time. The other capabilities decide what happens after a person is already in a journey.

## Split paths and next best path {#split-paths-next-best-path}

[Split paths](../marketing/split-merge-paths-nodes.md) let you define journey branches with explicit filter conditions: if a score is above a threshold, send a person down one path, otherwise another. This rule-based logic is precise and fully auditable, but each new condition requires a new branch.

The [Next best path](../marketing/next-best-path.md) node applies AI decisioning to the same problem. Instead of a fixed threshold, the model evaluates engagement, persona, product interest, and funnel stage together, predicts the best outcome for each person, and selects the optimal path automatically.

## Data inputs {#data-inputs}

AI decisioning draws on the following categories of data:

| Category | Examples |
|---|---|
| Demographic and firmographic | Job title, industry, and company size |
| Psychographic | Lead score, urgency, and priority |
| Engagement | Score, level, trend, last activity, and channel |
| Intent | Product or keyword intent, grouped into high, medium, or low buckets |
| Persona | Role in deal, job title, and persona |

## Evaluation cadence {#evaluation-cadence}

AI decisioning uses two different evaluation schedules. The underlying profile for a person is recomputed on a nightly batch. The decision itself is applied in real time at every interaction, using whatever the latest nightly profile indicates. So the continuous part of AI decisioning describes the decision moment, not the refresh rate of the profile.

## Guardrails and rules {#guardrails-rules}

Rules only cover conditions someone explicitly wrote down. When reality falls outside that tree, such as a hybrid persona or a signal combination nobody anticipated, rules do nothing until someone adds a new branch. AI decisioning scores every person continuously and outputs a confidence-based best action instead, so it handles combinations no one explicitly programmed for, and it improves as it sees more outcomes, which a rule never does.

Rules are explainable and instant to auditing, while AI decisioning is confidence-scored rather than deterministic. For that reason, rules remain the better tool when:

* A hard compliance boundary must never be crossed, such as suppressing opted-out contacts.
* There is not enough volume or history for a model to learn from yet.
* Every decision must be fully explainable on demand.

Most mature setups run both together: rules as guardrails, and AI decisioning handling everything in between.

## Benefits {#benefits}

* Less manual journey complexity, with fewer rule branches to maintain.
* More relevant experiences without building hundreds of rules.
* Higher qualification efficiency.
* Faster identification of the next best engagement for each profile.

>[!BEGINSHADEBOX]

**Future scope: account and buying-group context**

Not available today in Marketo Optimizer. AI decisioning is planned to extend beyond the individual profile to:

* Account context — Company and account-level signals as a decisioning input.
* Buying-group signals — Role in deal, decision-maker or practitioner status, and engagement aggregated across everyone involved in a purchase decision.
* Account-level journey orchestration — Routing and content decisions made for the account or buying group as a unit, with journey traffic control coordinating across the multiple people involved.

>[!ENDSHADEBOX]
