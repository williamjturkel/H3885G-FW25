# Assignment 01: Agent Persona and Grounding

## Teams and Google Chat Spaces

Each student has been randomly assigned to one of 7 teams. Each team has up to 6 people. You will receive information about which team you have been assigned to. I will also create a private Google Chat space for each team and invite you to join it. When you join the chat, be sure to introduce yourself (including your name and Gmail address) so that your teammates know who you are. Google Chat spaces are "persistent, collaborative group areas for teams or shared interests, acting as central hubs for discussions, file sharing, task assignment, and project management, accessible via Gmail or the Chat app, allowing threaded conversations and integration with other Google tools like Drive for streamlined teamwork within or outside organizations."

Key features of Google Chat spaces

- **Centralized Communication**: Keep all conversations, files, and tasks for a project or topic in one place.
- **Threaded Conversations**: Start threads for detailed discussions, keeping main channels organized.
- **Collaboration**: Share Drive files (Docs, Sheets, Slides), assign tasks, and schedule meetings directly within the space.
- **Accessibility**: Available in Gmail, the Google Chat app, or chat.google.com.

I will monitor your team's space to assess your teamwork. Since this is part of your grade, it is important to use this tool for teamwork rather than other channels.

## Topics

Each team has a choice of creating <u>one</u> of two sub-topics to build their initial corpus. Here are your options

- **1A**
  - **Official Military Records**: Declassified government reports, field operations summaries, casualty counts.
  - **Digital Photo Captions/Metadata**: Focusing on the textual context of iconic photos.
- **1B**
  - **Newspaper Editorials (US Perspective)**: Analysis of major US paper opinions (1965-1970).
  - **Music Lyrics (Pro- and Anti-War)**: Transcriptions and analysis of popular songs.
- **1C**
  - **Congressional Hearing Transcripts**: Debates and testimony regarding funding and policy.
  - **Anti-War Movement Pamphlets**: Texts from student groups, activist organizations, and protest flyers.
- **1D**
  - **Official Casualty Reports/Statistics**: Structured data files (CSV, simple tables) detailing troop movements, injuries, and fatalities.
  - **Contemporary Media Reviews/Criticism**: Reviews of films, books, and art about the war (1980s-1990s).
- **1E**
  - **Academic Historical Monographs (Snippets)**: Sampling of secondary source arguments and literature reviews.
  - **Visual Art & Photography Captions**: Focusing on the textual analysis of museum captions, exhibit descriptions, and critical reviews of wartime photography and art, linking text to image.
- **1F**
  - **Propaganda Texts**: Texts aimed at North Vietnamese, South Vietnamese, or US troops.
  - **Veteran Oral Histories**: Transcripts of interviews from different service branches and experiences.
- **1G**
  - **Post-War Policy/Treaty Texts**: Documents related to the aftermath and refugee crisis (1975-1980).
  - **Personal Soldier Letters/Diaries**: Digitized collections of letters home from the front lines.

## Important Note about Filenames and File Contents

In this class you will create two kinds of documents to submit for grading. For **team assignments** all documents may contain your TEAMNAME (e.g., 1A) but should not contain any other identifying information (_do not include your names or Gmail addresses_). This is to protect your **privacy** when the contents of the files are uploaded to AI tools. A typical document for a team assignment submission might be named something like **_1D-SCOPE.pdf_**, where 1D is the fourth team for Assignment 01, and the rest of the filename was specified in the assignment instructions.

For **individual assignments**, filenames will include your LASTNAME-FIRSTNAME but should not contain any identifying information within the file itself (_do not include your name or Gmail address_). This is to protect your **privacy** when the contents of the files are uploaded to AI tools. A typical document for an individual assignment submission might be named something like **_CARNEY-MARK-ESSAY.pdf_** if your name is Mark Carney. (He probably won't be in the class).

It is important that you pay close attention to the filenaming instructions and conventions. **Teams and individuals will lose marks if they name files improperly or do not follow these instructions**. The reason for this requirement is that so other people can reuse the products that you create. Consistent naming allows your classmates (and AIs) to know where to find information and what to expect.

## Corpus Creation (Wk 02. Jan 8-Jan 14)

Between our first and second class meetings, your **team** has to do the following

1. **Choose a team leader**. This person will be responsible for submitting the team portion of the assignment to OWL. They will also be responsible for making sure that files get submitted to the Class Data Pool on time.
2. **Discuss and choose which of the two sub-topics you are going collect a corpus for**.
3. **Define the scope of your collection**. The focus should be specific enough to be manageable but diverse enough for analysis. Write a short statement (a few sentences) describing the scope of your collection.
4. **Procudure (Collection Protocol)**:
   1. Use the **Structured Discovery Workflow** (below) to find and save sources as Files in your private Google Chat space.
   2. The files should be renamed to **_TEAMNAME-SOURCE-01.pdf_**, **_TEAMNAME-SOURCE-02.pdf_**, ...
   3. Create a Google Sheets document named **_TEAMNAME-SOURCES.csv_** to keep track of the sources you collect and save it as a CSV File in your private Google Chat space. Capture the following **metadata** for each source
       - Title
       - Author
       - Date
       - Source Filename (this will be something like _1D-SOURCE-07.pdf_)
       - URL  
   4. Upload all files to a **single NotebookLM notebook**.
   5. Use the NotebookLM **Share function** to grant all teammates Editor/Viewer access.

### Structured Discovery Workflow

1. **Constrained Search:** Use Gemini Advanced / Deep Research to find high-quality, long-form content.
    - **Prompt Example:** "Provide a list of 10 publicly available URLs for digitized Official Military Records from the Vietnam War period (1964-1975) from reputable archives or university collections. Focus on long PDF or text documents."
    - **Course Resources:** The [Resources](<../Resources>) section of this site contains some starting points with high-quality materials.
2. **Harvest URLs & Deep Research**:
    - Collect the 10 most relevant URLs provided by Gemini.
    - Use the **URL-loading feature** in the Gemini interface to ask Gemini to summarize and extract entities from each URL. This ensures the document is readable by the AI later.
3. **PDF/Document Conversion**:
    - For any relevant web pages (not PDFs), use your browser's "Print to PDF" function. This ensures a clean, single-file document suitable for NotebookLM grounding.
    - **Goal**: Convert all selected web content into PDF format (this is mandatory for reliable grounding in NotebookLM).
4. **Repeat & Filter**:
    - Repeat steps 1-3 until your team has acquired enough sources. How much is enough? If your sources are book length (hundreds of pages), then you need about 10 of them. If they are shorter (e.g., long webpages) then you will need about three times as many. For mixtures of book-length and shorter sources, somewhere in between. (This is because of the source limits of the free tier of NotebookLM. In Dec 2025 they were 500,000 words or 200MB per source file, with a maximum of 50 sources per notebook.)
    - Filter ruthlessly: Exclude short news clippings, simple landing pages, or low-quality sources.

### Submitting PDF Files to Class Data Pool

By Jan 14, the **team leader** will collect the **_TEAMNAME-SOURCES.csv_** file and the PDF sources into a single Google Drive folder and share that folder with the Instructor's Gmail address (_william.j.turkel@gmail.com_).

## High-Level Briefing Document (Wk 03. Jan 14-Jan 21)

Between our second and third class meetings your **team** has to do the following

- **Task**: Use your newly grounded NotebookLM corpus to generate a high-level **Briefing Document**.
- **Method**: Collaborate in the shared NotebookLM environment to formulate a question that requires **synthesis** across multiple sources in the corpus.
- **Output**: The final synthesized text generated by NotebookLM (approx. 750 words).
- **Evaluation**: Graded on the quality of the corpus, its relevance to the sub-topic, and the coherence of the final synthesized brief.

## Persona Critique and Essay (Wk 03. Jan 14-Jan 21)

Between our second and third class meetings **each individual student** has to do the following

### Design, Apply, and Critique Three Personas

- **Objective**: Test how System Instructions (Personas) affect the AI's research output on the same question.
- **Input**: Use your team’s shared NotebookLM corpus.
- **Procedure**:
    1. Formulate one **complex research question** for the corpus.
    2. Design **three distinct System Instructions (Personas)** (e.g., "Skeptical Historian," "Anti-War Journalist," "Policy Analyst"). These personas should make sense for your team's sub-topic.
    3. Run the **same research question** three times, applying a different persona each time.
    4. Save each of the three raw AI-generated answers
 
### Essay

- **Format**: A 500-word critical essay comparing the three AI-generated answers.
- **Focus**:
    - **Effectiveness**: Which persona produced the most effective scholarly argument?
    - **Citation**: How did the persona influence the **Referring** primitive (the number and quality of NotebookLM citations)?
    - **Justification**: You must explicitly justify your choice of the "best" answer, backing your claim with evidence _from the corpus_.

## What You Have to Hand In

### Team Leader

Team submission, to be uploaded to OWL Brightspace along with your individual assignment:

- All documents may contain your TEAMNAME (e.g., 1A) but should not contain any other identifying information (_do not include your names or Gmail addresses_). This is to protect your privacy when the contents of the files are uploaded to AI tools.
- **_TEAMNAME-SCOPE.pdf_**
    - Statement describing the scope of your collection
- **_TEAMNAME-SOURCES.csv_**
    - Google Sheets file saved as CSV containing source metadata (Title, Author, Date, etc.)
- **_TEAMNAME-BRIEFING.pdf_**

### All Students

Individual submission, to be uploaded to OWL Brightspace

- All document filenames will include your LASTNAME-FIRSTNAME but should not contain any identifying information within the file itself. This is to protect your privacy when the contents of the files are uploaded to AI tools.
- **_LASTNAME-FIRSTNAME-AI-ANSWERS.pdf_**
    - Collect all three answers in a single document
    - Give each answer a title which reflects the Persona that generated it
- **_LASTNAME-FIRSTNAME-ESSAY.pdf_**

## Pedagogical Focus: Why We Do This

|**Component**|**Pedagogical Goal**|**Why it Matters**|
|---|---|---|
|**Team Corpus (A01)**|Forces **methodological resource creation**.|You must be able to **create** the digital source collections you study.|
|**Individual Persona Critique**|Tests the ability to **constrain the agent**.|Critical research requires **predictable output**, not general chat.|
|**Referring/Citations**|Reinforces the **scholarly imperative** of verification.|Grounding is the foundation for all subsequent **Representing** and **Comparing** tasks.|
|**Team Rotation**|Allows research outputs to be handed over.|Subsequent teams will use your corpus—this enforces rigor and accountability.|
