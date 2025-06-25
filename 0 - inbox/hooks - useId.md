---
status: newBorn
related-links: 
created: 2025-06-24T16:09
updated: 2025-06-24T16:09
---
---

- use to generate random id which can be use.
- shouldn't be use to generate keys

```js
import React, { useId } from 'react'
const id = useId() // now this generated a unique id which we can use anywhere
```