---
status: newBorn
related-links: 
created: 2025-06-06T18:53
updated: 2025-06-06T20:53
---
---

> docs link: [Aggregation Operations - Database Manual - MongoDB Docs](https://www.mongodb.com/docs/manual/aggregation/)

- [[mongodb aggregation pipelines intro]]
- [[mongodb aggregation pipeline operators]]

- 

in mongodb, we can use aggregation in mongosh by following commands:

```js
database.<collection>.aggregate( [

   // Stage 1: Filter pizza order documents by pizza size
   {
      $match: { size: "medium" }
   },

   // Stage 2: Group remaining documents by pizza name and calculate total quantity
   {
      $group: { _id: "$name", totalQuantity: { $sum: "$quantity" } }
   }

] )
```

