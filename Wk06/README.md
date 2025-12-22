# Wk 06. Verification, Grounding, and Systematic Comparison

**Scholarly Primitive: Comparing** (Systematic analysis of structured data). **Goal**: Use Vibe Coding to generate analytical code that confirms (or refutes) research hypotheses using your new JSON dataset.

# Review: The Structured Data Advantage

## Moving from Corpus to Dataset

- **Raw Corpus** (Wk 02/03): Dozens of PDF documents. Comparison is slow, anecdotal, and qualitative. NotebookLM for analysis.
- **JSON Dataset** (Wk 05): Hundreds of JSON objects (Data Points). Comparison is fast, systematic, and quantitative. Vibe coded apps for analysis.
- **The Comparison Primitive**: We can now ask questions across the entire dataset that would have been impossible before: e.g., "What percentage of documents mentioning 'Guerilla Tactics' also score '4' or higher on the 'Confidence Score'?"

# Computational Dataset Structure

In our first activity, we are going to convert multiple, independent JSON outputs into a single, unified table suitable for large-scale analysis and comparison (the "Computational Dataset").

Each **row** in the spreadsheet represents a single, complete extraction (a single JSON object) from a source document. The **columns** are the collection of all unique fields defined across all JSON schemas used by the class.

## Interpreting Traceability (Source vs. Method)

The dataset uses two key fields to maintain methodological traceability across the randomized team structure:

|Field|Purpose|Origin|
|---|---|---|
|**Source Document**|Identifies the original historical document being analyzed.|The document compiled by the **Assignment 01 Team** (e.g., _1A-SOURCE-04.pdf_).|
|**Team_ID**|Identifies the specific **Extractor Tool** (the schema and Master Prompt) used to generate this data point.|The **Assignment 02 Team** (e.g., _2C_) that ran the extraction.|

The information that links those two fields is in the _**TEAMNAME-TEST-FILES.csv**_ file submitted by each team as part of Assignment 02. It should contain the following fields

- Test Number
- Source Filename
- Input Text Filename
- Output JSON Filename

So, for example, if _**2C-TEST-FILES.csv**_ contains this record as one of its rows

- Test Number: 5
- Source Filename: 1A-SOURCE-04.pdf
- Input Text Filename: 2C-TEST-05.txt
- Output JSON Filename: 2C-TEST-05.json

Then TEAM_ID is 2C (the team that extracted the JSON file) and Source Document is 1A-SOURCE-04.pdf

This means that you are going to have to upload the _**TEAMNAME-TEST-FILES.csv**_ files to your application along with the JSON files that are named _**TEAMNAME-TEST-01.json**_ to _**TEAMNAME-TEST-05.json**_.

## Core Columns (From Canonical Schema)

In previous classes, we defined a Canonical Vietnam War Research JSON Schema. These columns are expected to be present across most, if not all, team extractions. 

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

If one of the Assignment 02 teams used this schema exactly, then the expected columns in the Computational Dataset table and their values might look something like this:

|Column Header (Key)|Data Type|Example Value|Description|
|---|---|---|---|
|**Source Document**|STRING|_1A-SOURCE-04.pdf_|Traceability: The unique ID of the document where the data originated.|
|**key_actor**|STRING|General Westmoreland|The primary named entity extracted.|
|**date_of_event**|STRING (YYYY-MM-DD)|1968-03-24|The standardized date of the event or document.|
|**sentiment_score**|INTEGER (1-5)|4|The quantified emotional tone regarding the actor/event.|
|**doc_topic_tag**|STRING|Policy|Classification of the document's subject matter.|

That example value would correspond to the extraction of a single JSON object that looks like this:

``` json
{
  "key_actor": "General Westmoreland",
  "date_of_event": "1968-03-24",
  "sentiment_score": 4,
  "doc_topic_tag": "Policy"
}
```

## Heterogeneity and Analysis Columns

Because different teams may have customized their schemas, however, the output will not be perfectly uniform across the JSON files created by different A02 teams. So the table that your application creates will have columns that track who generated the data and unique fields introduced by specific teams. **Any unique key introduced by a team's custom schema will appear as a new column**. Entries where that key was not extracted will be marked as `NULL`. This systematic variation is the basis for the comparison activity.

|Column Header (Key)|Data Type|Example Value|Purpose|
|---|---|---|---|
|**Team_ID**|STRING|2C|Required for **Comparing** methodology (identifying differences between tools).|
|**rhetorical_device**|STRING|Irony|**Unique Key** (e.g., created by Team 2D).|
|**local_impact_score**|INTEGER (1-10)|7|**Unique Key** (e.g., created by Team 2E).|
|**Notes_or_Flaw**|STRING|_Null or Error_|Space to flag instances where the extracted JSON failed validation.|

Once the app has processed all of the JSON files to create the Computational Dataset table, it might look something like this:

|Source Document|key_actor|date_of_event|sentiment_score|doc_topic_tag|Team_ID|rhetorical_device|local_impact_score|
|---|---|---|---|---|---|---|---|
|_1B-SOURCE-01.pdf_|General Abrams|1970-05-01|3|Military|2C|NULL|NULL|
|_1D-SOURCE-03.pdf_|Anti-War Protestors|1969-11-15|1|Cultural|2D|Metaphor|NULL|
|_1E-SOURCE-07.pdf_|President Johnson|1967-07-28|5|Policy|2E|NULL|9|
|_1A-SOURCE-05.pdf_|Vietnamese Civilians|1966-08-10|2|Cultural|2A|NULL|NULL|

In this case, Team 2D extracted a _rhetorical_device_ field which the other teams did not, and Team 2E extracted a _local_impact_score_ field which was unique. Those show up as separate columns and receive NULL values for any team that did not extract them.

# Activity 1: Data Import and Cleaning (25 Min)

## Table Activity: Pooling the JSON Outputs

- **Task**: Take a sample of the **JSON outputs** generated by all teams for Assignment 02 and load them into a **Google Sheet**.
- **Procedure**:
  1. **Collect Samples and Metadata**: For each AO2 team, collect at least two JSON files (named _**TEAMNAME-TEST-01.json**_ to _**TEAMNAME-TEST-05.json**_) and the _**TEAMNAME-TEST-FILES.csv**_ metadata file.
  2. **Use Vibe Coding**: Use Vibe Coding to generate a simple _JavaScript utility script_ that can read a batch of JSON files and a batch of metadata CSV files and format the key-value pairs (e.g., `key_actor`, `date_of_event`, ...) into rows/columns suitable for CSV/Sheets export.
  3. **Import**: Paste the resulting CSV data into a Google Sheet.
- **Goal**: Create a unified, visible Computational Dataset based on the class's collective extraction efforts.

# Debrief: Reliability and Heterogeneity

## Critiquing the Computational Dataset

- **Discussion**: Look at the Google Sheet you created.
- **Heterogeneity**: Do all teams' JSON data look identical? (Answer: No, the structure might be clean, but the extracted _values_ will differ based on source and prompt nuances).
- **Verification Challenge**: If one team's extractor gives **Confidence Score: 5** and another team's extractor gives **Confidence Score: 2** for the same type of source, what does this tell us about the **methodology**?
- **Key Point**: Comparison immediately exposes flaws in the **Representation** (JSON Schema/Prompt).

# Activity 2: Vibe Coding for Analysis (25 Min)

## Table Activity: Generating Comparison Scripts

- **Task**: Use Vibe Coding to generate short, analytical JavaScript snippets that can answer simple research questions using the data in the Google Sheet.
- **Procedure**:
  1. **Formulate Hypothesis**: e.g., "Primary military documents show a higher frequency of 'adversarial' relationships than newspaper editorials."
  2. **Generate Code**: Use Vibe Coding: "Write a JavaScript function that iterates through a list of JSON objects and counts how many objects contain `relationship_type: "adversarial"`."
  3. **Execute**: Run the code snippet on the data in the Sheet to get a numerical answer.
- **Goal**: Prove that a high-level research hypothesis can be answered in **seconds** using code generated on-demand. This demonstrates the method; to test an actual research hypothesis you would be much more systematic and exhaustive about both data collection and measurement.

# Activity 3: Geospatial Referencing and Comparison (30 Min)

## Table Exercise: Mapping the Data (Illustrating)

- **Task**: Use Vibe Coding to generate an app that extracts geographical references from a source text and visualizes their location for comparison.
- **Procedure**:
  1. **Extraction Prompt**: "Generate a **JavaScript function** that takes a text input and uses the Gemini API to extract **up to five distinct geographic locations** and output them as a JSON array of objects, each containing a `location_name` and estimated `latitude` and `longitude`."
  2. **Visualization Prompt**: "Generate a single-file **HTML app** that includes a basic map display and a JavaScript function to plot the coordinates from the previous JSON array as markers."
  3. **Test & Compare**: Run the full app using the text below and verify: Did the AI correctly assign the Lat/Long coordinates to the historical location?
- **Goal**: Use the **Illustrating** primitive to verify the accuracy of the AI's geospatial knowledge against the known facts (Comparison).

### Test Text for Geocoding

!!!!! NEED !!!!!

# Any questions?

