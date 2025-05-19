---
status: newBorn
related-links: 
created: 2025-05-18T15:31
updated: 2025-05-18T16:18
---
---

- to give reference in schema of other model
	- we pass the name we game as first argument inside `mongoose.model("THIS ONE", 2nd argument)`
	- we give reference by setting the type as 
``` js
createdBy: {
            type: mongoose.Schema.Types.ObjectId,
            ref: "User"
        }
```
- little explaination
	- remerber that here, we are first declaring that the value we are giving is one of the types of values on out schema which is ObjectId which gets generated automatically
	- and the name we give is what we entered inside model
- remember in model, try to have the export variable name and the name inside mongoose.model be same