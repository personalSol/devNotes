---
status: newBorn
related-links: 
created: 2025-06-11T06:19
updated: 2025-06-11T06:19
---
---

### IndexedDB: The Powerful One

A SQL-based DB system that’s meant for **storing larger amounts of structured data.**

 ✅ Perfect for:
- Large datasets
- Offline apps
- File/blob storage
- Complex data structures

❌ Avoid for:
- Simple key-value pairs
- Small amounts of data
- Anything that local storage/cookies could handle

``` javascript
let db; 
// Opening or creating our database with a name and an ID 
// We call this request because we're "requesting" this database
const request = window.indexedDB.open("coolDatabase", 1) 

request.onerror = (event) => { 
  // Do something with request.error 
  console.error("Why didn't you allow my web app to use IndexedDB?"); }; 

request.onsuccess = (event) => { 
  // Do something with request.result 
  db = event.target.result 
};
```

