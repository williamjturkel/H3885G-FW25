# Assignment 02: Vibe-Coded Entity Extractor

## Core Goal: From Text to Data

- **Problem**: Text is flexible, but computers need **data**. We must move from paragraphs (unstructured text) to tables (structured data).
- **The Tool**: You will build a single-file, Vibe-Coded web application that accepts raw text input and forces the Gemini API to output verified, structured **JSON** data.
- **Scholarly Primitive Tested: Representing** (Creating a computational structure for analysis).
- **Methodological Insight**: We are forcing the AI to act as a **metadata transcriber**, not a writer.

## The Vibe-Coded Extractor Tool (Week 05. Jan 29-Feb 4)

After our Jan 29 meeting your **team** has to do the following

- **Choose a team leader**. This person will be responsible for submitting the team portion of the assignment to OWL. They will also be responsible for making sure that files get submitted to the [Class Data Pool](https://https//drive.google.com/drive/folders/1xWptcfsb1iWdcDU24xdbf4M_7Y9kSzVI?usp=sharing) on time.
- **Task**: Design and refine the single **Master Prompt** that serves as the top-down source code for the Extractor App, and use it to generate structured data outputs. All work is conducted within the **Google AI studio** environment.
- **Artifact Components**:
  - **The Master Prompt Text**: The single, finalized natural language command that generates the entire app (UI, Logic, and Schema). This text is the technical specification of your tool and serves as 'recipe' for future teams to generate your app.
  - **The Extractor App**: The functional `.html` file that results from executing the Master Prompt.
  - **Instruction Manual**: A 1-page document detailing how to use the Extractor and explaining the design choices of the JSON Schema.
- **Note on Portability**: Because all testing is done live within the cloud environment, **the Master Prompt Text itself** is the deliverable, not the code.

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

### Testing the Extractor App

- **Procedure**:
  1. The team must agree on the **single, best Master Prompt** and execute it in AI Studio to generate the final app.
  2. After creating the app, you must generate five final test runs for your submission. This requires two steps: **Data Preparation** and **Validation**.
     1. **Data Preparation (Isolating the Clean Text)**:
        - You must use the **NotebookLM** tool to isolate the specific text required for each test run from the larger PDF documents in the [Class Data Pool](https://https//drive.google.com/drive/folders/1xWptcfsb1iWdcDU24xdbf4M_7Y9kSzVI?usp=sharing).
        - **Method**: Open the PDF source in NotebookLM, locate a chapter or rich section, copy a segment (approx. 500-1000 words) that contains the entities your Extractor targets, and paste it into a clean text editor (like a Google Doc) to remove headers, footers, and page numbers. **This clean text is the mandatory input for your Extractor App**. For each test run, save the input file as a Text file named _**TEAMNAME-TEST-01.txt**_ to _**TEAMNAME-TEST-05.txt**_. Create a Google Sheets file named _**TEAMNAME-TEST-FILES.csv**_ containing information about your test runs (Test Number, Source Filename, Input Text Filename, Output JSON Filename).
     2. **Validation & Extraction**:
        - Run the final, optimized Extractor App (your team's .html file) on the 5 clean text segments you prepared in the previous step. The output will consist of 5 valid JSON files will be submitted as part of the team portion of your assignment. Name these files _**TEAMNAME-TEST-01.json**_ to _**TEAMNAME-TEST-05.json**_ to correspond to the input text files.

### Submitting Test Files to Class Data Pool

By Feb 4, the **team leader** will collect the _**TEAMNAME-TEST-FILES.csv**_, _**TEAMNAME-TEST-01.txt**_ to _**TEAMNAME-TEST-05.txt**_ text files, and the _**TEAMNAME-TEST-01.json**_ to _**TEAMNAME-TEST-05.json**_ JSON files into a single Google Drive folder and share that folder with the Instructor's Gmail address (_william.j.turkel@gmail.com_).

## Methodological Critique and Essay (Wk 06. Feb 5-Feb 12)

After our Feb 5 meeting **each individual student** has to do the following

- **Task**: Write a 500-word essay critically reflecting on the tool's performance and the methodological trade-offs of structured extraction.
- **Procedure**:
  1. **Validation**: Your team tested the Extractor App on five texts isolated from the PDFs and created JSON files as outputs
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

- Before you can submit an Assignment you will be asked to nominate one other person on your team as the Most Valuable Participant (MVP). Type in their Gmail account name (the part of their Gmail address before the at sign). This is mandatory and makes up part of the peer grade for each assignment.
- All documents may contain your TEAMNAME (e.g., 2A) but should not contain any other identifying information (do not include your names or Gmail addresses). This is to protect your privacy when the contents of the files are uploaded to AI tools.
- _**TEAMNAME-MASTER-PROMPT.txt**_
  - The single, finalized text file containing the complete Master Prompt. (This is the primary artifact).
- _**TEAMNAME-MANUAL.pdf**_
  - The one page instruction manual
- _**TEAMNAME-EXTRACTOR-APP-SCREENSHOT.png**_
  - A single screenshot of the fully generated and working app as it appears in the AI Studio Code/Preview windows. (Proof of a working artifact).
- _**TEAMNAME-TEST-FILES.csv**_
  - Google Sheets file saved as CSV containing information about your test runs (Test Number, Input Filename, Output JSON Filename)
- _**TEAMNAME-TEST-01.txt**_ to _**TEAMNAME-TEST-05.txt**_
  - The five text files extracted from the PDFs to serve as inputs for your Extractor
- _**TEAMNAME-TEST-01.json**_ to _**TEAMNAME-TEST-05.json**_
  - The five JSON files created as outputs during your tests

### All Students

Individual submission, to be uploaded to OWL Brightspace

- Before you can submit an Assignment you will be asked to nominate one other person on your team as the Most Valuable Participant (MVP). Type in their Gmail account name (the part of their Gmail address before the at sign). This is mandatory and makes up part of the peer grade for each assignment.
- All document filenames will include your LASTNAME-FIRSTNAME but should not contain any identifying information within the file itself. This is to protect your privacy when the contents of the files are uploaded to AI tools.
- _**LASTNAME-FIRSTNAME-ESSAY.pdf**_

## Screenshots of an Example Entity Extractor

When you are vibe coding, you working in collaboration with an AI that makes a number of decisions about how your app looks and works. You can request changes, but even people who follow the exact same instructions will end up with different working apps. When I tried following the A02 Vibe Coded Entity Extractor instructions in December 2025, I was able to get it working with a few revisions. To test it I used the AP news story by Anirhuddha Ghosal and Hau Dinh, ["The Vietnam War ended 50 years ago, but the battle with Agent Orange continues"](https://apnews.com/article/vietnam-war-anniversary-agent-orange-0829caefe48cc11fb88ab27982da922b) (April 30, 2025). To extract the text from the messy webpage and paste it into the app, I used the [Text Extractor](https://chromewebstore.google.com/detail/text-extractor/enihofloaglndlbpaockonfoehiflmma) Chrome Browser extension.

Here are some screenshots of my app to give you an idea of what yours might look like:

<image src="./Screenshots/a02-example-01.png" width=600 /><br/>
<image src="./Screenshots/a02-example-02.png" width=600 />
