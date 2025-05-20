---
status: newBorn
related-links: 
created: 2025-05-20T10:17
updated: 2025-05-20T11:22
---
---

- used because even if you have Prettier in VS Code, someone else might not
- to keep formatting consistent across the team, we install Prettier as a dev dependency
- create a `.prettierrc` file in the root (or `src/`) folder
    - write configurations inside it
    - format: JSON
- common properties:
    - `"singleQuote": true` → uses `'` instead of `"`
    - `"semi": false` → removes semicolons at line ends
    - `"tabWidth": 2` → sets tab spacing to 2 spaces
    - `"trailingComma": "es5"` → adds commas where valid in ES5 (e.g., objects, arrays)
    - `"printWidth": 80` → wraps lines that exceed 80 characters
    - `"arrowParens": "avoid"` → omits parens when there's a single function parameter
    - `"bracketSpacing": true` → adds spaces inside object literals → `{ foo: bar }`
- run Prettier from CLI:
    - `npx prettier . --write` → formats all files in the current directory recursively
- use `.prettierignore` to exclude files/folders from formatting
    - similar to `.gitignore`
    - example entries:
```ngnix
node_modules  
dist  
build  
*.min.js  
```

