# Wk 02. Research Agent Persona & Grounding

Successful AI research requires more than a simple prompt; it requires a specialized "Master Persona" with deep context and clear operational boundaries. Today we learn to "ground" our agents, ensuring every insight they provide is anchored strictly within the Digital Archives of the Vietnam War. We introduce **NotebookLM** for synthesis, and we use **System Instructions** to establish the AI's role and achieve **Referring** (Source Grounding).

# Website vs. Browser App: What’s the Difference?

While a **website** is like a digital brochure designed for you to _read_ information (like a news site or a blog), a **browser app** is actual software designed for you to _perform_ tasks (like a calculator, Gmail, or a research tool). In this course, we aren't just making webpages to look at; we are using AI Studio to build functional digital assistants that 'live' in your browser and process data for you.

## A Quick Analogy

- **A Website is like a Book**: You open it to find information that is already there. You can flip the pages, but you can’t make the book change its own text.
- **A Browser App is like a Machine**: You give it raw materials (your research files), tell it what to do, and it produces a specific result (like a summary or a data table).

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

- **Task**: As a group, study and customize the Sample Master Prompt for NotebookLM.
- **Questions to Discuss**:
    - **Citation Mandate**: How does it cite sources?
    - **Source Preference**: Does it have particular preferences?
    - **Verification**: Does it explicitly flag any contradictory evidence found in the corpus?
    - **Customization**: Think about how you would edit it to add a "Personal Research Focus." For example, if you are interested in the role of nurses, might add a statement like: "_Prioritize the extraction of medical logistics and gendered experiences within the medical corps._"
- **Output**: A single, clean, 1-paragraph system instruction.

> ### Sample Master Prompt: The Vietnam War Research Intelligence Analyst
>
> **Role**: You are the Historical Research Intelligence Analyst, a specialized AI agent designed to assist a senior historian in working with the digital archives of the Vietnam War. Your primary objective is to facilitate "Top-Down" research by navigating large corpora, identifying patterns, and ensuring all synthesis is strictly grounded in the provided primary and secondary sources.
>
> **Operational Philosophy**:
> - **Scholarly Primitives**: Your workflow is governed by the core activities of historical research: discovering relevant evidence, monitoring changes in narratives, searching across multimodal formats, and comparing disparate accounts of the same event.
> - **Vibe-Coded Precision**: While you communicate in natural, scholarly language, your internal logic must prioritize structured data extraction (names, dates, military units, and locations).
> - **Grounding Above All**: You must never hallucinate. If a fact is not present in the "Digital Archives of the Vietnam War" corpus, you must state that the information is unavailable in the current collection.
>
> **Response Guidelines**:
> 1. **Citations**: Every claim must be followed by a specific citation from the uploaded documents (e.g., "[Document Name, Page X]").
> 2. **Synthesis**: When asked to summarize, do not just condense text; analyze the intent and context of the sources. Compare "official" military reports with "unofficial" personal accounts (letters, oral histories) found in the archives.
> 3. **Structured Output**: When identifying entities or events, default to a structured format (like a bulleted list or a Markdown table) to prepare for future JSON extraction tasks.
> 4. **Epistemic Humility**: Identify gaps in the archive. If a specific perspective (e.g., a specific NLF unit's perspective) is missing from the grounded data, flag this as a "silence in the archive" for the researcher to investigate.
> 
> **Interaction Style**: Maintain a collaborative, intellectually curious, and professional tone. You are an expert peer, not just a search engine. When a student provides a document, your first step is to "read" it through the lens of a 1960s-70s geopolitical context.

# Debrief: System Instruction Quality

## What Makes a Persona Robust?

- **Weak Instruction**: "Be a good historian and write an essay." (Too vague).
- **Strong Instruction**: "**Role**: You are a critical editor. **Constraint**: You must use inline citations (Source Title, page number) for all claims. If a claim cannot be verified in the sources, you must state: `UNVERIFIABLE`. **Tone**: Formal, objective, and analytical." (Actionable).

# Activity 2: Grounding and Synthesis (25 Min)

## Individual Task: Testing Persona Application

- **Task**: Students practice using NotebookLM to work on synthesis briefing.
- **Procedure**:
    1. **Apply Persona**: In a new NotebookLM notebook, click "Configure Notebook" and then paste the edited **Sample Master Prompt** (from Activity 1) into the "Custom" window and save it.
    2. **Load Sources**: Load these two sources from the [Pentagon Papers](https://www.archives.gov/research/pentagon-papers) into the notebook (you can copy the URLs from the links and use those rather than downloading and uploading PDFs)
       - [Part V. A. Justification of the War. Public Statements. Volume I: C--The Kennedy Administration](https://nara-media-001.s3.amazonaws.com/arcmedia/research/pentagon-papers/Pentagon-Papers-Part-V-A-Vol-IC.pdf)
       - [Part V. B. 4. Justification of the War. Internal Documents. The Kennedy Administration. Book I](https://nara-media-001.s3.amazonaws.com/arcmedia/research/pentagon-papers/Pentagon-Papers-Part-V-B-4-Book-I.pdf)
    4. **Test**: Try asking "_Based on the grounding you have, what are the three most significant contradictions in these accounts?_" Save a copy of its response so you can refer to it later if you need to.
    5. **Formulate Question**: Try to formulate a complex research question that requires synthesis across multiple sources in the corpus.
    6. **Generate & Finalize**: Run the query. Refine the query until you achieve a high-quality, fully cited output (approx. 750 words).
    7. **Share with Team**: Upload your final query and the NotebookLM output to the Google Chat space for your team. As a group your team is going to have to create a **Briefing Document** to submit, and this activity gives individual team members a chance to work on the problem.

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
- **Objective**: Ensure your three personas are distinct and methodologically sound.
- **Procedure**:
  - **Select Thesis**: Formulate one **complex research question** for the corpus (this is your own thesis, not your teams, that you will test).
  - **Design Personas**: Individually design the full System Instruction for two Personas in addition to the Skeptical Historian. These should match the kind of person who might find something of interest in your corpus. If you have a corpus that relates to policy, then Policy Analyst might be a good choice. If your corpus relates to music lyrics then Countercultural Critic or Musicologist might be better choices.
  - **Peer Review**: Exchange the written persona instructions with your tablemates. Critique each other's designs for ambiguity or lack of constraint.

# Assignment 01

Assignment 01 is listed on OWL as due today (to keep you on track). You have a week to submit it.

# Any questions?
