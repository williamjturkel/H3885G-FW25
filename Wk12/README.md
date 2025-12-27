# Wk 12. Synthesis and Final Agent Prompting

**Scholarly Primitive: Synthesis** (Integrating all tools). **Goal**: Create the single, complex Master Prompt that generates the final, comprehensive Computational Essay Tool.

# The Challenge of Synthesis

## Combining Logic in a Single Prompt

- **Recap**: A02 required a prompt for extraction. A03 required a prompt for persona injection.
- **The A04 Problem**: The final Master Prompt must request the UI, the A02/A03 unified extraction logic, and the Wk 11 Visualization/Discovery logic all at once, ensuring they don't contradict each other.
- **Mastery of Top-Down**: This assignment is the most comprehensive test of your ability to use natural language as a programming interface.

# Activity 1: A04 Master Prompt Drafting (45 Min)

## Table Activity: The Final Recipe

- **Task**: Individually draft the complete, final **A04 Master Prompt** text, integrating the three required features defined in the assignment slides.
- **Procedure**:
  1. **Define UI & Structure**: Start by requesting a clean, single-file HTML app with three distinct input/output sections (Extraction, Semantic Search, Visualization).
  2. **Feature 1 (Extraction)**: Insert the combined A02/A03 Schema and System Instruction logic for Extraction.
  3. **Feature 2 (Semantic)**: Insert the prompt logic from the Wk 11 Semantic Scorer App for Semantic Search.
  4. **Feature 3 (Visualization)**: Insert the prompt logic for the Wk 11 Clustering Visualization App for the Visualization section.
  5. **Review**: Ensure the prompt explicitly asks for **D3.js** or a similar graphing library, and specifies the use of the **standard Gemini LLM**. Discuss your prompt with people at your table.
- **Goal**: Produce the single, integrated text block that represents the final complexity of your research tool.

# Debrief: Critique of the Master Prompt

## Finding Contradictions

- **Discussion**: Which prompts are too vague? (e.g., "Use a chart to show the data" vs. "Generate a D3.js scatter plot of [X-axis] vs. [Y-axis]").
- **The Contradiction Trap**: Does asking the AI to perform a Semantic Search and _also_ output a strict JSON array (A02 logic) cause a failure? (Often, it does. Synthesis requires finding the precise balance).

# Activity 2: Vibe Coding the Final Agent (45 Min)

## Table Activity: Generating the Synthesized App

- **Task**: Run the finalized Master Prompts to generate the functional A04 Computational Essay Tool.
- **Procedure**:
  1. **Consensus**: Select the single best **A04 Master Prompt** from Activity 1.
  2. **Generate**: Run the prompt in a clean AI Studio session.
  3. **Test**: Run a sample text through all three features (Extraction, Semantic Search, Visualization) in the preview window. Does the app successfully perform **all three tasks** without crashing?
- **Goal**: Prepare to finalize the **A04 Master Prompt Text** with your Assignment team for submission.

# Any questions?
