# Wk 10. Networks and Relational Analysis

**Scholarly Primitive: Illustrating** (Visualizing complex data). **Goal**: Use Vibe Coding to build a tool that extracts complex relational data and visualizes it as a network graph.

# Network Analysis: The Building Blocks

## Anatomy of a Graph

- **The Concept**: A network graph is a map of relationships. It moves us from studying _individual things_ to studying the _connections between things_.
- **The Two Core Atoms**:
  1. **Nodes (Vertices)**: The entities in the system.
     - _Examples_: A Person, A Document, A Location, An Organization.
  2. **Edges (Links)**: The relationship connecting two nodes.
     - **Examples**: "Wrote_Letter_To", "Commanded_Unit", "Located_In".
- **Visual Metaphor**: If a spreadsheet is a list of contacts, a network graph is a map showing who knows whom.

# Network Analysis: What We Measure

## Reading the Structure

- **Why do we graph data?** To see patterns of influence and community that are invisible in a list.
- **Key Metrics**:
  - **Degree Centrality (The Hub)**: Which node has the most connections? (e.g., The General who issues the most orders).
  - **Edge Weight (The Strength)**: How thick is the connection? (e.g., Two soldiers who served together in _five_ different operations have a "heavier" weight than those who served in one).
  - **Clusters (Communities)**: Groups of nodes that are more connected to each other than to the rest of the network.
 
# Applying Network Thinking to our Data

## From JSON Tables to Connected Graphs

- **The Shift**: For Weeks 01-09, we treated our data as **Rows** (independent documents). Now, we treat them as **Connected Points**.
- **Our Data Transformation**:
  - **Nodes**: The "Key Actors" or "Key Entities" you extracted in A02/A03.
  - **Edges**: The interactions between them that we will extract today.
- **The Research Question**: In addition to asking questions like "How many times does General Westmoreland appear?" we can begin asking questions like "Who is the bridge between the 'Military' cluster and the 'Policy' cluster?"

# Activity 1: The Network Extractor App (40 Min)

## Table Activity: Representing Connections

- **Task**: Generate a specialized Extractor App designed only to find and structure relationships.
- **Procedure**:
  1. **Define Schema**: The schema must output two nodes and the connecting edge (e.g., `Node_A`, `Node_B`, `Relationship_Type`).
  2. **Write Master Prompt**: Use Vibe Coding to generate a **single-file HTML app** (the Network Extractor). The prompt must instruct the app to:
     - Take a text input.
     - Use the Gemini API to extract **all named entities** and their relationships from the text.
     - Output the data in a strict **JSON array** of Node/Edge pairs.
  3. **Test**: Run the app on the text from David Coleman and Marc Selverstone, ["Lyndon B. Johnson and the Vietnam War"](https://prde.upress.virginia.edu/content/Vietnam) (2014) at the University of Virginia's Presidential Recordings Digital Edition. Does the JSON output correctly list the relationships?
- **Goal**: Create clean, raw Network Data (JSON) ready for visualization.

# Debrief: Network Data Flaws

## Critiquing the Computational Relationship

- **Discussion**: Look at your Network JSON output.
  - **Ambiguity**: Did the AI define the `Relationship_Type` clearly enough? (e.g., Is "Worked with" a strong or weak edge?)
  - **Computational Bias**: Did the AI's internal knowledge bias its interpretation of the relationship when it wasn't explicit in the source text?
- **Key Point**: **Representing** relationships computationally is the most challenging primitive, as it requires the highest level of interpretation from the AI.

# Activity 2: The Network Visualization App (50 Min)

## Table Activity: Illustrating the Structure

- **Task**: Generate a visualization app to display the network JSON created in Activity 1.
- **Procedure**:
  1. **Define Visualization Prompt**: Use Vibe Coding to generate a **single-file HTML app** that includes **a text input area for pasting Network JSON data** (the output from Activity 1). The prompt must request the use of a graphing library to render a force-directed network graph when a button is clicked.
  2. **Execute**: Paste the JSON output from the Network Extractor (Activity 1) into the Visualization App's input field, and view the graph in the preview window.
  3. **Analyze**: Inspect the resulting network graph. Which nodes are most central (highest influence)? Which nodes are poorly connected?
- **Goal**: Connect the **Illustrating** primitive (the graph) back to the **Comparison** primitive (analyzing which relationships are most frequent).

# Debrief: Visualization as Argument

## Reading the Network Graph

- **Observation**: The visualization is an argument. The placement, size, and clustering of nodes are not objective; they are determined by the visualization algorithm (which the AI chose).
- **Critical Question**: Did the graph reveal something about the data that you could not see in the JSON text? (e.g., two historical figures you didn't realize were central to a military action).
- **Measurement**: There are precisely defined measures of degree centrality, clusters (communities) and other network properties we discussed in this class. One modification of the Network Visualization App might be to have it calculate these measures and output one or more CSV files.
- **Final Primitive**: This activity concludes the cycle of scholarly primitives—from **Discovering** (Wk 01) to **Illustrating** (Wk 10).

# Any questions?
