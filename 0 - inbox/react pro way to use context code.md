---
status: newBorn
related-links: 
created: 2025-06-17T14:40
updated: 2025-06-17T14:40
---
---

```js
import { createContext, useContext, useState } from "react";

export const ThemeContext = createContext({
    themeMode: 'Light',
    darkTheme: ()=> {},
    lightTheme: ()=> {}
});

export const ThemeProvider = ThemeContext.Provider

export const useTheme = () => {
    return useContext(ThemeContext)
}
```

- in this we have done three things
	- one is created context + set initial values in it
	- two we created the Context Provider
	- three we combined the context with useContext hook so that we don't have to import both of them again
- we didn't do three things in this
	- one thing is set state management for the values like in out case `themeMode` 
	- also we didn't define what the function does
	- third is we didn't give Provider the data that it needs to pass on to it's child components
- so these tasks need to be done on the same file in which we will use wrapper provider ( `ThemeProvider`) 
like:

```jsx

```

