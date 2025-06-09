---
status: newBorn
related-links: 
created: 2025-05-31T22:35
updated: 2025-05-31T22:35
---
---

|Feature|`bcrypt`|`JWT`|
|---|---|---|
|Purpose|Hash passwords (one-way)|Create signed tokens for authentication|
|Output|Irreversible hash|Base64-encoded token with a signature|
|Use case|Storing & checking passwords|Verifying user identity across requests|
|Uses secret?|❌ No|✅ Yes, used for signature|

