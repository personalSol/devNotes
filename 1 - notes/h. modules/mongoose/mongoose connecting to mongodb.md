---
status: newBorn
related-links:
  - "[[Mongoose-MOC]]"
  - "[[MongoDB-MOC]]"
created: 2025-05-21T08:26
updated: 2025-05-30T21:33
---
---

> remember:: mongoose.connect returns a promise so we can use .then and .catch with it.  
#### ways
- now there are two methods to connect with database
	- one is to keep all the code including database connection code in `index.js/server.js`
		- in this method we use iife and immediately run method
	- 2nd is a more modular and better approach which is creating a separate db folder and importing the logic from there
		- in this we first have to import that function from other file
		- same that connection file in db folder
		- for basic reference [[mongoose flow#2 Connect to MongoDB config db js]]

- use async await because connecting to database takes time
	- will return a promise which will allow us to use .then and .catch
- use try catch because there is always some chance for error
- for first method we use `;(` semicolon is added to make sure all the previous lines are ended and they will not interfear with iife. It's a pro practice
- we write db name so that it will `use database` like in [[mongosh commands#^0kdifw]] command where it use database if exist or create if doesn't
- if we don't give then it by default uses test database
- to check if the connected database and server can talk to each other, we add an event lister


#### code to connect for method 1
```js
import mongoose from "mongoose";

;(
	async ()=>{
		try{
			// etc etc
		} catch(error){
			// etc etc
		}
	}
)()
```

#### method 2

```js
import mongoose from 'mongoose';
import express from 'express';
import { DB_NAME } from '../constants.js';
import dotenv from 'dotenv';

dotenv.config();

const app = express();

const connectDB = async () => {
    try {
        const connectionInstance = await mongoose.connect(
            `${process.env.MONGODB_URI}/${DB_NAME}`
        );

        console.log(`MongoDB connected!! Host: ${connectionInstance.connection.host}`);

        app.on('error', (err) => {
            console.log(`Facing issue: ${err}`);
        });
    } catch (error) {
        console.log(`MONGODB connection failed: ${error}`);
        process.exit(1);
    }
};

export default connectDB;
```
