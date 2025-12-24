# Wk 08. Deep Synthesis and Knowledge Generation (Workspace Integration)

Computable Knowledge and Custom Agents. **Scholarly Primitive: Annotating** (Creating specialized, reusable descriptive markup). **Goal**: Learn how to create and manage persistent, customized AI agents for specific, repeatable research tasks.

# Review: The Value of Annotation

## Unsworth's Primitive: Annotating

- **Definition**: Annotation is the process of attaching descriptive, interpretive, or contextual information to a source.
- **Traditional Annotation**: Slow, subjective, difficult to scale (e.g., highlighting, margin notes).
- **Computational Annotation**: Fast, consistent, and scalable. It allows us to apply a _controlled vocabulary_ (like a tag, a score, or an entity ID) across thousands of sources instantly.
- **Goal for A03**: We want an AI to apply consistent, specialized tags to our Vietnam War sources, beyond what our simple A02 extractor could do.

# Introducing Custom Agents (Gems)

## Specialized Tools for Specialized Tasks

- **What is a Custom Agent (Gem)?** A persistent, pre-programmed version of Gemini. You give it a specific name, a persona (System Instruction), and a rule set once.
- **Top-Down Advantage**: Instead of re-writing a complex prompt every time ("Act as a historian who specializes in military rhetoric and output a score..."), you just call the "Rhetoric Analyst Gem."
- **Use Case: Annotation**: We can build a Gem that specifically knows your JSON schema and applies a new layer of data (e.g., sentiment, rhetorical device, author intent) to your existing structured data.

# Activity 1: Defining the Annotation Rules (30 Min)

## Table Activity: Creating the Custom Annotation Schema

- Task: The new A03 teams must define the **three new properties** they will use to computationally annotate the existing A02 JSON dataset. You and your team will settle on these properties outside of class, but this activity gives you a chance to get started on the problem and discuss with people at your table.

- **Procedure** (In-Class Table):
  1. **Analyze A02 Data**: Review a sample of the structured data (JSON) created for A02. What's missing?
  2. **Define Rules**: Create rules for three new, qualitative, but quantifiable annotations relevant to the Vietnam War domain (e.g., `Propaganda_Intensity_Score (1-10)`, `Primary_Conflict_Actor`, `Source_Bias_Classification`).
  3. **Draft System Instruction**: Individually draft the exact instruction the Gem will need: "You are the [Gem Name]. Your sole task is to analyze text input and output the three following fields: [Property 1], [Property 2], [Property 3]. Base your output only on the provided text."
- **Deliverable (Individual)**: The final 3-property Annotation Schema and the Gem's complete System Instruction draft.

# SLIDE 5: Debrief: Generalist vs. Specialist AI

## Why Agents are Essential for Research

- **Generalist AI**: Good for brainstorming, poor for repeatable research. Tends to drift out of persona.
- **Specialist Agent (Gem)**: Focused on one task, maintains a consistent persona, and is ideal for applying **uniform annotation** across a large dataset.
- **Consistency Test**: If the same text is run through the "Rhetoric Analyst Gem" repeatedly, the annotation output should be nearly identical. This is crucial for scientific validity.

