---
status: adult
related-links:
  - "[[Core-Concepts-MOC]]"
created: 2025-02-24T22:11
updated: 2025-06-11T06:19
---
---

break down of when to use each one (and when not to).

### Types of Browser Storage

- Web Storage 
	- local - [[web local storage]]
	- session - [[web session storage]]
- Cookies 
- IndexedDB - [[browser storage - indexedDB]]

### Cookies Vs Local Storage 

Cookies and local storage serve different purposes.

Cookies are primarily for **reading server-side**, while local storage can **only be read by the client-side.**



### Quick Storage Size Limits

- LocalStorage: ~5-10MB
- SessionStorage: ~5-10MB
- Cookies: ~4KB
- IndexedDB: Several GB

- Need server access? → Cookies
- Temporary data? → SessionStorage
- Simple client data? → LocalStorage
- Complex/large data? → IndexedDB

### Remember

- Always validate stored data
- Clear sensitive data
- Handle storage errors
- Check available space
- Consider privacy modes

# Reference
`related notes + source + link(if any)`
 
