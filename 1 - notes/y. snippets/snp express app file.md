---
status: newBorn
related-links: 
created: 2025-06-27T10:01
updated: 2025-06-27T10:01
---
---

```js
import express from 'express';
import cors from "cors";
import cookieParser from 'cookie-parser';

const app = express();


app.use(cors({
    origin: process.env.CORS_ORIGIN,
    credentials: true
}))

app.use(express.json({limit: '16kb'}));
app.use(express.static('public'))
app.use(express.urlencoded({extended: true, limit: '16kb'}))
app.use(cookieParser());

// routes import
import userRoutes from './routes/user.router.js'


// routes declaration
app.use('/api/v1/users', userRoutes)

export {app}
```

