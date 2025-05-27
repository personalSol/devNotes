---
status: newBorn
related-links: 
created: 2025-05-28T02:45
updated: 2025-05-28T03:07
---
---

Node.js provides several **global objects** that are always available in any module without needing to `require()` them.

here is a list:
- 
- 


Global objects in Node.js are variables and functions accessible anywhere in your application without importing.

Global objects are higher-level constructs that contain properties, methods, and functionality, while variables typically just store single values. For example, the `process` global object is like a container with many properties (`env`, `argv`, etc.) and methods (`exit()`, `cwd()`), making it more complex than a simple variable.

Key examples:

- `process`: [[node - global object - process]]
- `console`: Logging functionality
- `global`: Node.js equivalent of browser's `window` object
- `__dirname`: Current directory path
- `__filename`: Current file path
- `require()`: Function to import modules
- `module`: Reference to current module
- `exports`: Shorthand for `module.exports`
- `Buffer`: For handling binary data
- `setTimeout/setInterval`: Timing functions