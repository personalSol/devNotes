---
status: newBorn
related-links:
  - "[[npm packages for web dev]]"
  - "[[Node-JS-MOC]]"
  - "[[authentication]]"
created: 2025-05-29T20:31
updated: 2025-06-01T15:15
---
---

**bcrypt** is a native C++ binding for Node.js, while **bcrypt.js** is a pure JavaScript implementation.

- **bcrypt**: Faster, requires compilation/build tools.
- **bcrypt.js**: Slower, but works everywhere (no native dependencies).


used for:
- hashing passwords
	- during sign up and login

methods
- bcrypt.hash() - hashes your password
- bcrypt.compare() - compares two things or passwords specifically

![[authentication sign in or login]]