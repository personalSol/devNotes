---
created: 2025-05-24T16:42:23
status: 
source: 
updated: 2025-05-24T17:39
---
---

![[Websites and Resources#^8cqevc]]

### Gen AI

- Unlike general databases where each input have a fixed currosponding output stored.
- gen ai is a model which tries to guess the next word from the prompt we give
- tries to find the pattern in input and generate next value
- it's not deterministic
- it can generate answer even for a question it has never seen before 

### technical process

- after receiving the prompt from user, ai converts the prompt into individual token ( the process of creating token depends on model used )
	- why tokanization: because machine doesn't understand english
		- it can understand tokens and find patterns to give answer
- those tokanized values are then recieved by the ai and then Ai try to generate the next token
- after reaching a token number that feels satisfatory by AI
- it returns the output to the user


### AI Models

GPT is Generative Pre-Trained Transformer.

- these models are trained with a set of data
- this trained model then becomes expert at finding patterns
- using the pattern it generates an output
- also called transformer because it transforms the data ( ex: converting text to image, video etc )
- not deterterministic: means for the same input it can give different outputs
	- because it's finding a pattern
	- each pattern is slightly or completely different from the previous one
	- hence different outputs 
