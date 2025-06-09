---
status: newBorn
related-links: 
created: 2025-06-06T19:14
updated: 2025-06-06T19:14
---
---

**Aggregation** is the process of processing data records and returning a combined result. It is used for:

- Filtering
- Grouping
- Sorting
- Transforming
- Joining (with `$lookup`)
- Calculating values (like totals, averages)

Aggregation is performed using an **Aggregation Pipeline** – a sequence of stages through which data is passed.

---

### Is Aggregation Filtering or Combining?

Aggregation can **do both**:

```js
[
  { $match: { age: { $gt: 18 } } },         // filtering
  { $group: { _id: "$city", total: { $sum: 1 } } }  // combining (grouping)
]
```


