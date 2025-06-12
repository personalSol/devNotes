---
status: newBorn
related-links:
  - "[[npm packages for web dev]]"
  - "[[Node-JS-MOC]]"
  - "[[auth - main]]"
created: 2025-05-29T20:31
updated: 2025-06-11T20:06
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
- bcrypt.compare() - compares two passwords
- [[bcrypt hash and verification]]


related questions:
- [[auth why bcrypt and not crypto]]

- [[authentication sign in or login]]