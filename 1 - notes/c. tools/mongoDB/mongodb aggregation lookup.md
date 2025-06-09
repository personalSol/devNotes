---
status: newBorn
related-links: 
created: 2025-06-06T19:15
updated: 2025-06-06T19:15
---
---

### `$lookup` in Aggregation

- `$lookup` is a stage in the aggregation pipeline used to **join** documents from another collection.
- `$lookup` adds a **new field** to each document in the pipeline.
- That new field is an **array** (not just the name).
	- it's an array of just one object that's why we use 0th index
- The **field name** is what you specify with `as`.

#### Syntax: + example

```js
{
  $lookup: {
    from: "users",              // collection to join
    localField: "userId",       // field in current collection
    foreignField: "_id",        // field in the foreign collection
    as: "userDetails"           // output array field name
  }
}
```

#### result

```js
{
  _id: 1,
  userId: ObjectId("abc123"),
  userDetails: [                      // 👈 this is the output array field
    {
      _id: ObjectId("abc123"),
      name: "Alice"
    }
  ]
}
```

This joins each document with matching documents from the `users` collection.

