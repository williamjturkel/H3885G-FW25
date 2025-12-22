# Wk 06. Verification, Grounding, and Systematic Comparison

**Scholarly Primitive: Comparing** (Systematic analysis of structured data). **Goal**: Use Vibe Coding to generate analytical code that confirms (or refutes) research hypotheses using your new JSON dataset.

# Review: The Structured Data Advantage

## Moving from Corpus to Dataset

- **Raw Corpus** (Wk 02/03): Dozens of PDF documents. Comparison is slow, anecdotal, and qualitative. NotebookLM for analysis.
- **JSON Dataset** (Wk 05): Dozens of JSON objects (Data Points). Comparison is fast, systematic, and quantitative. Vibe coded apps for analysis.
- **The Comparison Primitive**: We can now ask questions across the entire dataset that would have been impossible before: e.g., "What percentage of documents mentioning 'Guerilla Tactics' also score '4' or higher on the 'Confidence Score'?"

# Computational Dataset Structure

In our first activity, we are going to convert multiple, independent JSON outputs into a single, unified table suitable for large-scale analysis and comparison (the "Computational Dataset").

Each **row** in the spreadsheet represents a single, complete extraction (a single JSON object) from a source document. The **columns** are the collection of all unique fields defined across all JSON schemas used by the class.

## Interpreting Traceability (Source vs. Method)

The dataset uses two key fields to maintain methodological traceability across the randomized team structure:

|Field|Purpose|Origin|
|---|---|---|
|**Source Document**|Identifies the original historical document being analyzed.|The document compiled by the **Assignment 01 Team** (e.g., _1A-SOURCE-04.pdf_).|
|**Team_ID**|Identifies the specific **Extractor Tool** (the schema and Master Prompt) used to generate this data point.|The **Assignment 02 Team** (e.g., _Team C_) that ran the extraction.|

The information that links those two fields is in the _**TEAMNAME-TEST-FILES.csv**_ file submitted by each team as part of Assignment 02. It should contain the following fields

- Test Number
- Source Filename
- Input Text Filename
- Output JSON Filename

So, for example, if _**2C-TEST-FILES.csv**_ contains this record

- Test Number: 5
- Source Filename: 1A-SOURCE-04.pdf
- Input Text Filename: 2C-TEST-05.txt
- Output JSON Filename: 2C-TEST-05.json

Then TEAM_ID is 2C (the team the extracted the JSON file) and Source Document is 1A-SOURCE-04.pdf

!!!!!!!!!!!!!!!!!!!!!!!! FOOBAR !!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!! Maybe make a schematic picture showing document flow from A01 through A02 !!!!!

## Core Columns (From Canonical Schema)

Recall that a single JSON object might look something like this:

``` json
{
  "key_actor": "Robert McNamara",
  "date_of_event": "1965-02-07",
  "sentiment_score": 2,
  "doc_topic_tag": "Policy"
}
```

In previous classes, we defined a Canonical Vietnam War Research JSON Schema 

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

If one of the teams (2A) used this schema exactly, then the expected columns in the Computational Dataset table and their values might look something like this:

|Column Header (Key)|Data Type|Example Value|Description|
|---|---|---|---|
|**Source Document**|STRING|_Team A - Document 1_|Traceability: The unique ID of the document where the data originated.|
|**key_actor**|STRING|General Westmoreland|The primary named entity extracted.|
|**date_of_event**|STRING (YYYY-MM-DD)|1968-03-24|The standardized date of the event or document.|
|**sentiment_score**|INTEGER (1-5)|4|The quantified emotional tone regarding the actor/event.|
|**doc_topic_tag**|STRING|Policy|Classification of the document's subject matter.|

Because different teams may have customized their schemas, the output will not be perfectly uniform. The import process must account for this by adding one or more fields that support comparison. For example

|Column Header (Key)|Data Type|Example Value|Purpose|
|---|---|---|---|
|**Team_ID**|STRING|Team C|Required for **Comparing** methodology (identifying differences between tools).|
|**Notes_or_Flaw**|STRING|_Null or Error_|Space to flag instances where the extracted JSON failed validation.|

Once the app has processed all of the JSON files to create the Computational Dataset table, it will look something like this:

|Source Document|key_actor|date_of_event|sentiment_score|doc_topic_tag|Team_ID|
|---|---|---|---|---|---|
|Team B - Doc 1|General Abrams|1970-05-01|3|Military|Team C|
|Team D - Doc 3|Anti-War Protestors|1969-11-15|1|Cultural|Team A|
|Team E - Doc 7|President Johnson|1967-07-28|5|Policy|Team B|

