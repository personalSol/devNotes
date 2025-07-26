---
status: newBorn
related-links: 
created: 2025-07-26T22:20
updated: 2025-07-26T22:20
---
---

### 🧠 How Context Is Saved in React (Auth State)

React Context is a built-in way to manage global state like authentication. But it's important to understand where and how this state is stored.

---

### ⚙️ 1. Where is React Context State Stored?

- React Context data (like `user`, `isLoggedIn`) is stored **in memory**.
    
- It's lost when the page refreshes.
    
- React just holds the state during the life of the app in the browser tab.
    

```jsx
<AuthContext.Provider value={{ user, login, logout }}>
  {children}
</AuthContext.Provider>
```

---

### 🚫 2. Does Context Persist Across Refreshes?

- ❌ No. Once the browser refreshes, memory is wiped, and the context resets.
    
- You have to reinitialize context state using:
    
    - Data from localStorage or sessionStorage
        
    - Tokens in cookies
        
    - A fetch to the backend (e.g., get user from /me API)
        

---

### 🧩 3. How to Make Context Persistent

You combine context with a **persistent storage** layer.

Example: On app startup, read from `localStorage` and set context.

```jsx
useEffect(() => {
  const storedUser = localStorage.getItem("user");
  if (storedUser) setUser(JSON.parse(storedUser));
}, []);
```

Also, save user on login:

```js
localStorage.setItem("user", JSON.stringify(user));
```

---

### 🛠️ 4. Context vs Redux vs Zustand (Storage Behavior)

|Tool|Storage Location|Persistent?|Persistence Method|
|---|---|---|---|
|Context|JS Memory|❌ No|Manual (localStorage/cookie)|
|Redux|JS Memory|❌ No|With `redux-persist`|
|Zustand|JS Memory|❌ No|Built-in `persist` middleware|

---

### 🔄 Summary

- React Context stores data **in-memory**, not in browser storage.
    
- It **does not persist** across refresh unless you manually sync it with persistent storage.
    
- For true persistence, combine context with `localStorage`, `cookies`, or a backend API call.

