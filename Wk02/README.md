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

# Activity 2: Grounding and Synthesis (25 Min)

## Individual Task: Testing Persona Application

- **Task**: Students use their team's NotebookLM notebook to work on synthesis briefing.
- **Pre-Requisite**: Team corpus must be available in Files section of Google Chat space, and NotebookLM notebook created and shared.
- **Procedure**:
    1. **Apply Persona**: Input the refined **Skeptical Historian Persona** (from Activity 1) as the first part of your prompt.
    2. **Formulate Question**: Try to formulate a complex research question that requires synthesis across multiple sources in the corpus.
    3. **Generate & Finalize**: Run the query. Refine the query until you achieve a high-quality, fully cited output (approx. 750 words).
    4. **Share with Team**: Upload your final query and the NotebookLM output to the Google Chat space for your team. As a group your team is going to have to create a **Briefing Document** to submit, and this activity gives individual team members a chance to work on the problem.

# Debrief: The Referring Primitive

## Critique Your Synthesized Briefing

- **Core Question**: Did the AI meet the **Referring** requirement?
- **Checklist**:
      - Are the claims directly supported by the source snippets provided by NotebookLM?
      - Are there citations for every major claim?
      - Could a reader trace every sentence back to your original corpus documents?
- **Methodological Check**: If the AI failed to cite, your **System Instruction (Persona)** was not strong enough. This reinforces the need for rigorous constraint.

# Activity 3: Designing Three Personas (25 Min)

## Table Activity: Preparing for the Individual Critique

- **Task**: Prepare material needed for your Individual Portion of [Assignment 01](<../A01>).

Objective: Ensure your three personas are distinct and methodologically sound.

Procedure:

Select Thesis: Formulate one complex research question for the corpus (this is the thesis you will test).

Design Personas: Individually design the full System Instruction for the two remaining Personas (e.g., "Enthusiastic Journalist," and "Policy Analyst").

Peer Review: Exchange the written persona instructions with your tablemates. Critique each other's designs for ambiguity or lack of constraint.
