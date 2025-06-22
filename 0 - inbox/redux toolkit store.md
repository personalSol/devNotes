---
status: newBorn
related-links: 
created: 2025-06-21T00:19
updated: 2025-06-21T02:17
---
---

- used to store all the reducers in one place so that store have all the reducers react to be accessed
- single source of truth
- it has configureStore
- introduce reducer

#### syntax

```js
import { configureStore } from '@reduxjs/toolkit'
import todoReducer from '../features/todo/todoSlice'

export const store = configureStore({
    reducer: todoReducer
});
```

- here we created configurations of store reducers
- so we imported and then saved it