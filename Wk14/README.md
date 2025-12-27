# Wk 14. The War Room Analyst: Vibe-Coded Simulation

**Scholarly Primitive: Synthesis** and **Discovery** (in simulation). **Goal**: Use Vibe Coding to generate an immersive, high-stakes historical simulation tool.

# The Final Challenge: Mission Control

## Synthesis Through Simulation

- **The Problem**: Throughout the semester, we focused on _analysis_. Now, we pivot to _prediction_ and _decision-making_.
- **The Task**: We will Vibe Code a "**Mission Control Portal**," a single app that forces the LLM to adopt the persona of a senior military analyst and make a critical decision (e.g., retreat, escalate, negotiate) based on a complex historical scenario.
- **Mastery Test**: The success of the simulation will depend entirely on how well we craft the final, most complex **Master Prompt** of the entire course.

# Activity 1: The War Room Persona (20 Min)

## Table Activity: Drafting the Final Master Prompt

- **Task**: Draft the ultimate Master Prompt that will generate the **Mission Control Portal**.
- **The Persona Injection**: The prompt must include a System Instruction that forces the LLM to adopt a hyper-specific role ("You are the Senior Intelligence Analyst for MACV, January 1968. Your goal is to minimize political casualties and maximize military leverage. Your response MUST be structured as a formal briefing.")
- **The Constraint**: The prompt must include strict, quantified decision rules (“Decisions must be based on a risk score (1-10) and a political viability score (1-10).”)
- **Goal**: Produce the most detailed, high-stakes System Instruction possible.

# Activity 2: Generating the Portal (30 Min)

## Individual Task: Vibe Coding the Simulation App

- **Task**: Use Vibe Coding to generate the **Mission Control Portal** based on the prompt drafted in Activity 1.
- **Procedure**:
  1. **Open Clean Session**: Start a new Vibe Coding session.
  2. **Prompt**: Run your complete **Mission Control Master Prompt**.
  3. **Check**: The generated app should have a text input for the "Scenario" and a structured, formal output area for the "Briefing."
- **Goal**: Create a functional, single-file HTML simulation environment.

# Activity 3: Running the Simulation (50 Min)

## Table Activity: High-Stakes Historical Scenarios

- **Task**: Run three challenging historical scenarios (described below) through the generated Mission Control Portal.
- **Procedure**:
  1. **Paste Scenario**: Paste the first ambiguous scenario into the app's input.
  2. **Analyze Briefing**: Read the AI's final decision and justification (e.g., "RECOMMENDATION: ESCALATE. Risk Score: 7/10."). Use Google Search with AI to fill in the historical context of the scenario.
  3. **Critique (Network Lens)**: Discuss at your table: Did the Analyst Persona focus on Central Actors (like the President) or did it give weight to Edges (relationships between minor players) in its decision?
- **Goal**: Experience the immediate, high-level computational power of the tool you commanded into existence.

### Scenario 1: The Imminent Threat at Khe Sanh

**The Situation**: MACV has received highly credible, but unconfirmed, reports indicating a massive buildup of NVA forces (estimated 20,000-40,000 troops) around the Marine outpost at Khe Sanh near the DMZ. Intelligence suggests this is a deliberate attempt to replicate the siege of Dien Bien Phu. General Westmoreland is committed to defending the base at all costs, viewing it as crucial to blocking NVA infiltration routes. You have conflicting information: some analysts believe this is a genuine offensive; others believe it is a massive diversion intended to draw U.S. troops away from major population centers.

**The Question**: Given the resource strain and political risk of a siege, should MACV divert B-52 assets and the majority of the operational reserve (essential for protecting Saigon and other urban areas) to reinforce Khe Sanh now, or hold them back for potential urban attacks?

### Scenario 2: The Credibility Crisis and Political Viability

**The Situation**: A major American news magazine is about to publish an exposé based on leaked military documents, claiming that the U.S. public has been systematically misled about the strength of the Viet Cong and that the "light at the end of the tunnel" is false. This leak coincides with an upcoming presidential election year and growing domestic dissent. The White House is pressuring MACV to publicly dismiss the report as propaganda, but internal estimates show the magazine's data on Viet Cong troop strength is roughly correct.

**The Question**: Should MACV issue a swift, forceful public denial (minimizing immediate political damage but risking future credibility if the truth emerges), or should you provide a modified, less optimistic update on enemy capabilities (sacrificing political viability now for long-term intelligence accuracy)?

### Scenario 3: The Urban Intelligence Gap

**The Situation**: Throughout late 1967, intelligence has heavily focused on border regions and known enemy bases (like the buildup near Khe Sanh). However, raw, low-level intelligence from provincial sources is now showing an abnormal increase in courier activity and small-scale movement of supplies into four major South Vietnamese cities, including Hue and Saigon. There is no historical precedent for a coordinated, large-scale enemy attack on urban centers. Many analysts dismiss the data as noise, but your gut, based on network analysis of captured communications, suggests the enemy command structure is moving toward something unprecedented.

**The Question**: Should MACV divert scarce Special Forces and conventional surveillance assets away from the established border fronts (where a known threat exists) and into urban areas for counter-intelligence screening, knowing that such a move will leave key rural defenses dangerously thin?

# Any questions?

