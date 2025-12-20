# Wk 04. From Research Idea to AI Prototype (Vibe Coding)

The Master Prompt: Generating the full research tool. **Scholarly Primitive: Representing** (Creating the container and the data structure). **Goal**: Craft a single natural language command that generates the entire Extractor App.

# What is a Research Prototype?

## The Master Prompt Mindset

- **The Challenge**: For a single tool (the Extractor), the UI design, the API call, the JSON schema, and the JavaScript logic must all be integrated into a **single Vibe Coding request**.
- **The Master Prompt**: This is the single, highly constrained, and verbose natural language command that serves as the **top-down source code** for the entire application.
- **Focus Shift**: Rather than writing code we are mastering the art of the integrated prompt. We are building a high-performance **engine** by designing the blueprint _first_.

# Anatomy of the Master Prompt

## Integrating Requirements into One Command

The Master Prompt must contain three parts. If you forget to include a requirement, Vibe Coding will not necessarily generate it.

|Component|Purpose|Prompt Instruction Example|
|---|---|---|
|**1. UI/Architecture**|Defines the interface and code language.|"Generate a single-file HTML/JS app with a large text input and a button..."|
|**2. Logic/Action**|Defines the API call and data flow.|"...when the button is clicked, call the Gemini API and send the text input..."|
|**3. Data Schema (Wk 05 Preview)**|Defines the structure of the output.|"...The response MUST be valid JSON, strictly following this schema: `paste schema here`"|

# Activity 1: Generating the Minimal UI Scaffold (25 Min)

## Table Activity: Building the Container

- **Task**: Use Vibe Coding in AI Studio to generate the basic, single-file HTML app.
- **Procedure**:
  1. **Draft the Prompt (Focus on UI)**: Write a prompt that requests a simple, modern-looking web app with a title, a large text input box, and a button. **Crucially, specify the logic must be in JavaScript**.
  2. **Generate & Refine**: Run the prompt to generate the initial code. Use natural language to make two small functional refinements (e.g., "Make the output area scrollable").
- **Goal**: Generate a clean HTML document that serves as the visual shell for the extractor your team will make in Assignment 02.

# Debrief: Code Review and Architecture

## Readying the Shell for the Master Prompt

- **Discussion**: Why is using JavaScript vital here? (Answer: Zero installation burden, browser-native execution).
- **The Pipeline Check**: Ensure your generated app has the three parts: 1) Input area, 2) Button (the trigger), and 3) Output display area.
- **Methodological Insight**: If the shell is bad now, the final app will be bad. We prioritize architecture before data logic.

# Activity 2: Drafting the Master Prompt (25 Min)

## Individual Task: Engineering the Top-Down Command

- **Task**: Individually draft the complete **Master Prompt** that will generate the final, functional Extractor App.
- **Input**: You must integrate the UI prompt developed in Activity 1 and the **Canonical Vietnam War Research JSON Schema** (below).
- **Procedure**:
  1. **Integrate UI**: Start with the prompt from Activity 1.
  2. **Integrate Logic**: Add the commands for API integration (e.g., "Use the fetch API to call the Gemini model...").
  3. **Integrate Schema**: Paste the canonical schema directly into the prompt text, using the strict language required (e.g., "The response MUST adhere to this structure...").
- **Goal**: Produce the single, integrated text block that represents the full complexity of your research tool.

**Canonical Vietnam War Research JSON Schema** (Use this in your prompt)

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

# Debrief: The Master Prompt as Source Code

## Complexity Managed by Language

- **Observation**: The final Master Prompt is long and highly prescriptive.
- **Pedagogical Insight**: This complex paragraph is the equivalent of writing dozens of lines of JavaScript code. You bypassed manual programming by mastering the top-down instruction set.
- **Team Handover Link**: This final Master Prompt (not the resulting code) is the true recipe for the Team Portion of A02.

# Activity 3: Prompt Peer Review (25 Min)

## Table Activity: Critiquing the Blueprint

- **Task**: Peer review your tablemates' individual Master Prompts.
- **Procedure**:
  1. **Exchange**: Share your full Master Prompt text with your tablemates. You could do this through Google Chat.
  2. **Critique**: Identify the single most ambiguous or contradictory instruction in each prompt. Discuss ways you might edit the prompt to correct flaws.
  3. **AI Assist**: Open a Gemini chat window and use a prompt like this: "I am trying to write a prompt to describe an app for AI studio. Can you make suggestions for improving the prompt? Here it is: `paste in prompt text`"
- **Goal**: Individual students leave with the highest quality, least ambiguous Master Prompt ready for discussion with their A02 team.

# Any questions?
