# Wk 03. Data Acquisition and Preparation for Custom Corpus

Digital research is only as good as the source collection it is based on, and today we begin the hands-on work of acquiring and preparing our digital corpus. We will learn how to transform raw historical documents into a curated, AI-ready data set that serves as the foundation for the rest of the term. Harvesting data at scale is a core research skill. We use **Vibe Coding** to generate apps for targeted web data ingestion, data cleaning, and **Sampling** of large document sets.

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
    3. **Test**: Run your app and see how it works. <br/> NOTE: The first time I tested this in December 2025, the app notified me that "Direct URL fetching may fail due to browser CORS policies. Paste HTML below for 100% reliability." It included both a URL input and an HTML input. The website did block extraction from the URL so I had to paste the HTML source instead. If you need to paste HTML source, visit the URL in the Chrome browser. Choose _View &rarr; Developer &rarr; View Source_. Click in the source and select all of it to copy to the clipboard. Then you can paste it into your app.

# Debrief: Code Quality and Acquisition Ethics

## Evaluating Our Generated Utility Code

- **Discussion**: What were the immediate challenges with the generated code? (e.g., failed imports, difficulty running). **Auto-fix errors**.
- **Code is a Means, Not an End**: We are not fixing bugs; we are determining if the AI-generated code successfully performs the **Sampling** primitive. If it fails repeatedly, we have to revise our prompt or rethink our approach.
- **Ethical Check**: When we collect data from public websites we have ethical responsibilities. A script that requests too much data too quickly is similar to a denial of service attack, so we need to make sure to prompt for polite behavior. Also, vibe coding should only be used on static, non-gated archival documents. It is OK to use it for resources that are available on the open web but not for, say, resources that we access through the university library catalogue. If in doubt, make sure to ask me.

# Iterative Development and a Fully Specified Prompt

## How I Improved the Data Sampler

- The Data Sampler tool that you created in Activity 1 extracts the main body of text in a long web page and removes some of the formatting.
- The process of extracting information from unstructured text is called **text mining**. Traditionally this involved searching for **regular expressions (regex)**, character patterns that allowed the machine to identify things in the text. A valid email address, for example, always includes the at sign symbol. Now that we have LLMs that can 'read' text, we can prompt them to do things like "extract email addresses".
- There are some problems with using LLMs instead of regular expressions. They are more costly, more likely to comment on what they are doing, and less likely to be exhaustive.
- When I tried to improve the Data Sampler to extract specific information, I used these prompts in AI Studio
  - **Prompt**: Can you modify this app so that it requests a pattern (described in natural language) to optionally extract from the document? <br/> **Result**: Auto-fix error. App automatically uses LLM to read the source. LLM only extracts a few examples of pattern and provides a lot of commentary.
  - **Prompt**: The app should use Gen AI to translate the pattern into a regular expression that can be used on the JavaScript DOM. <br /> **Comment**: Instead of having the LLM read the whole document, I am asking it to use the LLM only to create a regular expression, then use that to process the webpage. <br/> **Result**: Successful application.
- This process, where I kept adjusting my requests until I got something working is called **Iterative Development**. But what if I want to share the results without having you go through a similiar iterative process? I gave AI Studio a final instruction
  - **Prompt**: Perfect. I would like to provide a single prompt to create an app like this so that my students can use it in AI Studio without going through the iterative development process we just followed. Please create that prompt. <br/> **Response**: [Fully Specified Prompt](./wk03-fully-specified-prompt.md).
- **Insight**: We can use the AI to tell us how to create a successful prompt. 

# Activity 2: Data Cleaning and Preparation (30 Min)

## Table Activity: Structuring Raw Text for Analysis

- **Task**: Use the [Fully Specified Prompt](./wk03-fully-specified-prompt.md) in AI studio to create a new app that extracts specific information from the body of a webpage.
- **Process**: You can copy the prompt from the link and paste it into a new AI Studio session.
- **Test**: Provide the URL for the Agent Orange chapter as an input and give the app this description of what you want: "Extract all sentences containing the word 'Agent' or 'Agents' followed immediately by one or more color words such as 'Orange', 'White'". Is the output a list of sentences that matches that description?
- **Deeper Understanding**: Unless you are already an experienced programmer, there will be a number of things in the fully specified prompt that you do not understand. Open a Gemini chat session and provide the prompt URL as input. Then ask Gemini to explain the different parts of the prompt to you at a level that suits your understanding. Discuss with the other students at your table.

# Debrief: From Raw Text to Usable Data

## The Gap Between Acquisition and Analysis

- **Challenge**: Raw text often contains metadata, headers, footers, and OCR errors that confuse LLMs. Since we were working from a digital document (a web page) rather than a digitized document, we did not have to deal with OCR errors or elements like "Page 1 of 50" in the text itself. With messier sources, we might have to vibe code apps to clean up the text before extraction.
- **Unsworth's Primitives**: The process just completed moves the data from **Sampling** (collection) to the first steps of **Representing** (cleaning/pre-structuring).
- **The Next Hurdle**: The current text is clean but **unstructured**. It's useless for advanced computational tasks like Network Analysis or large-scale comparison.
- **Moving Forward**: We need to go from a simple text file (.txt) to a **Structured Data** format (.json or .csv) that the AI can reliably read and process in the next phase.

# Assignment 2 Overview

[Assignment Page](<../A02>)

# Any questions?
