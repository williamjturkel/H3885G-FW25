# Assignment 03: Annotation Agent

## Assignment 03 Overview

### The Challenge: Quantifying the Qualitative

- **Problem**: Research requires subjective judgments (bias, tone, rhetorical intensity). How do we make subjective judgment scalable and verifiable?
- **Solution**: **The Custom Annotation Persona**: We will build a specialized **System Instruction** and **JSON Schema** and embed them in a Vibe-Coded app to apply consistent, complex annotations across your sources.
- **Goal**: Create a **Vibe-Coded Annotation Portal** that forces the standard LLM to behave like a specialist, consistent annotator.

## The Annotation Portal (Week 09. Feb 26-Mar 4)

After our Feb 26 meeting your **team** has to do the following

- **Choose a team leader**. This person will be responsible for submitting the team portion of the assignment to OWL.
- **Task**: Create a **Custom Annotation Persona** (System Instruction + Schema) and a **Vibe-Coded HTML Portal** that can process raw text from any **A01 Sub-Corpus** and output **THREE complex, research-relevant annotation fields**.
- **Methodology**: The final Portal App must be created by **regenerating the app from scratch** using a single **A03 Master Prompt**. This prompt must request the same user interface as the A02 Extractor but embed the **A03 Annotation Persona logic** (System Instruction and Schema) into the API call.
- **The Three Annotation Fields MUST**:
  1. Be **qualitative** but **quantifiable** (e.g., a score from 1-10, or a classification category).
  2. Be designed to expose a new analytical insight (e.g., _emotional distance in reporting_).

## Coding as Conversation Reflection (Week 10. Mar 5-Mar 12)

After our Mar 5 meeting **each individual student** has to do the following

- **Task**: Write a focused reflection on the methodological experience of **'Coding as Conversation'** (Week 09).
- **Focus Areas (Address ALL)**:
  1. **Persona Failure**: Describe the Annotation Persona's most stubborn instance of **hallucination or resistance** exposed during the Week 09 Debugging activity. (e.g., "It kept outputting an irrelevant field even though the schema was strict.")
  2. **The Conversational Fix**: Explain the **specific conversational turn(s)** (the refined prompt text) you used to teach the Persona to adhere to its rules.
  3. **Computational Advantage**: Articulate how creating this specialized Persona enabled an ambitious, scalable research question that would have been much more difficult through manual annotation.
- Evaluation: Clarity of the conversational _fix_ and the depth of the analysis on the _value_ of agent creation. Does the essay demonstrate a nuanced understanding of 'Coding as Conversation'?

## What You Have to Hand In

### Team Leader

Team submission, to be uploaded to OWL Brightspace along with your individual assignment:

- All documents may contain your TEAMNAME (e.g., 3A) but should not contain any other identifying information (_do not include your names or Gmail addresses_). This is to protect your privacy when the contents of the files are uploaded to AI tools.
- _**TEAMNAME-ANNOTATION-PERSONA.txt**_:
  - The finalized text of the **A03 Master Prompt** (which includes the System Instruction and the JSON Schema). This is the technical recipe that defines your tool.
- _**TEAMNAME-MANUAL.pdf**_:
  - The one page instruction manual describing how to use the Portal and the Persona's rules.
- _**TEAMNAME-ANNOTATION-PERSONA-SCREENSHOT.png**_:
  - A single screenshot of the fully generated and working app as it appears in the AI Studio Code/Preview windows. (Proof of a working artifact).
- _**TEAMNAME-TEST-FILES.csv**_:
  - Google Sheets file saved as CSV containing information about your test runs (Test Number, Input Filename, Output JSON Filename)
- _**TEAMNAME-TEST-01.txt**_ to _**TEAMNAME-TEST-15.txt**_
  - The fifteen text files extracted from the PDFs to serve as inputs for your Annotation Portal.
- _**TEAMNAME-TEST-01.json**_ to _**TEAMNAME-TEST-15.json**_:
  - JSON files demonstrating the Persona's successful application across **15 documents**.

### All Students

Individual submission, to be uploaded to OWL Brightspace

- All document filenames will include your LASTNAME-FIRSTNAME but should not contain any identifying information within the file itself. This is to protect your privacy when the contents of the files are uploaded to AI tools.
- _**LASTNAME-FIRSTNAME-ESSAY.pdf**_
