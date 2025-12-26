# Wk 09. Coding as Conversation: Custom Research Agents

**Scholarly Primitive: Annotating** (Ensuring consistency). **Goal**: Use natural language conversation (Vibe Coding) to refine and perfect the AI's System Instruction and Schema.

# Review: The First Failure

## Preparing for Conversational Debugging

- **Context**: The A03 team used the A03 Master Prompt to regenerate the Annotation Portal.
- **Problem**: The Portal can fail in a number of ways, e.g., hallucinating a source, misclassifying a score, ignoring the JSON schema.
- **The Fix**: We cannot edit the JavaScript code. The only way to fix the application's _logic_ is to edit the **Master Prompt/System Instruction text** that created the logic, and then regenerate the app.
- **Definition: Conversational Debugging**: The process of feeding the AI its own bad output and telling it, in natural language, why it failed, until it generates a new, perfect instruction set (the final **A03 Master Prompt**).

# The Three Types of Failure

## Diagnosing the Persona Flaw

|Failure Type|Description|Conversational Fix Example|
|---|---|---|
|**Ambiguity**|The Persona instruction was too vague (e.g., "Score the bias 1-10").|"Define 'Bias Score 1' as 'Strongly Pro-US' and 'Bias Score 10' as 'Strongly Anti-US' in the instructions."|
|**Schema Violation**|The AI produced text instead of a number, or omitted a required field.|"STRICTLY adhere to the JSON schema and do not output any text outside of the JSON object. Do not include your reasoning."|
|**Contextual Drift**|The Persona forgot its role and started synthesizing or generalizing.|"The sole purpose of this persona is to annotate. Do NOT write interpretive summaries or draw conclusions."|

# Activity 1: Identifying the Systemic Flaw (30 Min)

## Table Activity: Analyzing Failure Reports

- **Task**: Gather examples of failures from your A03 team portal. Share and critique these reports.
- **Procedure**:
  1. **Identify the Symptom**: What did the AI do wrong (e.g., "The `Propaganda_Intensity_Score` was always 5").
  2. **Diagnose the Cause**: Which part of the **System Instruction text** led to that predictable failure? (e.g., "We used the word 'intensity' but didn't define it.")
  3. **Group Consensus**: As a table, agree on the best single sentence to add to the System Instruction to fix the flaw.
- **Goal**: Prepare individual students to write the A03 critique essay by identifying the systemic flaw.

# Debrief: Prompt Quality as Code Quality

## Iterative Refinement

- **Observation**: Fixing a flaw requires precision. A single missing word in the System Instruction can cause dozens of bad JSON outputs.
- **Core Takeaway**: Your ability to write a precise, unambiguous **System Instruction** is the measure of your _coding_ skill in this top-down methodology.

# Activity 2: Vibe Coding the Conversational Fix (35 Min)

## Table Activity: Generating the Corrected Logic

- **Task**: Use a **new Vibe Coding session** to generate a corrected version of the Annotation Portal, now incorporating the fix defined in Activity 1.
- **Procedure**:
  1. **Start Clean**: Open a new AI Studio session.
  2. **Draft the Fix Prompt**: Start with the **A03 Master Prompt Text** and manually incorporate the corrective sentence agreed upon in Activity 1. Run the generation.
  3. **Run the Fix**: Run the newly generated app on the _same failing document_ that caused the failure in the first place. Did the flaw disappear?
- **Goal**: Verify that a simple, conversational change to the Master Prompt text can instantly fix the complex logic of the application.

# Activity 3: Finalizing the Annotation Rules (30 Min)

## Table Activity: Refining the Persona Artifact

- **Task**: Review the now-working Portal and finalize the definitive **A03 Master Prompt Text** for the assignment submission.
- **Procedure**:
  1. **Extract Final Text**: Copy the full, perfected **A03 Master Prompt Text** from the current session.
  2. **Schema Audit**: As a table, perform a final audit of the 3-property schema. Is every property truly quantifiable? Is there any risk of future ambiguity?
  3. **Documentation**: Individually save the final **A03 Master Prompt Text** for the individual A03 essay.
- **Goal**: Ensure individual students have all artifacts needed to write their A03 reflection.

