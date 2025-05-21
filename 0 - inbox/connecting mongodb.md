---
status: newBorn
related-links: 
created: 2025-05-21T08:26
updated: 2025-05-21T12:29
---
---

#### ways
- now there are two methods to connect with database
	- one is to keep all the code including database connection code in `index.js/server.js`
	- 2nd is a more modular and better approach which is creating a separate db folder and importing the logic from there

#### code to connect
```js



import mongoose from "mongoose";

;(
	async ()=>{
		try{
			
		}
	}
)()
```

- use async await because connecting to database takes time
- use try catch because there is always some chance for error
- `;(` semicolon is added to make sure all the previous lines are ended and they will not interfear with iife. It's a pro practice