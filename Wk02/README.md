# Wk 02. Research Agent Persona & Grounding

Defining the computational essay. Introducing **NotebookLM** for synthesis. Using **System Instructions** to establish the AI's role and achieve **Referring** (Source Grounding).

# The Hallucination Trade-Off

## Constraining Creativity for Verifiable Research

- **LLMs are optimized for**: _Fluency, creativity, and plausibility_.
- **Scholarship requires**: _Accuracy, verification, and accountability_.
- **Insight**:  In academic research, you must trade the AI's creative speed for absolute control over its knowledge base.

|**Research Pitfall**|**The Fix**|
|---|---|
|**Hallucination** (Inventing facts)|**Grounding** (Forcing the AI to read your files).|
|**Vague Responses** (Generalities)|**Persona** (Forcing the AI to adopt a specific role).|
|**Uncitable Claims** (No source)|**Referring** (Mandating in-text citations from the source).|

# System Instructions: The Agent Persona

## How to Establish Control

- **Definition**: The **System Instruction** (or Persona) is a block of text at the beginning of a prompt that defines the AI's _permanent identity, goals, and constraints for the entire session_.
- **The Three Core Elements**:
    - **Role**: Who is the agent (e.g., "You are a professional historian...").
    - **Constraint**: What must the agent _always_ do (e.g., "Limit output to 500 words.").
    - **Style/Tone**: How must the agent communicate (e.g., "Use skeptical, academic language.").
 
# Activity 1: Deconstructing System Instructions (20 Min)

## Table Activity: Defining the Critical Persona

- **Task**: As a group, draft the ultimate System Instruction to create a "Skeptical Historical Editor" Persona for NotebookLM.
- **Constraints that MUST be included**:
    - **Citation Mandate**: Must cite the NotebookLM source for every factual claim.
    - **Source Preference**: Must prioritize archival sources over secondary summaries.
    - **Verification**: Must explicitly flag any contradictory evidence found in the corpus.
- **Output**: A single, clean, 1-paragraph system instruction.

# Debrief: System Instruction Quality

## What Makes a Persona Robust?

- **Weak Instruction**: "Be a good historian and write an essay." (Too vague).
- **Strong Instruction**: "**Role**: You are a critical editor. **Constraint**: You must use inline citations (Source Title, page number) for all claims. If a claim cannot be verified in the sources, you must state: `UNVERIFIABLE`. **Tone**: Formal, objective, and analytical." (Actionable).
