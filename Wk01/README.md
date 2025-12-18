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

# The Gemini Research Ecosystem

## Core Environments for developing the Computational Essay

- **NotebookLM (Supports Research)**:
  - **Function: Grounding and Synthesis**. Individuals and teams upload private corpora (corpus: collection of documents; corpora is plural)
  - **Scholarly Primitive: Referring** (Source Grounding). NotebookLM draws on and cites your sources rather than using LLM's general knowledge    
- **Google AI Studio / Vibe Coding (Supports Prototyping)**:
    - **Function: Tool Building**. We use natural language prompts to generate custom web apps and utility scripts (Extractors, Visualizations, etc.)
    - **Scholarly Primitive: Sampling, Representing**.
- Google Workspace (Supports Teamwork and Creation of Scholarly Products):
    - **Function: Collaboration and Output**. Google Docs, Slides (via Gemini Canvas), Sheets, Chat and Meet.
