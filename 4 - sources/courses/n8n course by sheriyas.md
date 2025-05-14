---
created: 2025-05-13T07:47:04
status: 
source: 
updated: 2025-05-14T10:47
---
---

**What Are AI Agents?**  
Software entities that perceive environments, make decisions, and act autonomously.

**Types of AI Agents**

- Model-based
- Goal-based
- Utility-based
- Learning

**Evolution**  
From rule-based automation to intelligent systems with contextual understanding.

**Use Cases**  
Customer service and business process automation—driving real-world impact.



### In n8n


#### inside ai-agent
- system message are like side instructions that we give to ai model which are fixed every time

maximum number of tokens
- the **"Maximum number of tokens"** refers to the **maximum amount of text** (both input and output combined) that the AI model can handle in a single request.
- A **token** is a chunk of text — typically:
	- **1 token ≈ 4 characters of English text**
	- Or roughly **0.75 words**
- If your limit is **1000 tokens**, and your input is **300 tokens**, the model can only generate **up to 700 tokens** in response.
- **Setting it too low**: Output might get cut off mid-sentence.
- **Setting it too high**: Can consume more credits (if you're using a paid API like OpenAI).


Sampling temperature means
- **Sampling temperature** controls how **creative or random** the AI's responses are:
- **0.0–0.3** = Deterministic, focused, reliable (good for facts, code)
- **0.4–0.7** = Balanced, natural (good for general use)
- **0.8–1.0+** = Creative, varied, unpredictable (good for ideas, stories)
Higher = more variety. Lower = more accuracy.
- usually between 0.5 to 0.7

Memory:
- remembers what were the last 10 onput and output. This helps personalize the output because it remembers/keep in mind the last conversations  


# Reference
`related link(if any)`

