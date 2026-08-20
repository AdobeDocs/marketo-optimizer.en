---
title: Next Best Path Node
description: Use the Next best path node in Marketo Optimizer for AI-driven journey routing with natural language prompts, path simulation, confidence scores, and live split path results.
---
# Next best path node

In Marketo Optimizer, the *Next best path* node brings AI-driven split path decisioning directly into the journey canvas. Instead of configuring filter conditions on a [split paths](./split-merge-paths-nodes.md) node, you describe your intent in natural language and let the system determine the most relevant path for each person.

In B2B buying, a profile may appear to be one type of buyer, but their behavior, firmographic data, and engagement context reveal a more nuanced story. The next best path node evaluates that context to make an intelligent routing decision, while letting you review, modify, or override any AI recommendation before activating the journey.

## Path decisioning {#path-decisioning}

There are three steps to go from intent to activation.

* **Step 1: Define paths** — Add a Next Best Path node into your journey, name each path, and write a natural language prompt describing who should progress down the path. You can add or remove paths at any time.

* **Step 2: Simulate** — Pick a sample audience and run a simulation. You see profile counts per path, confidence scores, and the AI reasoning so that you can validate the logic before activating.

   >[!NOTE]
   >
   >Simulation runs only against sample data and never affects live journey execution.

* **Step 3: Activate** — Publish the journey against your real audience. The AI evaluates each person at runtime, assigns the best-fit path in real time, and a default fallback ensures that no one hits a dead end.

### AI decisioning inputs {#ai-decisioning-inputs}

When a person reaches the node, the system fetches profile context, applies constraints, and uses an LLM to select the best-fit path. The AI evaluates each person using a combination of the following inputs:

* **Engagement history** – Email opens, link clicks, web page visits, and other behavioral signals from the current and prior journeys
* **Real-time signals** – High-intent events such as form fills and pricing page visits
* **Profile attributes** – Demographics, job title, persona, and firmographic data
* **Account attributes** – Firmographic and technographic data associated with the person's account

### AI context building {#ai-context-building}

Underlying the routing decision, the AI constructs an inferred layer for each profile. It combines demographic and firmographic data, account details, and behavioral signals (such as persona details, problem intent, and product intent) into a contextual summary for that person. Using this enriched context, the AI can route each person to the optimal path and provide both a confidence score and the natural-language reasoning behind each decision.

Each decision is logged with a confidence score and natural-language reasoning for transparency and observability.

If no path is a strong match, or if the prompt references data not available for a profile, the person is routed to the default fallback path.

## Add a next best path node {#add-node}

1. Open the person journey and navigate to the journey canvas.

1. Click the plus ( **+** ) icon on a path and choose **Next best path**.

   The node is added to the canvas and the AI split configuration panel opens on the right. It starts with one path and a default *Other people* path to route people who do not qualify for any of the defined paths.

## Configure paths {#configure-paths}

For each path, define a name and a natural language prompt that describes who should be routed there. Prompt input replaces the filter condition UI entirely; there are no attribute conditions to configure.

1. Click **Add path** for each additional path you want to include.

   To remove a path, click the *Delete* icon on the path card.

1. For each path card in the right panel:

   * Enter a **Label** that reflects the audience or intent for that segment.

   * Enter a **Prompt** in natural language describing who belongs on this path. Focus on intent and outcome, not specific attribute values.

     **Example prompts for a three-path split:**

     * *Path 1 – HR Leaders:* Identify people in HR leadership roles most likely to engage with talent management and employee experience content.
     * *Path 2 – Technical Evaluators:* Identify technical stakeholders most likely to engage with product architecture, integrations, and implementation content.
     * *Path 3 – Business Decision-Makers:* Identify business stakeholders most likely to engage with ROI, business outcomes, and case study content.

1. If needed, reorder paths to set the priority order for matching.

   Path filtering is evaluated in top-down order. Each person proceeds along the first path that matches. Click the up and down arrows at the top right of each path card to move it higher or lower in the list.

1. Review the default path (last in the path list) and change the label if needed.

   The default path is used when the AI cannot confidently assign a person to any defined path or when the relevant data is unavailable. When a prompt references data that does not exist in the dataset for a given profile, the system routes that profile to the default path and flags the data gap.

>[!BEGINSHADEBOX]

**Human-in-the-loop controls**

AI recommendations are non-binding. Before activating the journey, you can:

* Edit any path prompt to refine the routing logic.
* Add, remove, or reorder paths.
* Override AI suggestions with custom conditions as needed.

AI-driven path assignments do not take effect until you publish the journey.

>[!ENDSHADEBOX]

## Prompt examples by use case {#prompt-examples}

The following examples show how to write effective path prompts across common B2B marketing use cases. Use them as starting points and adapt the language to match your journey context and audience data.

*  "Identify people who have engagement on HR sites (shrm.org, hbr.org/topic/human-resource-management), interested in Journey Optimizer over the last 30 days, who are likely to attend a webinar on AI in HR Operations. They should have also shown someinterest in AI products."

* Identify people who have engagement on Finance sites (wsj.com/finance,investopedia.com), interested in Marketo over the last 30 days, who are likely to attenda webinar on AI in Financial Planning. They should have also shown some interest in AI products."

* "Identify people who have engagement on Risk/Research sites(mckinsey.com/capabilities/risk-and-resilience, forrester.com/research), interested in GenStudio over the last 30 days, who are likely to attend a webinar on AI in RiskManagement. They should have also shown some interest in AI products."

## Simulate decisioning before publishing {#simulate}

Use simulation to test how the AI evaluates your prompts against a real audience before the journey goes live. Simulation is available only while the journey is in *Draft* status and has no effect on any published journey.

### Run a simulation {#run-simulation}

1. Select the next best path node and click the *Simulate* icon at the top of the right panel.

1. In the dialog, choose the audience to use for the simulation:

   * **[!UICONTROL Original person lists]** – Use the audience from the audience node. Specify a sample size when the full audience exceeds the simulation threshold.
   * **[!UICONTROL Dynamic and static lists]** – Use a Marketo Engage static or dynamic list.
   * **[!UICONTROL Test records]** – Use AI-suggested test profiles.

   >[!NOTE]
   >
   >* If the selected audience exceeds the simulation threshold, the system runs the simulation on a 100-profile sample. An indicator in the UI shows that results are sample-based.
   >* If the selected audience is not yet materialized, simulation is blocked. An inline warning directs you to materialize the audience first.

1. Click **[!UICONTROL Simulate]**.

### Review simulation results {#review-results}

After the simulation runs, the right panel displays the distribution of profiles across each path and the AI reasoning behind those assignments:

| Result | Description |
|---|---|
| **Profiles** | The number of profiles routed to the path. |
| **Split** | The percentage of profiles routed to the path. |
| **Confidence** | The AI confidence level for the path assignment. Confidence reflects data freshness, signal strength and consistency, and the historical success of similar routing patterns. |
| **Prompt** | The prompt that was evaluated for the path. |
| **AI reasoning** | A natural-language explanation of why profiles were collectively assigned to this path. |

>[!NOTE]
>
>When available data or scope limits a decision, the results include information about the limitation. For example, when a required attribute is not present in the dataset, the results include an explicit indicator explaining how the missing data impacted the results.

Use the results to refine prompts and confirm that the routing reflects your intended outcome. You can modify path prompts and re-run the simulation as many times as needed before publishing.

## Publish and monitor the journey {#publish-monitor}

After validating the simulation results:

1. Connect the people audience to the journey entry node.

2. [Publish the journey](./journeys-overview.md).

After the journey is live, the next best path node runs at execution time. As each person reaches the node, the AI evaluates them in real time using the latest signals and routes them to the most relevant path.

For a published journey, open the journey canvas and select the next best path node to view the **_[!UICONTROL Live results]_** section in the right panel. Live results show:

* The percentage distribution of profiles across each path
* The confidence score for each path assignment
* Path-level and profile-level reasoning, with expandable detail for individual profiles

Live results are also available in the Journey Console and through the Journey Observability skill in the AI Hub.