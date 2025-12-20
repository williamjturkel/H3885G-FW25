# Wk 05. Structured Data: JSON In, JSON Out

Data validation and schema refinement. **Scholarly Primitive: Representing** (Verifying the quality of the structured data). **Goal**: Debug the JSON Schema by testing the Vibe-Coded app against unfamiliar data.

# JSON Refresher: The Language of Data

### Anatomy of a Structured Object

- **JSON (JavaScript Object Notation)**: A standard text format for representing structured data. It is easy for humans to read and for machines to parse.
- **Syntax Rules**:
  - **Objects**: Surrounded by curly braces `{ }`.
  - **Key-Value Pairs**: Separated by a colon `:`. Keys must be in double quotes.
  - **Separators**: Pairs are separated by commas `,`.
- **The "Key"**: The label or category (e.g., `"key_actor"`).
- **The "Value"**: The actual data extracted from the text (e.g., `"General Westmoreland"`).

**Canonical Vietnam War Research JSON Schema**

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
