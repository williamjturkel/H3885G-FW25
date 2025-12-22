# Wk 06. Verification, Grounding, and Systematic Comparison

**Scholarly Primitive: Comparing** (Systematic analysis of structured data). **Goal**: Use Vibe Coding to generate analytical code that confirms (or refutes) research hypotheses using your new JSON dataset.

# Review: The Structured Data Advantage

## Moving from Corpus to Dataset

- **Raw Corpus** (Wk 02/03): Dozens of PDF documents. Comparison is slow, anecdotal, and qualitative. NotebookLM for analysis.
- **JSON Dataset** (Wk 05): Dozens of JSON objects (Data Points). Comparison is fast, systematic, and quantitative. Vibe coded apps for analysis.
- **The Comparison Primitive**: We can now ask questions across the entire dataset that would have been impossible before: e.g., "What percentage of documents mentioning 'Guerilla Tactics' also score '4' or higher on the 'Confidence Score'?"

# Computational Dataset Structure

In our first activity, we are going to convert multiple, independent JSON outputs into a single, unified table suitable for large-scale analysis and comparison (the "Computational Dataset").

Each **row** in the spreadsheet represents a single, complete extraction (a single JSON object) from a source document. The **columns** are the fields defined in the JSON schemas used across the class.

Recall that a single JSON object might look something like this:

``` json
{
  "key_actor": "Robert McNamara",
  "date_of_event": "1965-02-07",
  "sentiment_score": 2,
  "doc_topic_tag": "Policy"
}
```

## Core Columns (From Canonical Schema)

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

If one of the teams (2A) used this schema exactly, then the expected columns in the Computational Dataset table might look something like this:

|Column Header (Key)|Data Type|Example Value|Description|
|---|---|---|---|
|**Source Document**|STRING|_Team A - Document 1_|Traceability: The unique ID of the document where the data originated.|
|**key_actor**|STRING|General Westmoreland|The primary named entity extracted.|
|**date_of_event**|STRING (YYYY-MM-DD)|1968-03-24|The standardized date of the event or document.|
|**sentiment_score**|INTEGER (1-5)|4|The quantified emotional tone regarding the actor/event.|
|**doc_topic_tag**|STRING|Policy|Classification of the document's subject matter.|



