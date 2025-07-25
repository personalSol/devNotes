---
status: newBorn
related-links: 
created: 2025-07-25T00:05
updated: 2025-07-25T00:05
---
---

- default export allows you to export directly and import it with any name
	- reason is that express assumes that the thing that is going to be exported without destructure must be important and so it has default export set and so i should just import the default
- second is named export which allows us to export multiple things
	- they must always be imported in destructure format

```js
// 📁 math.mjs

// 🔹 Named export (must be imported using { square })
export const square = (x) => x * x;

// 🔹 Another named export
export function cube(x) {
  return x * x * x;
}

// 🔹 Default export (can be imported without curly braces)
export default function greet() {
  console.log("Welcome to math module!");
}


// 📁 main.mjs

// ✅ Importing default export (no curly braces)
import greet from './math.mjs';

// ✅ Importing named exports (must use curly braces)
import { square, cube } from './math.mjs';

greet();              // Output: Welcome to math module!
console.log(square(3)); // Output: 9
console.log(cube(2));   // Output: 8

// ❌ Wrong: trying to import a named export as default
// import square from './math.mjs'; // ❌ Error: square is not the default export

// ✅ You can also rename named exports
import { square as sq } from './math.mjs';
console.log(sq(5)); // Output: 25
```

