# Wk 08. Deep Synthesis and Knowledge Generation (Workspace Integration)

# !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

Computable Knowledge and Custom Personas. **Scholarly Primitive: Annotating** (Creating specialized, reusable descriptive markup). **Goal**: Learn how to define and embed persistent **System Instructions** and **Schemas** to force the AI to perform specialized research tasks.

# Review: The Value of Annotation

## Unsworth's Primitive: Annotating

- **Definition**: Annotation is the process of attaching descriptive, interpretive, or contextual information to a source.
- **Traditional Annotation**: Slow, subjective, difficult to scale (e.g., highlighting, margin notes).
- **Computational Annotation**: Fast, consistent, and scalable. It allows us to apply a _controlled vocabulary_ (like a tag, a score, or an entity ID) across thousands of sources instantly.
- **Goal for A03**: We want an AI to apply consistent, specialized tags to our Vietnam War sources, beyond what our simple A02 extractor could do.

# Introducing Custom Agents (Personas)

## Specialized Tools for Specialized Tasks

- **Gems**: Paid Gemini accounts have an interface that allows you to create "Gems." These are a persistent, pre-programmed version of Gemini. You give it a specific name, a persona (System Instruction), and a rule set once. Then you call it by name whenever you need it, instead of rewriting a complex prompt.
- **What is a Custom Annotation Persona?** It is a persistent set of rules (System Instruction and Schema) that we send to the standard LLM with every request. It allows us to create something that works like a Gem without requiring a paid subscription.
- **Mechanism**: The Vibe-Coded app includes the System Instruction and JSON Schema in the API payload, making the standard model behave like a specialist _only for that request_.
- **Top-Down Advantage**: Instead of re-writing a complex prompt every time, the Vibe-Coded app embeds the **Annotation Logic** for you.

> _App &rarr; API Call (Payload includes System Instruction + Schema) &rarr; Standard LLM &rarr; Specialist Output_.

# Activity 1: Defining the Annotation Rules (30 Min)

## Table Activity: Creating the Custom Annotation Schema

- Task: The new A03 teams must define the **three new properties** they will use to computationally annotate the existing A02 JSON dataset. You and your team will settle on these properties outside of class, but this activity gives you a chance to get started on the problem and discuss with people at your table.

- **Procedure** (In-Class Table):
  1. **Analyze A02 Data**: Review a sample of the structured data (JSON) created for A02. What's missing?
  2. **Define Rules**: Create rules for three new, qualitative, but quantifiable annotations relevant to the Vietnam War domain (e.g., `Propaganda_Intensity_Score (1-10)`, `Primary_Conflict_Actor`, `Source_Bias_Classification`).
  3. **Draft System Instruction**: Individually draft the exact instruction the Gem will need: "You are the specialist [Persona Name]. Your sole task is to analyze text input and output the three following fields: [Property 1], [Property 2], [Property 3]. Base your output only on the provided text."
- **Deliverable (Individual)**: The final 3-property Annotation Schema and the Persona's complete System Instruction draft.

# Debrief: Generalist vs. Specialist AI

## Why Agents are Essential for Research

- **Generalist AI**: Good for brainstorming, poor for repeatable research. Tends to drift out of persona.
- **Specialist Agent (Persona)**: Focused on one task, maintains a consistent persona, and is ideal for applying **uniform annotation** across a large dataset. (You can also use a Gem for the same purpose).
- **Consistency Test**: If the same text is run through the "Rhetoric Analyst Persona" (via the API payload) repeatedly, the annotation output should be nearly identical. This is crucial for scientific validity.

# Activity 2: Vibe Coding the API Payload Logic (35 Min)

## Individual Task: Generating the Call Logic

- **Task**: Use Vibe Coding to generate the **new JavaScript function** that includes the System Instruction and Schema in the API request body.
- **Procedure**:

Define the Change: Explain to Vibe Coding that you are replacing the previous logic: "Generate a JavaScript function called callCustomAnnotator(textInput, systemInstruction, schema) that calls the standard Gemini LLM (gemini-2.5-flash) but sends the systemInstruction and schema within the API payload. The function must return the JSON result."

Generate Replacement: Vibe Coding will produce a complete, self-contained function.

Key Difference: The function now requires passing the System Instruction text and the JSON Schema as variables, embedding them into the request body.

Key Concept: We replace the entire original A02 API logic with a new, Vibe-Coded logic block that carries the persona and rules in its baggage.
