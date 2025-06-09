---
created: 2025-06-07T11:56:16
status: 
source: 
updated: 2025-06-09T09:04
---
---

in our LLM Model, we know that it takens tokens and then generate more tokens.

thing is free models use limited amout of tokens per output and paid ones charge on basis of how much tokens are used.

`token spend = token of (context provided ( of previous chat or anything )) + token of (prompt) + token of(output)`

now we have to save tokens as much as possible to decrease our cost. For that we can use some methods:

- trying to give selected part of context, like from start or end or from specific place
- or by giving summary of the previous context

in both cases, there is a chance that we miss important information context needed to generate the desired output. 

![[Pasted image 20250607120329.png||450]]

### when we want out llm model to remember the core instructions

- basically means to remember what it is supposed to do or answer around. 
- like a zomato/swiggy bot is supposed to only work around customer query.
- there was a risk that if customer prompted that forget all the previous instructions then model use to forget the core instruction and objective it was supposed to answer around and then ended up being misused by users to run and do other things for free
- to solve this, we don't write the core instruction in `contents` anymore and we write them in `config`.

> link: [Text generation  \|  Gemini API  \|  Google AI for Developers](https://ai.google.dev/gemini-api/docs/text-generation#system-instructions)