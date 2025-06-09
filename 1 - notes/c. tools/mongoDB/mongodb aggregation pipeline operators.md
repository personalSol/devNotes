---
status: newBorn
related-links: 
created: 2025-06-06T20:53
updated: 2025-06-06T20:53
---
---

### 🔁 Core Pipeline Stages

- `$match` – Filter documents (like WHERE).
- `$project` – Select/modify fields. 
	- limits the number of fields we need to get
- `$group` – Group by a field and use aggregations.
- `$sort` – Sort documents.
- `$limit` – Limit number of docs.
- `$skip` – Skip number of docs.
- `$lookup` – Join with another collection -- [[mongodb aggregation lookup]]
- `$unwind` – Break array into individual docs.
- `$addFields` / `$set` – Add or update fields.

### 🧮 Core Accumulators (inside `$group`)

- `$sum` – Total.
- `$avg` – Average.
- `$min` / `$max` – Min/Max.
- `$first` / `$last` – First/Last in group.
- `$push` – Create array of values.
- `$addToSet` – Array of unique values.

### 🔧 Core Expressions

- `$cond` – If-else condition.
- `$eq`, `$gt`, `$lt`, `$ne`, `$in` – Comparisons & checks.
	- `$in` – Checks if a value exists in an array or object.
		- Example: `{ "$in": [ "apple", ["apple", "banana", "cherry"] ] } // true`
- `$and`, `$or`, `$not` – Boolean logic.
- `$concat` – Combine strings.
- `$toInt`, `$toString`, `$toDate` – Type conversions.
- `$size` – Length of an array.
- `$arrayElemAt` – Get item at index.
- `$map` / `$filter` – Work with array elements.
