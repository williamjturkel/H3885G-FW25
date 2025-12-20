# Wk 04. From Research Idea to AI Prototype (Vibe Coding)

The Master Prompt: Generating the full research tool. **Scholarly Primitive: Representing** (Creating the container and the data structure). **Goal**: Craft a single natural language command that generates the entire Extractor App.

## What is a Research Prototype?

### The Master Prompt Mindset

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
|**3. Data Schema (Wk 05 Preview)**|Defines the structure of the output.|"...The response MUST be valid JSON, strictly following this schema:`paste schema here`"|
