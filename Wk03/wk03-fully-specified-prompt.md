# Wk 03 Fully Specified Prompt for AI Studio

**Role:** Act as a senior frontend engineer and AI specialist.

**Objective:** Create a high-performance, aesthetically pleasing web application called "Regex Extractor AI." The app allows users to fetch content from any URL or paste raw HTML, clean it using heuristic algorithms, and then optionally use AI to generate a JavaScript Regular Expression from a natural language request to extract specific data points.

**Core Features & Logic:**

1. **Source Input:**
    - A URL input field that fetches content using `https://corsproxy.io/?` to bypass CORS restrictions.
    - A fallback textarea for manual HTML pasting.
2. **Heuristic Pre-processing:**
    - Use a `DOMParser` to remove non-content tags: `script`, `style`, `nav`, `header`, `footer`, `aside`, `form`, `iframe`.
    - Strip all inline CSS `style` attributes.
    - Heuristically identify the main content using selectors like `article`, `main`, `#content`, or `.content`.
3. **AI-Powered Regex Generation:**
    - Include an optional "What do you want to find?" text input (e.g., "all emails", "prices in USD", "links to PDFs").
    - Use the **Gemini 3 Flash** model via `@google/genai`.
    - The AI must return a JSON object containing: `regex` (string), `flags` (string), and `explanation` (string).
    - If a pattern is provided, apply the generated regex to the cleaned text and display only the matches.
        
4. **UI/UX Design:**
    - Use **Tailwind CSS** for a professional, "SaaS-like" aesthetic.
    - Color palette: Slate-50 background, Indigo-600 accents, Slate-900 text.  
    - Include a "Logic Card" that visualizes the AI-generated regex in a code block with a plain-English explanation. 
    - Show extraction stats (original length vs. cleaned length and reduction percentage). 
    - Ensure a fully responsive layout with clear loading states and robust error handling (especially for fetch failures).
        
**Technical Requirements:**

- **Language:** TypeScript/React.
- **AI SDK:** Use `@google/genai` (new `GoogleGenAI` class).
- **API Key:** Use `process.env.API_KEY` exclusively.
- **Model:** `Use gemini-3-flash-preview`.
- **System Instruction for AI:** "You are a Regular Expression expert. Convert natural language intent into valid JavaScript RegExp strings. Return JSON only."
    
**Deliverable:** A single-file implementation (or index.html + index.tsx) that is production-ready, accessible, and works out-of-the-box.
