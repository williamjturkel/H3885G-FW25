# Wk 08. Deep Synthesis and Knowledge Generation (Workspace Integration)

Following the break, we integrate our findings into a unified workspace to begin the process of deep synthesis. We will explore how AI can help us generate new historical knowledge by identifying patterns across our entire Vietnam War corpus. **Scholarly Primitive: Annotating** (Creating specialized, reusable descriptive markup). We learn how to define and embed persistent **System Instructions** and **Schemas** to force the AI to perform specialized research tasks.

# Review: The Value of Annotation

## Unsworth's Primitive: Annotating

- **Definition**: Annotation is the process of attaching descriptive, interpretive, or contextual information to a source.
- **Traditional Annotation**: Slow, subjective, difficult to scale (e.g., highlighting, margin notes).
- **Computational Annotation**: Fast, consistent, and scalable. It allows us to apply a _controlled vocabulary_ (like a tag, a score, or an entity ID) across thousands of sources instantly.
- **Goal for A03**: We want an AI to apply consistent, specialized tags to our Vietnam War sources, beyond what our simple A02 extractor could do.

# Introducing Custom Agents (Personas)

## Specialized Tools for Specialized Tasks

- **Gems**: Paid Gemini accounts have an interface that allows you to create "Gems." Each gem is a persistent, pre-programmed version of Gemini. You give it a specific name, a persona (System Instruction), and a rule set once. Then you call it by name whenever you need it, instead of rewriting a complex prompt.
- **What is a Custom Annotation Persona?** It is a persistent set of rules (System Instruction and Schema) that we send to the standard LLM with every request. It allows us to create something that works like a Gem without requiring a paid subscription.
- **Mechanism**: The Vibe-Coded app includes the System Instruction and JSON Schema in the API payload, making the standard model behave like a specialist _only for that request_.
- **Top-Down Advantage**: Instead of re-writing a complex prompt every time, the Vibe-Coded app embeds the **Annotation Logic** for you.

> _App &rarr; API Call (Payload includes System Instruction + Schema) &rarr; Standard LLM &rarr; Specialist Output_.

# Activity 1: Defining the Annotation Rules (30 Min)

## Table Activity: Creating the Custom Annotation Schema

- Task: The new A03 teams must define the **three new properties** they will use to computationally annotate the existing A02 JSON dataset. You and your team will settle on these properties outside of class, but this activity gives you a chance to get started on the problem and discuss with people at your table.

- **Procedure** (In-Class Table):
  1. **Analyze A02 Data**: Review a sample of the structured data (JSON) created for A02. (These files are available in the Class Data Pool.) What's missing?
  2. **Define Rules**: Create rules for three new, qualitative, but quantifiable annotations relevant to the Vietnam War domain (e.g., `Propaganda_Intensity_Score (1-10)`, `Primary_Conflict_Actor`, `Source_Bias_Classification`).
  3. **Draft System Instruction**: Individually draft the _exact_ instruction the **Custom Annotation Persona** will need: "You are the specialist [Persona Name]. Your sole task is to analyze text input and output the three following fields: [Property 1], [Property 2], [Property 3]. Base your output only on the provided text."
- **Deliverable (Individual)**: The final 3-property Annotation Schema and the Persona's complete System Instruction draft.

# Debrief: Generalist vs. Specialist AI

## Why Agents are Essential for Research

- **Generalist AI**: Good for brainstorming, poor for repeatable research. Tends to drift out of persona.
- **Specialist Agent (Persona)**: Focused on one task, maintains a consistent persona, and is ideal for applying **uniform annotation** across a large dataset. (You can also use a Gem for the same purpose).
- **Consistency Test**: If the same text is run through the "Rhetoric Analyst Persona" (via the API payload) repeatedly, the annotation output should be nearly identical. This is crucial for scholarly validity.

# Activity 2: Vibe Coding a Persona Validator (30 Min)

## Individual Task: Prototyping the Logic with an App

- **Task**: Use Vibe Coding to generate a **Simple Validator App** (Single-File HTML) to test if your System Instruction works _before_ you try to build the main Portal. (The **Portal** is the new Vibe-Coded web interface that will run your specialized Annotation Persona logic.)
- **Procedure**:
  1. **Open New Session**: Start a new Vibe Coding session in AI Studio.
  2. **Prompt for App**: "Generate a **single-file HTML app** that acts as a test harness. It must have a text input and a button. When clicked, it must call the Gemini API, **injecting the following System Instruction and Schema into the payload**, and display the resulting JSON." (Paste your draft from Activity 1 into the prompt).
  3. **Test**: Run the generated app in the preview window. Paste a sample text. Does the AI follow your rules?
- **Goal**: Verify that your **logic** (Persona + Schema) works by creating a throwaway app. If it fails here, it will fail in the main portal.

# Activity 3: The A03 Master Prompt Blueprint (30 Min)

## Table Activity: Creating the Regeneration Prompt

- **Task**: Draft the **complete A03 Master Prompt** that the A03 team will use to **regenerate** the A03 Annotation Portal. Again, you will do this with your A03 team but this gives you a chance to get started and discuss with people at your table.
- **Context**: You have the finalized **A02 Master Prompt Text** (from previous weeks) and a working Annotation Logic (Activity 2). You need to merge them. All A02 Master Prompt Text files are available in the Class Data Pool.
- **Procedure**:
  1. **Start with A02 Text**: Take the finalized **A02 Master Prompt Text** (the one that generated the UI) as your starting document.
  2. **Merge and Replace**: Edit the A02 prompt text to:
     - **Keep the UI identical**.
     - **Delete the old A02 JSON Schema**.
     - **Inject the new A03 System Instruction and Schema**.
  3. **Final A03 Master Prompt**: This resulting document is the **single technical specification** for the A03 Annotation Portal.
  4. **Review**: Peer review this prompt. Is it specific enough?
- **Goal**: We do not write code to update the app; we create a new, refined **Master Prompt** to force the AI to regenerate the entire app with the new logic.

# Assignment 03 Overview

[Assignment Page](<../A03>)

# Any questions?
