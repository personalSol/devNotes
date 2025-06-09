---
status: newBorn
related-links: 
created: 2025-06-06T18:15
updated: 2025-06-06T18:15
---
---

here I explained the subscription model of mongoose

```js
import mongoose from "mongoose";

const subscriptionSchema = new mongoose.Schema({
    subscriber: {
        type: mongoose.Schema.Types.ObjectId, // the one who is subscribing
        ref: "User"
    },
    channel: {
        type: mongoose.Schema.Types.ObjectId, // the one who subscriber is subscribing to
        ref: "User"
    }
}, {timestamps: true})

export const Subscription = mongoose.model("Subscription", subscriptionSchema)
```


![[Recording 20250606181826.m4a]]

![[Recording 20250606181921.m4a]]

![[Recording 20250606182000.m4a]]
