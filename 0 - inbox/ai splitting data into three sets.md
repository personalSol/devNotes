---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-11-09T12:08
---
---

- 3 sets: in three sets, a data is divided into three sets/parts.
	- one part is kept for training the model
	- second part is kept for validation of model and find tuning
	- third part is for real testing after the model is trained and this data is used to compare different models
	- one problem that can occur mistakenly is we provide the third/final set data during tuning and training. This will make the model perform well on final set because it has already seen the data but that doesn't always mean the model is trained well
		- we want to avoid them becoming memorization machines


![[terms for AI#^tdpez8]]

Conclusion: we divide the data intro three sets of 70% 15% and 15%. the first set is used to train the model. After training we validate the model using second test and fine tune it accordingly. Finally once the model is trained, we test the model on third set as well as other models to check which model is most accurate. One thing to make sure is the three sets stay separate and only come in contact with model during their particular phrase so the model will not become a memorization machine and just memorize outputs for a particular set and be stupid for other/new data.

![[Pasted image 20251109120235.png||500]]

