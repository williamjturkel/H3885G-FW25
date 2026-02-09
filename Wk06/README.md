# Wk 06. Verification, Grounding, and Systematic Comparison

As scholars we must verify everything. Today we learn techniques to challenge our own AI agents. By performing systematic comparisons between AI outputs and primary sources, we ensure our digital research remains grounded in historical truth. **Scholarly Primitive: Comparing** (Systematic analysis of structured data).

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
|**Source Document**|Identifies the original historical document being analyzed.|The document compiled by the **Assignment 01 Team** (e.g., _1A-SOURCE-04_).|
|**Team_ID**|Identifies the specific **Extractor Tool** (the schema and Master Prompt) used to generate this data point.|The **Assignment 02 Team** (e.g., _2C_) that ran the extraction.|

The information that links those two fields is in the _**TEAMNAME-TEST-FILES.csv**_ file submitted by each team as part of Assignment 02. It should contain the following fields

- Test Number
- Source Filename
- Input Text Filename
- Output JSON Filename

So, for example, if _**2C-TEST-FILES.csv**_ contains this record as one of its rows

- Test Number: 5
- Source Filename: 1A-SOURCE-04
- Input Text Filename: 2C-TEST-05.txt
- Output JSON Filename: 2C-TEST-05.json

Then TEAM_ID is 2C (the team that extracted the JSON file) and Source Document is 1A-SOURCE-04

Rather than having you work with each of the individual _**TEAMNAME-TEST-FILES.csv**_ files, I have created a single file that contains all of the information for the whole class. It is called _**WHOLE-CLASS-TEST-FILES.csv**_.

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
|**Source Document**|STRING|_1A-SOURCE-04_|Traceability: The unique ID of the document where the data originated.|
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

Because different teams may have customized their schemas, however, the output will not be perfectly uniform across the JSON files created by different A02 teams. This means that the table that your application creates will have columns that track who generated the data and unique fields introduced by specific teams. **Any unique key introduced by a team's custom schema will appear as a new column**. Entries where that key was not extracted will be marked as `NULL`. This systematic variation is the basis for the comparison activity.

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

# Activity 1: Data Import and Cleaning (30 Min)

## Table Activity: Preparing the Class Data Pool (Batch Processing)

- **Task**: Take a sample of the **JSON outputs** and the required **metadata CSV** generated by all teams for Assignment 02 and use Vibe Coding to generate an app that loads them into a **Google Sheet**.
- **Procedure**:
  1. **Collect Samples**: For each A02 team, collect at least two JSON files (these are named _**TEAMNAME-TEST-01.json**_ to _**TEAMNAME-TEST-05.json**_) from the shared Drive folder. You will also need a copy of the _**WHOLE-CLASS-TEST-FILES.csv**_ metadata file.
  2. **Vibe Code the Converter App**: Use Vibe Coding to generate a dedicated, single-file HTML app. The app must contain **a file upload field** for multiple JSON files, another for the CSV metadata file, and a large **output area** that displays the combined data formatted as **CSV (comma-separated values) when a button is clicked**. Work through the points below carefully and use them to develop your prompt:
     - Each row in the spreadsheet represents a single, complete extraction (a single JSON object) from a source document. The columns are the collection of all unique fields defined across all of the uploaded JSON files.
     - The output dataset will use two key fields to methodological traceability, `TEAM_ID` and `Source Document`. For an input JSON file, these fields can be extracted from the metadata CSV. Suppose one of the JSON files is named `2C-TEST-05.json`. There will be a record in the metadata CSV files that looks something like this: `Test Number: 5, Source Filename: 1A-SOURCE-04, Input Text Filename: 2C-TEST-05.txt, Output JSON Filename: 2C-TEST-05.json`. In this case `TEAM_ID` should be set to `2C` and `Document Source` should be `1A-SOURCE-04.pdf` for all JSON objects extracted from this JSON file.
     - Any unique key introduced in one of the JSON files will appear as a new column. Entries where that key was not extracted will be marked as `NULL`.
  3. **Import Data**: Use the app to generate the master CSV text. Copy the resulting text from the output area and paste it into a  Google Sheet.
- **Goal**: Create a unified, visible **Computational Dataset** based on the class's collective extraction efforts.

# Debrief: Reliability and Heterogeneity

## Critiquing the Computational Dataset

- **Discussion**: Look at the Google Sheet you created.
- **Heterogeneity**: Do all teams' JSON data look identical? (Answer: No, the structure might be clean, but the extracted _values_ will differ based on source and prompt nuances).
- **Verification Challenge**: If one team's extractor gives **Confidence Score: 5** and another team's extractor gives **Confidence Score: 2** for the same type of source, what does this tell us about the **methodology**?
- **Key Point**: Comparison immediately exposes flaws in the **Representation** (JSON Schema/Prompt).

## Accessing AI "Thinking"

We can leverage the **Gemini 3 "Thinking"** mode to audit our agents and ensure they aren't just telling us what we want to hear.

### Understanding Gemini 3 "Thinking"

In late 2025, Google introduced a specialized reasoning mode that differs from standard "fast" generation.

- **The Difference**: Standard models (like Flash) predict the next likely word. **Thinking models** use iterative rounds of reasoning to explore multiple hypotheses and cross-reference data _before_ they start writing the final response.
- **Why it matters for Scholarship**: This mode is significantly better at catching subtle logical contradictions in historical accounts and identifying "hallucinations" in your JSON entity extractors.
- **How to Access "Thinking"**: Select the "**Thinking**" toggle in the model dropdown of Gemini.

# Activity 2: The Historical "Red-Team" (20 Min)

<image src="./google-search-grounding.png" width=600 />

## Table Activity

- **Task**: "Red-teaming" is the process of intentionally trying to break or find flaws in a system. You will use a **Thinking-enabled agent** to critique the CSV file you created in Activity 1.
- **Procedure**:
  1. **Go to Playground section of AI Studio**: See screenshot above.
  2. **Input Your CSV**: Provide the agent with the computational dataset CSV you created in Activity 1.
  3. **The Prompt**: "You are a skeptical historical auditor. Using the highest thinking level, review this data. Identify any extracted dates, locations, or units that seem historically improbable based on the context of the Vietnam War. Point out potential hallucinations."
  4. **The Goal**: Find at least two instances where the agent over-generalized or misattributed a fact.
  5. **Systematic Grounding**: Verification is not just about "thinking"; it’s about checking the source. We will use the **Grounding with Google Search** tool alongside our local Vietnam War corpus.
     - **Integrated Grounding**: In Gemini 3, the model can now perform real-time searches to verify "world knowledge" (like the date of the Tet Offensive) against the specific, private documents in your archive.
     - **Exercise**: Pick a controversial event from your archive. Ask the Thinking model: "_Compare [Document A]'s account of this event with the consensus of modern scholarship found via Google Search. Where are the significant discrepancies?_"

# Activity 3: Geospatial Referencing and Comparison (25 Min)

## Table Exercise: Mapping the Data (Illustrating)

- **Task**: Use Vibe Coding to generate a single, integrated **Geospatial Extractor/Map App** that extracts locations from a source text and plots them instantly.
- **Procedure**:
  1. **Write the Master Prompt**: Formulate a single Vibe Coding prompt that requests: "Generate a **single-file HTML app** with a text input area. When the button is clicked, use the Gemini API to extract **up to five distinct geographic locations** from the text, and output them as a JSON array containing `location_name` and estimated `latitude`/`longitude`. **The app must then immediately render a map display** and plot the extracted coordinates as markers."
  2. **Test & Compare**: Run the full app using the text on the US Defense POW/MIA Accounting Agency, [The Tet Offensive](https://dpaa-mil.sites.crmforce.mil/dpaaFamWebInTetOffensive) webpage and verify: Did the AI correctly assign the Lat/Long coordinates to the historical location?
- **Goal**: Use the **Illustrating** primitive to verify the accuracy of the AI's geospatial knowledge against the known facts (Comparison).

# Any questions?

