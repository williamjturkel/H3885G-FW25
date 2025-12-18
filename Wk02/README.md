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
 
# Activity 1: Defining the Critical Persona (20 Min)

## Table Activity: The Skeptical Historian

