# Wk 05. Structured Data: JSON In, JSON Out

Data validation and schema refinement. **Scholarly Primitive: Representing** (Verifying the quality of the structured data). **Goal**: Debug the JSON Schema by testing the Vibe-Coded app against unfamiliar data.

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
  - **Rule**: `"sentiment_score": { "type": "INTEGER" }`
  - **The Instance (The Result)**: This is what the AI produces when it reads a document and follows those rules.

**Example Instance**:

```jason
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

- **Problem**: The AI generated the code, but did it generate the right code? Did it adhere to the JSON schema 100% of the time?
- **Verification**: The process of ensuring that the extracted data is accurate and fits the defined schema.
- **Testing against Unfamiliar Data**: Since your team used a corpus created by a different team, this immediately tests the reliability of your Extractor on data it was not tuned for.

# Activity 1: JSON Validation and Refinement (40 Min)

## Getting Clean Text from the Class Data Pool

- **Challenge**: Our Vibe-Coded app needs a single text block, not a full PDF.
- **Procedure**:
  1. **Access**: Open the PDF file within **NotebookLM**.
  2. **Locate Segment**: Navigate to a chapter or section that is rich in the entities your Extractor targets.
  3. **Copy Clean Text**: Copy a continuous segment of text (approx. 500-1000 words, or 1-2 pages) and paste it into a temporary Doc or simple text editor to remove any extra line breaks or headers.
- **Goal**: Create a clean, usable text sample that accurately represents the source material but is isolated for the Extractor input field.

## Table Activity: Finding Errors in Representation

- **Task**: Run your team's Extractor App on text from **five** documents from the sub-corpus.
- **Procedure**:
  1. **Run Extraction**: Paste text and run the analysis.
  2. **Validate Structure**: Check if the output is **valid JSON**. (If not, the schema definition was bad).
  3. **Validate Content**: Check if the **content** adheres to the schema rules (e.g., if a field is defined as an `INTEGER` but the output is text).
  4. **Share Findings**: Discuss the most persistent error (e.g., the AI keeps including the citation text in the `key_entity_name` field) with your tablemates.
- **Goal**: Use the class time for rigorous, collaborative debugging and error identification for your individual team's tool.

# Debrief: The Systemic Flaw

## Preparing for Your Individual Essay for A02

- **Discussion**: What error did you find that cannot be fixed by editing the prompt? (e.g., the corpus simply too vague to provide an "integer confidence score").
- **Systemic Flaw**: The issue lies in the **design** of the JSON Schema itself. This flaw is the core subject of the Individual Essay for A02.
- **Key Question**: Does our **Representation** (the schema) truly serve our research question, or is it forcing the data into a mold that destroys meaning?

# Activity 2: Immediate Analytical Querying (40 Min)

## Table Activity: Testing the Computational Advantage

- **Task**: Use Vibe Coding to generate a quick **JavaScript utility script** that runs simple analysis on the extracted JSON data, proving the value of structure.
- **Procedure**:
  1. **Identify Insight**: Formulate a simple research question based on the canonical schema (e.g., "What is the average 'Sentiment Score' for all documents extracted so far?").
  2. **Use Vibe Coding**: "Generate a **JavaScript** function that takes an array of JSON objects (the data we just extracted) and calculates the average value of the `sentiment_score` key."
  3. **Execute & Share**: Run the script in the browser's console using your extracted JSON data. Discuss the numerical result with your tablemates.
- **Goal**: Immediately demonstrate the computational power of structured data, connecting the "Representing" primitive to the "Comparing" primitive (Week 06).

# Any questions?
