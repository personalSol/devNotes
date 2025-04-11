---
status: adult
related-links:
  - "[[Core-Concepts-MOC]]"
created: 2025-02-24T22:11
updated: 2025-02-25T00:04
---
---

break down of when to use each one (and when not to).

### Types of Browser Storage

- Web Storage (Local & Session)
- Cookies
- IndexedDB

### Web Storage: The Simple One

#### Local Storage

Local Storage **stays saved even when you close and reopen your browser.**

✅ **Perfect for:**

- User setting preferences
    
- Theme settings
    
- Shopping cart items
    
- Language choice
    

❌ **Avoid for:**

- Sensitive data
    
- Large objects
    
- Frequently changing data
    

``` javascript
// ✅ Good Storage Usage
localStorage.setItem('theme', 'dark');
localStorage.setItem('language', 'en');
sessionStorage.setItem('formStep', '2');

// ❌ Bad Storage Usage
localStorage.setItem('creditCard', '4111-1111-1111-1111');
localStorage.setItem('bigData', JSON.stringify(hugeObject));
```

#### Session Storage

Similar to local storage except it **DOES NOT save when you close and reopen your browser.**

 ✅ **Perfect for:**

- Form wizard data
    
- Multi-step processes
    
- Temporary user state
    

❌ Avoid for:

- Data needed after tab close
    
- Cross-tab communication
    
- Long-term storage
    

``` javascript
// ✅ Good SessionStorage Usage
sessionStorage.setItem('formStep', '2');
sessionStorage.setItem('tempData', JSON.stringify(formData));

// ❌ Bad SessionStorage Usage
sessionStorage.setItem('userPreferences', preferences);
```

### Cookies: The Classic One

A Cookie is a small piece of data a server sends to a user's web browser.

Cookies will also stay saved even when you close and reopen your browser.

 ✅ Perfect for:

- Authentication
    
- Server-side needed data
    
- Cross-subdomain data
    
- User Tracking (yeah…)
    
- Small bits of data (4KB limit)
    

❌ Avoid for **(kinda)**:

- Large amounts of data (that’s why we have databases)
    
- Client-only data (local storage could do that for us, **but this depends on the situation**)
    
- Frequent updates (You’ll be transferring additional data to the server every time you make a request. More so if you are storing a lot of data into the cookies.)
    

Disclaimer: Cookies are honestly good for a lot of things, but it all depends on the situation.

``` javascript
document.cookie = 'sessionId=abc123; Secure; SameSite=Strict';
document.cookie = 'theme=dark; max-age=31536000';
```

### Cookies Vs Local Storage

Cookies and local storage serve different purposes.

Cookies are primarily for **reading server-side**, while local storage can **only be read by the client-side.**

### IndexedDB: The Powerful One

A SQL-based DB system that’s meant for **storing larger amounts of structured data.**

 ✅ Perfect for:

- Large datasets
    
- Offline apps
    
- File/blob storage
    
- Complex data structures
    

❌ Avoid for:

- Simple key-value pairs
    
- Small amounts of data
    
- Anything that local storage/cookies could handle
    

``` javascript
let db; 
// Opening or creating our database with a name and an ID 
// We call this request because we're "requesting" this database
const request = window.indexedDB.open("coolDatabase", 1) 

request.onerror = (event) => { 
  // Do something with request.error 
  console.error("Why didn't you allow my web app to use IndexedDB?"); }; 

request.onsuccess = (event) => { 
  // Do something with request.result 
  db = event.target.result 
};
```

### Quick Storage Size Limits

- LocalStorage: ~5-10MB
    
- SessionStorage: ~5-10MB
    
- Cookies: ~4KB
    
- IndexedDB: Several GB
    

- Need server access? → Cookies
    
- Temporary data? → SessionStorage
    
- Simple client data? → LocalStorage
    
- Complex/large data? → IndexedDB
    

### Remember

- Always validate stored data
    
- Clear sensitive data
    
- Handle storage errors
    
- Check available space
    
- Consider privacy modes

# Reference
`related notes + source + link(if any)`
 
