---
status: newBorn
related-links: 
created: 2025-06-27T09:50
updated: 2025-06-27T09:50
---
---

```js
class ApiResponse {
    constructor(statusCode, data , message="Success"){
        this.statusCode = statusCode;
        this.data = data;
        this.message = message;
        this.success = statusCode < 400;
    }
} 

export {ApiResponse};
```

