---
status: newBorn
related-links: 
created: 2025-06-24T10:39
updated: 2025-07-17T15:46
---
---

### Redux Overview

- **Redux** is a JavaScript library for managing state in **any JS app** (not just React).
- Works with other frameworks like **Vue, Angular**, etc.
- For React, there’s a separate integration: **React Redux**.

### Background

- **Flux** (by Facebook) was the earlier solution for state management.
- **Redux** was introduced in **2015** as a simpler alternative.

### Core Principles

- State should never be modified directly.
- All state updates must happen through pure functions called reducers.

### Modern Update

- [[redux toolkit]] was introduced as the official, recommended way to write Redux logic, reducing boilerplate and simplifying setup.
- [[react redux]] is still used today—it’s the bridge between Redux and React.
- Redux Toolkit works _with_ React Redux—it doesn’t replace it but improves how Redux is written and used in React apps.
- **Redux Toolkit didn’t replace React Redux.**  
	- It replaced the _old manual Redux patterns_ (like creating separate action files, types, and reducers from scratch).  
	- React Redux is still the official connector library between React and Redux. Redux Toolkit just made writing Redux code easier and more efficient.
	- ab redux aaya tha to uske stepup me thoda jayada time lagta tha compare to contex api and debugging karne me v problem ja rhi thi. tab developers ne redux-toolkit introduce kiya jisme setUp or debugging easy ho gya kuchh redux functions ke dawara, isliye redux use karne ke liye ye dono libraries install karni jaruri hai.