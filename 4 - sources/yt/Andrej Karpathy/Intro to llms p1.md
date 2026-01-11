---
created: 2026-01-11T09:48:51
status:
source:
updated: 2026-01-11T13:21
---
---

in this video andrej told us about llms and parameters. 


### what llm contains

- each llm contains basically 2 files
	- parameters file ( the main llm file which have all the knowledge in parameters). It can be a 7 billion parameter file or 70 or 100
		- each parameter in this is a float type and hence take 2 byte of storage.
	- we can say these parameters are kind of gistalt version of that data 
	- run C file which is used to run this model parameters. It doesn't have any dependency file or anything

### how llm generates

- basically in this he told us that parameters save data but the amount of data it saves and what data is saves is unknown
- when a model gives output it is basically generating text or we can say dreaming text. The outputs that it gives contains both facts and halucinations. Which part is halucination and which is fact is something we have no way of knowing. 

![[Pasted image 20260111105313.png]]

### to train an llm

- initally to a model one needs:
	- a large amout of data 
	- a lot of gpus
	- time to run this data though these gpu ( with certain algorithm ig )
- example is llama 70 billion parameter model was trained on 6000 gpus for 12 days and costed about $2 million

### a little on what is inside these llms and how they work

- these llms have netural networks and how these neural networks work is something we still dont know
- they also store data but we need to be asking in certain way to get the data
- ex: if you ask who is tom cruis's mother then it will give name of the mother but if you ask who is the son of `mother name here` then it will say idk
- `what the model produce after giving input is what we call inference or output`

![[Pasted image 20260111105235.png]]

### stages of training an llm


![[Pasted image 20260111105357.png]]
- first is the training which is described above
- second is finetuning
	- why finetuning is needed?
		- rn model is just trained but we don't know how and what output will it give.
		- like it can give answer in an internet document format or even ask questions
		- but what we need is answer in Q&A format and to achieve this we finetune the model
	- how to finetune?
		- to finetune a model we need to feed it with a lot of Q&A type documents
		- it can be roughly 100k documents
		- so a user asks a question and we hire human who creates answer (possibly on the basis of inference given by llm) and hence we get an optimal answer
		- by feeding this converstional type documents to llm we make it realise how it needs to converse with user
- here is also a third stage of this process which is called rlhf 
	- in rlhf or reinforcement learning with human feedback, we get two outputs of the same question for llm and select which one is better
	- this helps model/llm further improve their answers in the next run.
	- in chatgpt in start or even sometimes today we know for the same question it generates two outputs and ask to choose the better one which further helps it improve


### iterations of these stages

- training a model costs a lot so it's basically done once every year or after many months
- finetuning a model is relatively cheap and hence it is mostly done once per week or even daily

### how to rank model

- for model ranking there are websites like chatbot arena or lmaena where we each mdoel is give an elo
- the elo is decided by making two models fight
- simple way of that is in this site user asks a question and gets two answers in return
	- user has to select the better answer without knowing which answer is from which ai
	- the llm with better answer gets selected and their rating increase while other ones decrease 


![[Pasted image 20260111131545.png]]

- he says that at that moment there was only ai that thinks of the next word and not any llm which takes time like 30 mints and then give an even better answer. 

![[Pasted image 20260111131924.png]]

![[Pasted image 20260111132003.png]]


- we have seen that to play alpha go deepmind team created an ai which firstly was imitating the best players but then they defined a reward system which was to win the game and made ai compete with each other and learn over time which created a model which doesnt imitate the best player but is better than that plater. 