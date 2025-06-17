---
status: newBorn
related-links: 
created: 2025-06-16T15:36
updated: 2025-06-16T15:36
---
---


# Why Not Use Plain Global Files in React Instead of Context?

When building React apps, you might wonder:

> Why not just create a global JavaScript file with variables and import them wherever we want, instead of using `createContext`?

Let's explore why this doesn't work as expected in React.

---

## 🚫 Why a Plain Global File Doesn't Work Well in React

### If you do this:

```js
// globals.js
export let user = null;
```

### When you import user in a React component:

```js
import { user } from './globals';
```

✅ You **will get the value of `user` when the component first loads.**  
❌ BUT: If `user` changes later, **React will not know it needs to re-render.**

Because React tracks changes via **state, props, and context — NOT via plain variables.**

---

## 🎯 Key Reason:

🛑 **Global variables don't trigger React re-renders.**

React re-renders when:

- Component state changes (`useState`)
    
- Context value changes (`useContext`)
    
- Props change
    

When you update a plain global variable:

```js
user = 'newUser';
```

👉 React has **no idea that something changed.**  
👉 Components won’t automatically update.

---

## ✅ Why `createContext` is Needed

When you use `createContext` + `useContext` + `Provider`:

- React tracks that value.
    
- When the context value changes, **all components consuming it will automatically re-render.**
    

This makes it:

- Reactive
    
- Reliable
    
- Scoped properly inside React’s system
    

---

## ⚙️ Example Difference

### ❌ Global Variable (Won't Re-render)

```js
// global.js
export let user = null;

// Component
import { user } from './global';

console.log(user); // It won't update in the UI when 'user' changes elsewhere.
```

### ✅ Context (Will Re-render)

```jsx
// AuthContext.js
import { createContext, useContext, useState } from 'react';

const AuthContext = createContext();

export const AuthProvider = ({ children }) => {
    const [user, setUser] = useState(null);
    return (
        <AuthContext.Provider value={{ user, setUser }}>
            {children}
        </AuthContext.Provider>
    );
};

export const useAuth = () => useContext(AuthContext);

// Component
import { useAuth } from './AuthContext';

const Profile = () => {
    const { user } = useAuth();
    return <div>{user}</div>; // Will update automatically when 'user' changes.
}
```

---

## ✅ Summary

|Method|Reactive?|Should You Use?|
|---|---|---|
|Global File|❌ No|🚫 Bad idea|
|React Context|✅ Yes|✅ Best practice|

👉 **Global files are static — React won't track changes.**  
👉 **Context keeps React in control — triggers updates automatically.**
