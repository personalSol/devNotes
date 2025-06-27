---
status: newBorn
related-links: 
created: 2025-06-27T09:53
updated: 2025-06-27T09:53
---
---

```js
class ApiError extends Error {
    constructor(
        statusCode,
        message= "Something went wrong",
        errors = [],
        stack = ""
    ){
        super(message)
        this.statusCode = statusCode
        this.message = message
        this.success = false;
        this.errors = errors
        if (stack) {
            this.stack = stack
        } else{
            Error.captureStackTrace(this, this.constructor)
        }
    }
} 

export {ApiError}
```

