---
status: newBorn
related-links: 
created: 2025-06-10T16:49
updated: 2025-06-11T07:42
---
---

- used to decode a jwt token, but it only decodes and not actually really verify it
- if the string can't be decoded then it gives false, but if you attach correct header and mess up with payload then it knows the algorithm to decode but the decoded value isn't json so it throws an error

|Method|Token Validity|Signature Verified?|Throws Error?|
|---|---|---|---|
|`jwt.decode`|Any|❌ No|✅ If payload is not valid JSON|
|`jwt.verify`|Must be valid|✅ Yes|✅ If token invalid or signature fails|