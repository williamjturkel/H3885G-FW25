# Wk 03. Data Acquisition and Preparation for Custom Corpus

A core research skill: harvesting data at scale. Using **Vibe Coding** to generate simple scripts for targeted web data ingestion, data cleaning, and **Sampling** of large document sets.

# The Need for Custom Data

## Why We Stop Using NotebookLM's Sources

- **Limitation of Grounding**: NotebookLM is excellent for deep reading of a _small, curated_ collection of digital sources, as we saw in Assignment 01. But large-scale digital research requires thousands of data points.
- **Unsworth's Sampling**: Research is often about collecting data based on **criteria** (e.g., "all mentions of 'Operation Ranch Hand' between 1965 and 1970").
- **The Top-Down Fix**: Instead of writing a program to crawl the web, we use **Vibe Coding** to generate a simple, customized **Sampler Tool** for us.
- **Insight**: We are generating **utility code**, not a final app. The code's output (clean text or a CSV) is the valuable product.

# Vibe Coding: Prompting for Browser-Native Code

## Rules for Generating a Research Tool

- **Rule 1: Browser Native Mandate**: ALL code must be in JavaScript (JS) and run inside a single HTML file.
- **Rule 2: Define the Action**: Clearly state the acquisition method (e.g., Given a URL as input write a JavaScript function to ingest the URL content and...").
- **Rule 3: Set Constraints**: Provide the specific criteria for **Sampling** and cleaning (e.g., "Only keep paragraphs containing the word 'Agent' or 'Agents' followed immediately by one or more color words such as 'Orange', 'White', etc. and ignore all HTML tags.")

# Activity 1: Generating the Sampler Tool (25 Min)

## Table Activity: Code for Corpus Acquisition

- **Task**: Use Vibe Coding in AI Studio to generate a working **Data Sampler** script.
- **Goal**: Generate a script that collects and cleans a specific type of text relevant to a research topic.
- **Procedure**:
    1. **Select a Target**: For this example we will be using Institute of Medicine (US) Committee to Review the Health Effects in Vietnam Veterans of Exposure to Herbicides, _Veterans and Agent Orange: Health Effects of Herbicides Used in Vietnam_, [Chapter 3: The U.S. Military and the Herbicide Program in Vietnam](https://www.ncbi.nlm.nih.gov/books/NBK236347/). Washington, DC: National Academies Press, 1994. The URL is https://www.ncbi.nlm.nih.gov/books/NBK236347/.
    2. **Prompt**: Write a Vibe Coding prompt (e.g., "Write a JavaScript function that requests a URL and fetches the content. Extract the main body text only, and remove all inline CSS tags and navigation menus.")
    3. **Test**: Run your app and see how it works. NOTE: The first time I tested this in December 2026, the app notified me that "Direct URL fetching may fail due to browser CORS policies. Paste HTML below for 100% reliability." It included both a URL input and an HTML input. The website did block extraction from the URL so I had to paste the HTML source instead. If you need to paste HTML source, visit the URL in the Chrome browser. Choose View &rarr; Developer &rarr; View Source. Click in the source and select all of it to copy to the clipboard. Then you can paste it into your app.

# Debrief: Code Quality and Acquisition Ethics

## Evaluating Our Generated Utility Code

- **Discussion**: What were the immediate challenges with the generated code? (e.g., failed imports, difficulty running). Auto-fix errors.
- **Code is a Means, Not an End**: We are not fixing bugs; we are determining if the AI-generated code successfully performs the **Sampling** primitive. If it fails repeatedly, we have to revise our prompt or rethink our approach.
- **Ethical Check**: When we collect data from public websites we have ethical responsibilities. A script that requests too much data too quickly is similar to a denial of service attack, so we need to make sure to prompt for polite behavior. Also, vibe coding should only be used on static, non-gated archival documents. It is OK to use it for resources that are available on the open web but not for, say, resources that we access through the university library catalogue. If in doubt, make sure to ask me.

# Iterative Development and a Fully Specified Prompt

## How I Improved the Data Sampler

- The Data Sampler tool that you created in Activity 1 extracts the main body of text in a long web page and removes some of the formatting.
- The process of extracting information from unstructured text is called **text mining**. Traditionally this involved searching for **regular expressions (regex)**, character patterns that allowed the machine to identify things in the text. A valid email address, for example, always includes the 'at sign symbol'. Now that we have LLMs that can 'read' text, we can prompt them to do things like "extract email addresses".
- There are some problems with using LLMs instead of regular expressions. They are more costly, more likely to comment on what they are doing, and less likely to be exhaustive.
- When I tried to improve the Data Sampler to extract specific information, I used these prompts in AI Studio
      - **Prompt**: Can you modify this app so that it requests a pattern (described in natural language) to optionally extract from the document? **Result**: Auto-fix error. App automatically uses LLM to read the source. LLM only extracts a few examples of pattern and provides a lot of commentary.
      - **Prompt**: The app should use Gen AI to translate the pattern into a regular expression that can be used on the JavaScript DOM. **Comment**: Instead of having the LLM read the whole document, I am asking it to use the LLM only to create a regular expression, then use that to process the webpage. **Result**: Successful application.
- This process, where I kept adjusting my requests until I got something working is called **Iterative Development**. But what if I want to share the results without having you go through a similiar iterative process?
- I gave AI Studio a final **Prompt**: Perfect. I would like to provide a single prompt to create an app like this so that my students can use it in AI Studio without going through the iterative development process we just followed. Please create that prompt. **Response**: Fully Specified Prompt.

# Activity 2: Data Cleaning and Preparation (35 Min)

## Table Activity: Structuring Raw Text for Analysis



Extract all sentences containing the word 'Agent' or 'Agents' followed immediately by one or more color words such as 'Orange', 'White'

Instead of using AI to do the extraction, use AI to translate the natural language refinement pattern into a regular expression
 
