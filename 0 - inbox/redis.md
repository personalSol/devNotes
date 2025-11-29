---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-11-29T18:55
---
---

Data is stored in RAM, not on disk — which makes it extremely fast.  
  
💾 Disk-Based Databases (MongoDB / PostgreSQL):  
These read from disk, so they’re slower compared to memory.  
  
⚡ Frequently Accessed Data:  
Data that doesn’t change often but is requested constantly  
(e.g., product lists, dashboard stats, sessions).  
  
🎯 Cache Hit:  
The data is found in Redis → instant response → no database needed.  
  
❌ Cache Miss:  
Data is not found in Redis → server goes to the real database → fetches → returns → then stores a copy in Redis.  
  
🔑 Key–Value Store:  
Redis stores data like:  
key → value  
Simple, fast lookups.  
  
🚀 Why Redis?  
Less load on your main database.  
Faster API responses.  
Used in almost every production-grade app.

