# Assignment 02: Vibe-Coded Entity Extractor

## Core Goal: From Text to Data

- **Problem**: Text is flexible, but computers need **data**. We must move from paragraphs (unstructured text) to tables (structured data).
- **The Tool**: You will build a single-file, Vibe-Coded web application that accepts raw text input and forces the Gemini API to output verified, structured **JSON** data.
- **Scholarly Primitive Tested: Representing** (Creating a computational structure for analysis).
- **Methodological Insight**: We are forcing the AI to act as a **metadata transcriber**, not a writer.

## The Vibe-Coded Extractor Tool (Week 05. Jan 29-Feb 4)

After our Jan 29 meeting your **team** has to do the following

- **Task**: Generate the complete, integrated Extractor App using a single **Master Prompt** and validate its output.
- **Artifact Components**:
  - **The Master Prompt**: The single natural language command that generates the entire app (UI, Logic, and Schema). This serves as 'recipe' for future teams to generate your app.
  - **The Final App**: The functional `.html` file that results from executing the Master Prompt.
  - **Instruction Manual**: A 1-page document detailing how to use the Extractor and explaining the design choices of the JSON Schema.
- **Input Data**: The team must test the tool by successfully extracting data from five documents in a sub-corpus they did not create (drawn from the Class Data Pool).
- **Output Files**: These 5 valid JSON files will be submitted as part of the team portion of your assignment.

### The Required JSON Schema: Defining Data Structures for Vietnam War Research

Your Schema Must Define and Extract at Least FOUR entities or relationships per source:
- **Schema as Prompt Input**: Your final JSON schema must be included inside the Master Prompt (Wk 04) to ensure the AI generates the API call correctly.
- **Example Entities** (Must be defined as OBJECT properties):
  - `document_id` (string)
  - `key_entity_name` (string)
  - `date_of_occurrence` (string, standard format YYYY-MM-DD)
  - `relationship_type` (string, e.g., 'causal', 'adversarial', 'supportive')
  - `confidence_score` (integer, 1-5, where 5 is high)
- **Evaluation Note**: The precision of this schema defines the limits of your research.

## Methodological Critique and Essay (Wk 06. Feb 5-Feb 12)

After our Feb 5 meeting **each individual student** has to do the following

- **Task**: Write a 500-word essay critically reflecting on the tool's performance and the methodological trade-offs of structured extraction.
- **Procedure**:
  1. **Validation**: Your team tested the Extractor App on five documents and created JSON files as outputs
  2. **Identify Failures**: Try to find at least two instances where the Extractor **failed** or produced **incorrect data** (e.g., hallucinated a date, misclassified a relationship).
  3. **Critique**: Analyze the root cause of the failure. **Was the systemic issue a flaw in the JSON Schema (Representation) or the Master Prompt's System Instruction**? Or was it something else?
- **Evaluation**: Graded on depth of **methodological insight** and clarity in articulating computational limitations.

### Individual Critique: Guiding Questions about the Depth of the Flaw (Systemic vs. Surface)

Use these questions to guide your 500-word critique:

- **Structural Limits**: Did the strict JSON schema (e.g., forcing a 1-5 integer score) destroy necessary nuance in the source material? How is the primitive of **Representing** limiting your interpretation?
- **Prompt vs. Schema**: Which is the weaker link? Did the AI fail because the schema was too complex, or because the Master Prompt's system instructions were ambiguous? Or for some other reason?
- **Computational Advantage**: Despite the flaws, how does having 100 structured data points enable a form of **Comparison** or **Network Analysis** that would be impossible with 100 text documents?

## What You Have to Hand In

### Team Leader

Team submission, to be uploaded to OWL Brightspace along with your individual assignment:

- All documents may contain your TEAMNAME (e.g., 2A) but should not contain any other identifying information (do not include your names or Gmail addresses). This is to protect your privacy when the contents of the files are uploaded to AI tools.
- _**TEAMNAME-MASTER-PROMPT.pdf**_
  - The complete text of your prompt
- _**TEAMNAME-MANUAL.pdf**_
  - The one page instruction manual
- _**TEAMNAME-APP.html**_
  - The HTML file of your application
- _**TEAMNAME-TEST-FILES.CSV**_
  - Google Sheets file saved as CSV containing information about your test runs (Test Number, Input Filename, Output JSON File)
- _**TEAMNAME-TEST-01.json**_ to _**TEAMNAME-TEST-05.json**_
  - The five JSON files created as outputs during your tests

### All Students

Individual submission, to be uploaded to OWL Brightspace

- All document filenames will include your LASTNAME-FIRSTNAME but should not contain any identifying information within the file itself. This is to protect your privacy when the contents of the files are uploaded to AI tools.
- _**LASTNAME-FIRSTNAME-ESSAY.pdf**_

