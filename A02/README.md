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
  - **The Master Prompt**: The single natural language command that generates the entire app (UI, Logic, and Schema).
  - **The Final App**: The functional `.html` file that results from executing the Master Prompt.
  - **Instruction Manual**: A 1-page document detailing how to use the Extractor and explaining the design choices of the JSON Schema.
- **Input Data**: The team must test the tool by successfully extracting data from a sub-corpus they did not create (drawn from the Class Data Pool).

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


!!!!! FOOBAR  - got to Slide 5

Team Submission: The Master Prompt text, ????? the final .html file [DO I WANT THEM TO UPLOAD CODE?], and the Instruction Manual, information about test, JSON output from test.
