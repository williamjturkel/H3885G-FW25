# Wk 08. Deep Synthesis and Knowledge Generation (Workspace Integration)

Computable Knowledge and Custom Agents. **Scholarly Primitive: Annotating** (Creating specialized, reusable descriptive markup). **Goal**: Learn how to create and manage persistent, customized AI agents for specific, repeatable research tasks.

# Review: The Value of Annotation

## Unsworth's Primitive: Annotating

- **Definition**: Annotation is the process of attaching descriptive, interpretive, or contextual information to a source.
- **Traditional Annotation**: Slow, subjective, difficult to scale (e.g., highlighting, margin notes).
- **Computational Annotation**: Fast, consistent, and scalable. It allows us to apply a _controlled vocabulary_ (like a tag, a score, or an entity ID) across thousands of sources instantly.
- **Goal for A03**: We want an AI to apply consistent, specialized tags to our Vietnam War sources, beyond what our simple A02 extractor could do.

# Introducing Custom Agents (Gems)

## Specialized Tools for Specialized Tasks

- **What is a Custom Agent (Gem)?** A persistent, pre-programmed version of Gemini. You give it a specific name, a persona (System Instruction), and a rule set once.
- **Top-Down Advantage**: Instead of re-writing a complex prompt every time ("Act as a historian who specializes in military rhetoric and output a score..."), you just call the "Rhetoric Analyst Gem."
- **Use Case: Annotation**: We can build a Gem that specifically knows your JSON schema and applies a new layer of data (e.g., sentiment, rhetorical device, author intent) to your existing structured data.

