---
status: newBorn
related-links: "[[React-MOC]]"
created: 2025-05-02T17:09
updated: 2025-05-23T10:00
---
---

components are of two types:
- functional components
- class components




a good approach for big projects with multiple components:
- instead of separately importing all the components in app.jsx or any other file
- in the components folder itself, create a `components.js` or `index.js` 
	- import all the components in this
	- and then do the object export
- benefit of doing it with index file is index file is called by default even if you just give the directory and not the file itself
```jsx
import InputBox from "./InputBox";

export {InputBox}
```


