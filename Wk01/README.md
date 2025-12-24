# Wk 01. The Top-Down Philosophy, Scholarly Primitives & Gemini Ecosystem

Introduction to Large Language Models (LLMs). The shift from bottom-up programming to top-down, natural language control. **Goal**: Setup & Conceptual Grounding.

# Unsworth's Scholarly Primitives

John Unsworth’s [“Scholarly Primitives”](https://people.brandeis.edu/~unsworth/Kings.5-00/primitives.html) (2000) are a set of fundamental actions common to humanities research across all eras and media. These primitives form the conceptual backbone of advanced digital research. In this course they are used to define the basic functions that our computational tools should enable. The key primitives include:
- **Discovering**: The act of locating relevant materials and information, which in a digital context moves beyond simple keyword search to advanced methods like semantic searching.
- **Representing**: The necessary step of converting sources into a computational structure (like structured data, graphs, or maps) so they can be processed and analyzed by tools.
- **Comparing**: The systematic analysis of two or more entities—texts, images, or data sets—based on defined criteria to identify similarities, differences, and patterns.
- **Annotating**: The process of attaching descriptive, contextual, or interpretive metadata to a source, allowing human judgment to be applied consistently at scale.
- **Referring**: The foundational requirement to link every piece of knowledge back to its source, ensuring traceability and verification (or “grounding”) in research.
- **Sampling**: The methodological process of selecting and acquiring a subset of data from a larger archive based on specific, defensible criteria.
- **Illustrating**: The final step of turning research findings into a persuasive visual form, such as a chart, graph, or network map, to aid analysis and communication.

# From Bottom-Up Coding to Top-Down Control

## The Methodological Shift

The old approach focused on syntax. The new approach focuses on design.

|   |   |
|---|---|
|**Bottom-Up (Traditional DH)**|**Top-Down (Generative AI)**|
|**Tool**: Python, Javascript, R|**Tool**: Gemini, NotebookLM, Vibe Coding|
|1. Learn a Programming Language.|1. **Define the Goal** (e.g., "Extract JSON").|
|2. Manually write every line of code.|2. **AI generates** the custom web app/script.|
|3. Debug syntax errors.|3. **Critique** the AI's methodology/output.|
|**Focus**: _How_ to make the code run.|**Focus**: _Why_ the code should run that way.|

When you come across unfamiliar terms, ask me or Google them.

# The Gemini Research Ecosystem

## Core Environments for developing the Computational Essay

- **NotebookLM (Supports Research)**:
  - **Function: Grounding and Synthesis**. Individuals and teams upload private corpora (corpus: collection of documents; corpora is plural)
  - **Scholarly Primitive: Referring** (Source Grounding). NotebookLM draws on and cites your sources rather than using LLM's general knowledge    
- **Google AI Studio / Vibe Coding (Supports Prototyping)**:
    - **Function: Tool Building**. We use natural language prompts to generate custom web apps and utility scripts (Extractors, Visualizations, etc.)
    - **Critical Mandate: All custom apps must be generated as a single, standalone HTML file using inline JavaScript/CSS only.**
    - **Scholarly Primitive: Sampling, Representing**.
- Google Workspace (Supports Teamwork and Creation of Scholarly Products):
    - **Function: Collaboration and Output**. Google Docs, Slides (via Gemini Canvas), Sheets, Chat and Meet.

To use all of the course tools, you are going to need a Gmail account if you do not already have one. **Please email me your Gmail address right now if you haven't already**__.

# Activity 1: Generating Code-Free Prototypes (30 Min)

## Table Activity: Vibe Coding

Table activities give you a chance to work with one or two other people and figure things out together.

- **Task**: Use Vibe Coding to generate a functional web app without typing code.
- **Instructions**:
    1. Go to [Google AI Studio](https://aistudio.google.com) and navigate to the Vibe Coding / Build mode.
    2. With the other students at your table, agree on a research tool to build (there are a list of options below).
    3. Type your full request into the prompt window.
    4. Run the generation and see the code appear.
    5. Try running your app and testing it with the suggested source.
    6. If you have time, try some of the other prompts.
- **Sample Research Tool Prompts**:
  - Create a tool that summarizes a document, **extracts** three key entities and formats them as a bulleted list
    - Test with: [National Vietnam War Veterans Day](https://www.nixonlibrary.gov/news/national-vietnam-war-veterans-day) from the Nixon Presidential Library
  - Build a simple web tool that accepts two quotes and returns the **semantic distance** between them as a percentage.
    - Test with these quotes from the National Vietnam War Veterans Day post, trying them in pairs (a vs. b, a vs. c, b vs. c):
      1. "Some protesters, who had clamored for the troops’ return, now gathered at airports to meet the soldiers with angry slogans. Many service members were even encouraged to change out of their uniforms before they landed to avoid being confronted by the protesters."
      2. "Almost as bad as the abuse by the few was the indifference of the many. War-weary civilians didn’t want to talk about Vietnam anymore; they wanted it to disappear..."
      3. "President Harry S. Truman sent a small number of military advisors; President Dwight D. Eisenhower sent money and equipment; President John F. Kennedy sent 16,000 American troops as advisors."
  - Generate a single-file app with two text boxes and a button to compare the **sentiment (positive/negative)** of the text in box A versus box B.
    - Test with these quotes from the National Vietnam War Veterans Day post:
      1. "Officially designated in 2017, National Vietnam Veterans Day has its origins with President Nixon’s February 26, 1974, proclamation stating that “Friday, March 29, 1974, shall be a day of commemoration…” as well as “urging all citizens of every age to participate in the events of this day as one means of honoring those men and women who served their country faithfully and courageously during the Vietnam conflict.”"
      2. "U.S. public opinion supporting involvement was generally positive in the beginning. However, with the increasing death toll and no clear end of the war in sight, much of the public’s view of the war had become increasingly unfavorable, resulting in considerable unrest at home. In 1968, the Republican candidate for president, Richard Nixon, ran heavily on a campaign pledge of getting the country out of Vietnam." 
  - Create an HTML app that takes an essay as input and **outputs a JSON schema** detailing the argument's main premise, evidence, and conclusion.
    - Test with: [National Vietnam War Veterans Day](https://www.nixonlibrary.gov/news/national-vietnam-war-veterans-day) from the Nixon Presidential Library
   
# Debrief: Code from Natural Language

## The Vibe Coding Revelation

- **Observation**: You just generated a fully functional program using only natural language.
- **Insight**: Your natural language instruction (the prompt) is the new programming interface.
- **The Scholarly Challenge**: General, conversational language produces unpredictable results. To control our agent with scholarly rigor, we must define the rules using **System Instructions**—our focus next week.

# Grounding: The Methodological Imperative

## Why We MUST Control the AI's Knowledge

- **The Problem**: Unconstrained LLMs tend to "hallucinate" (invent facts, sources, or details). This is fatal to academic research. 
- **Solution: Grounding**: We force the AI to use only the specific knowledge we provide (e.g., a document corpus) rather than its vast, general training data.
- **Scholarly Primitive: Referring**: Grounding is the technical mechanism for guaranteeing traceability and citation.

> _User Query + General LLM &rarr; Answer (No Source)_<br/>
> _User Query + NotebookLM (Grounded) &rarr; Answer + Source Citation (Referring is Achieved)_

# Activity 2: Testing Generality vs. Specificity (30 Min)

## Table Activity: Compare Unguided vs. Grounded Answers

- **Objective**: Visually demonstrate the value of grounding.
- **Step 1 (Unguided)**: Ask the **general Gemini interface** a complex question related to the Vietnam War: "What was the role of the press in the Tet Offensive?"
- **Step 2 (Grounded)**: 
  - Open [NotebookLM](https://notebooklm.google.com/)
  - Create a new notebook and upload the following source Clarence R. Wyatt, ["The American Press in Vietnam"](https://journals.lib.unb.ca/index.php/JCS/article/download/14854/15923/19642) _Conflict Quarterly_ (1989).
  - Ask the same question to your NotebookLM interface, which is grounded on this single PDF source.
- **Goal**: Note and discuss the differences in tone, detail, and citation.

# Debrief: The Hallucination Problem

## The Human as the Final Verifier

- **Key Outcome**: The **Grounded** response should be more conservative, more specific, and always point directly back to the source document.
- **Core Takeaway**: You must become the **curator, verifier, and guarantor** of the AI's output. The AI is a powerful assistant, not a truth machine.
- **Next Step**: We use **System Instructions** next week to formally define the agent's role (e.g., "You are a skeptical historical editor who must cite every fact.") to prevent hallucination.

# Assignment 01 Overview

- [Assignment Page](<../A01>)

# Any questions?
