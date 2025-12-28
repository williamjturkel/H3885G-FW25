# Wk 05. Structured Data: JSON In, JSON Out

This week focuses on moving from the "vibe" of natural language to the precision of structured data. While we have been interacting with our archives through conversation, historical research often requires systematic analysis: counting, mapping, and comparing entities across hundreds of documents. 
Precision is crucial for historical work, and today we use NotebookLM Data Tables to turn messy narratives into structured data. We will focus on extracting entities into JSON format, allowing us to export our findings for more rigorous systematic analysis. **Scholarly Primitive: Representing** (Verifying the quality of the structured data).

# Activity 1: NotebookLM Data Tables (30 Min)

## Automated Entity Extraction

- **Task**: Instead of manually reading every document to find dates or names, you will instruct the AI to build a table for you.
- **Procedure**:
  1. Open NotebookLM with your Vietnam War notebook
  2. Select the "**Studio**" tab and click the Pencil icon beside "**Data Table**." This will allow you define specific "columns" for the data you want to extract across your entire corpus.
  3. Suggested Columns
     - **Entity Name**: The specific person, military unit, or location mentioned.
     - **Temporal Marker**: The exact or approximate date of the event.
     - **Sentiment/Vibe**: A brief "vibe-coded" description of the tone (e.g., "Official/Optimistic," "Critical/Dissenting").
     - **Source Citation**: The specific file and page number where this entity was found.
  4. **Verify**: check the "Source Citation" column against the original documents to ensure the AI hasn't "hallucinated" entities that don't exist in your source collection.
  5. **Export to Sheets**: Export the Data Table to Google Sheets. This allows you to save the table as a CSV file if you want to refer to it in the future.
  6. **Convert to JSON**: In your NotebookLM chat session try the following prompt: "_Convert the current Data Table into a structured JSON array suitable for a network analysis tool_." We will discuss this output next.

# JSON Refresher: The Language of Data

## Anatomy of a Structured Object

- **JSON (JavaScript Object Notation)**: A standard text format for representing structured data. It is easy for humans to read and for machines to parse.
- **Syntax Rules**:
  - **Objects**: Surrounded by curly braces `{ }`.
  - **Key-Value Pairs**: Separated by a colon `:`. Keys must be in double quotes.
  - **Separators**: Pairs are separated by commas `,`.
- **The "Key"**: The label or category (e.g., `"key_actor"`).
- **The "Value"**: The actual data extracted from the text (e.g., `"General Westmoreland"`).

### Canonical Vietnam War Research JSON Schema

```json
{
  "type": "OBJECT",
  "properties": {
    "key_actor": { "type": "STRING" },
    "date_of_event": { "type": "STRING", "format": "YYYY-MM-DD" },
    "sentiment_score": { "type": "INTEGER", "description": "Score 1-5 (1=Negative, 5=Positive)" },
    "doc_topic_tag": { "type": "STRING", "description": "Classify as 'Policy', 'Military', or 'Cultural'." }
  },
  "required": ["key_actor", "date_of_event", "sentiment_score", "doc_topic_tag"]
}
```

# From Schema to Instance

## Analyzing the Canonical Vietnam War JSON Schema

- **The Schema (The Rules)**: In Week 04, we used a specific set of rules to tell the AI what we wanted.
  - _Rule_: `"sentiment_score": { "type": "INTEGER" }`
- **The Instance (The Result)**: This is what the AI produces when it reads a document and follows those rules.

**Example Instance**:

```json
{
  "key_actor": "Robert McNamara",
  "date_of_event": "1965-02-07",
  "sentiment_score": 2,
  "doc_topic_tag": "Policy"
}
```

- **Critical Check**: Note that `2` is a number (Integer), not text `"2"`. Note that the date follows the strict `YYYY-MM-DD` format. This precision is what makes the data computable.

# Verification: The Methodological Checkpoint

## Trust, but Verify the Data

- **Problem**: The AI generated the code, but did it generate the _right_ code? Did it adhere to the JSON schema 100% of the time?
- **Verification**: The process of ensuring that the extracted data is accurate and fits the defined schema.
- **Testing against Unfamiliar Data**: Since your team used a corpus created by a different team, this immediately tests the reliability of your Extractor on data it was not tuned for.

# Activity 2: JSON Validation and Refinement (30 Min)

## Getting Clean Text from the Class Data Pool

- **Challenge**: Our Vibe-Coded app needs a single text block, not a full PDF.
- **Procedure**:
  1. **Access**: Open the PDF file within **NotebookLM**.
  2. **Locate Segment**: Navigate to a chapter or section that is rich in the entities your Extractor targets.
  3. **Copy Clean Text**: Copy a continuous segment of text (approx. 500-1000 words, or 1-2 pages) and paste it into a temporary Doc or simple text editor to remove any extra line breaks or headers.
- **Goal**: Create a clean, usable text sample that accurately represents the source material but is isolated for the Extractor input field.

## Table Activity: Finding Errors in Representation

- **Task**: Run your team's Extractor App **live in the AI Studio preview window** on text from **five** clean documents from the sub-corpus.
- **Procedure**:
  1. **Run Extraction**: Paste text and run the analysis.
  2. **Validate Structure**: Check if the output is **valid JSON**. (If not, the schema definition was bad).
  3. **Validate Content**: Check if the **content** adheres to the schema rules (e.g., if a field is defined as an `INTEGER` but the output is text).
  4. **Share Findings**: Discuss the most persistent error (e.g., the AI keeps including the citation text in the `key_entity_name` field) with your tablemates.
- **Goal**: Use the class time for rigorous, collaborative debugging and error identification for your individual team's tool.

# Debrief: The Systemic Flaw

## Preparing for Your Individual Essay for A02

- **Discussion**: What error did you find that _cannot_ be fixed by editing the prompt? (e.g., the corpus simply too vague to provide an "integer confidence score").
- **Systemic Flaw**: The issue lies in the **design** of the JSON Schema itself. This flaw is the core subject of the Individual Essay for A02.
- **Key Question**: Does our **Representation** (the schema) truly serve our research question, or is it forcing the data into a mold that destroys meaning?

# Activity 3: Immediate Analytical Querying (30 Min)

## Table Activity: Visualizing the Computational Advantage

- **Task**: Use Vibe Coding to generate a dedicated **Data Visualization App** that proves the value of your structured JSON data.
- **Procedure**:
  1. **Prepare Data**: Copy and aggregate the five JSON outputs generated in Activity 1.
  2. **Vibe Code Prompt**: Start a new Vibe Coding session. Prompt for a single-file HTML app that includes a **text input area** for pasting the combined JSON data, a button, and the **D3.js** library. The app must generate a **labeled Pie Chart** showing the frequency distribution of the `doc_topic_tag` field (Policy, Military, Cultural) when the button is clicked..
  3. **Execute & Analyze**: Paste your combined JSON data into the text input area, click the button, and run the preview.
- **Goal**: Immediately demonstrate the computational power of structured data, by visually connecting the "Representing" primitive to the "Illustrating" primitive.

# Any questions?
