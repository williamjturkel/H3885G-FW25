# Wk 11. Semantic Search and Clustering

Standard keyword searches often miss the "meaning" behind the text; today we leverage semantic search to find conceptually related documents. We will use AI clustering to group our archive into thematic nodes, revealing hidden structures in the historical record. **Scholarly Primitive: Discovery** (Finding non-obvious patterns). We use Vibe Coding to build tools that discover meaning based on _context_ (embeddings), not _keywords_.

# Beyond Keywords: Semantic Embeddings

## The Computational Meaning

- **Keyword Search**: Finds documents containing the exact word "Tet." Ignores documents discussing "Lunar New Year attacks." (Fails to capture meaning).
- **Semantic Embeddings**: A high-dimensional vector that represents the _meaning_ or _context_ of a word or sentence. Documents with similar meanings are numerically close together.
- **Discovery Primitive**: We use the LLM to calculate semantic similarity, allowing us to find documents that are _conceptually_ related, even if they use different vocabulary.

# Activity 1: The Semantic Scorer App (40 Min)

## Table Activity: Quantifying Context

- **Task**: Generate an app that uses the LLM to score the contextual similarity between a user query and two document samples.
- **Procedure**:
  1. **Define Schema**: The schema must output three fields: `Similarity_Score_A` (0-10), `Similarity_Score_B` (0-10), and `Semantic_Category` (A short classification).
  2. **Write Master Prompt**: Use Vibe Coding to generate a single-file HTML app with three text inputs (Query, Document A, Document B) and a button. The prompt must instruct the app to:
     - Compare the **semantic meaning** of the Query to Document A and Document B.
     - Output the score and category in a strict JSON object.
  3. **Test**: Run the app on the three documents below. Does the scoring align with your intuition?
     - Query from CIA, ["North Vietnamese Military Potential for Fighting in South Vietnam"](https://www.cia.gov/readingroom/document/0001166476) (June 4, 1966): "CONCLUSIONS A. We estimate the present strength of the North Vietnamese Armed Forces to be slightly over 400,000 with about 375,000 of these in the army. North Vietnam has sufficient manpower to provide a total military force of over 500,000 men without serious strain. B. The total Communist force in South Vietnam is estimated at between 260,000 and 280,000. The major combat elements include some 38,000 North Vietnamese troops, approximately 63,000 VC regular main and local forces, and about 100,000 to 120,000 guerrillas. C. North Vietnam is estimated to have a current annual capability to train 75,000 to 100,000 individual replacements for infiltration. By making a maximum effort, this total might be doubled. From these, North Vietnam could organize some 24 to 36 infantry regiments per year. D. There is considerable margin for error in estimating total Communist losses. Nevertheless, we believe these losses are mounting rapidly. The loss rate has already begun to strain the replacement capability of the VC in South Vietnam, but it appears that current total Communist losses could be replaced, if necessary, from within South Vietnam. E. We estimate that the VC could recruit and train 7,000 to 10,000 men per month. The replacement of cadre, however, is probably a problem and is almost certain to become more difficult in the future. By the end of 1967, the loss rate may exceed the estimated capability of the VC to recruit replacements from within South Vietnam, especially if the rate of combat increases. In such case, the Communists might be forced either to scale down their plans for expansion or to step up the rate of infiltration from North Vietnam."
     - Document A from [Summary of Secretary of Defense Robert S. McNamara’s Memo to President Johnson, July 20, 1965](https://www.vassar.edu/the-wars-for-vietnam/documents/summary-secretary-defense-robert-s-mcnamaras-memo-president-johnson): "Secretary McNamara’s 20 July 1965 Memorandum for the President [Doc. 261] spelled out the troop requirements for Vietnam as follows: The forces for 1965 should be brought up to about 175,000, and 'It should be understood that the deployment of more men (perhaps 100,000) may be necessary in early 1966, and the deployment of additional forces thereafter is possible but will depend on developments.' This 100,000-man possible addition was broken down in a cable from COMUSMACV to CINCPAC as providing 27 maneuver battalions with associated battalions to 61 sometime in 1966. The question arises as to how this 100,000-man 27-battalion figure was reached. In the absence of documentary evidence, it seems simplest to assume that Westmoreland was given pretty much what he asked for. However, the 61-battalion figure comes very close to the number of battalions the Secretary of Defense was thinking about earlier in July, when a memorandum for the record dated 12 July shows a proposal to strengthen U.S. forces by 63 battalions through a combination of calling up reserves, extending tours of duty, and increasing the draft. In fact, the 63 battalion figure appears again in the Secretary’s 20 July memorandum to the President, allowing one to speculate that the size of the build-up had already been fixed in early July prior to the trip. In either case, the result was that Phase II was recommended to the President at a level of roughly 100,000 which when added to the then-current estimates for Phase I of 175,000 gave a total estimate of 275,000 by the end of 1966."
     - Document B from Natalie Swindle, [Interview with David E. Adcock](https://vva.vietnam.ttu.edu/repositories/2/digital_objects/432160) (Feb 3, 2009): "DA: Yeah. I don’t know how much time had passed. You kind of lose track of time. But they had begun to bring in resupply helicopters and medevac helicopters back to the rear of where I was located. Of course, they set up the mortar back there and I started trying to call in mortar fire. But one of my friends, a guy named Michaelvitch was an M-60, had an M-60 machinegun. He had fired that gun so much that they had melted the barrel on it and so they had ordered another barrel and it came in on a helicopter to our rear. He and his ammo bearer ran back there to get the extra barrel and to get the ammo. The VC dropped some mortars in back there where the helicopters were coming in and out. He got hit by one of those mortars rounds and never came back. I talked to him years and years later and he said it was a pretty close call, it had come real close to getting him. That’s just another thing that leads to what I was talking about, about the total chaos. You don’t know where the enemy is, really, you don’t know how much more is fixing to happen so it was a very tense situation. We were able to medevac out all the guys that had gotten hit pretty quick. I know we had a photographer with us from one of the major news agencies and it seemed like that any time we had a photographer with us we would always make contact. It was like they knew something"
- **Goal**: Create a measurable, objective score for subjective semantic relationships.

# Debrief: Prompting for Context

## Critiquing the Semantic Score

- **Discussion**: Does the LLM need explicit instruction on _what kind_ of similarity to score? (e.g., Should it score political similarity or temporal similarity?)
- **Core Takeaway**: To achieve true semantic discovery, the **System Instruction** must define the dimension of comparison (e.g., "Score based only on the thematic relevance to supply chain logistics").

# Activity 2: The Data Clustering App (50 Min)

## Table Activity: Illustrating Hidden Communities

- **Task**: Generate an app that visualizes patterns of similarity in structured data (Clustering).
- **Procedure**:
  1. **Define Visualization Prompt**: Use Vibe Coding to generate a **single-file HTML app** that includes a text input area for pasting combined A02/A03 JSON data.
  2. The app must generate a **2D Scatter Plot** (using D3.js or similar) that plots each document based on two quantitative variables (e.g., **Sentiment Score** on the X-axis and **Propaganda Intensity Score** on the Y-axis).
  3. **Analyze**: Run the app. Do the documents naturally cluster into groups (e.g., a "high sentiment, low propaganda" community)?
- **Goal**: Use the **Illustrating** primitive to visually expose **Discovery** patterns that would be very difficult to find manually. This tool is a strong candidate for the A04 final visualization.

# Assignment 04 Overview

[Assignment Page](<../A04>)

# Any questions?
