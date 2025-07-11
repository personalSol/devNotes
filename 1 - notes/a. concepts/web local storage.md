---
status: newBorn
related-links: 
created: 2025-06-11T06:07
updated: 2025-06-18T17:24
---
---

#### Local Storage

> only stores things in string format so before giving it value, we have to save it as string before we set it. same with get, we have to convert it from string if needed as per case 

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

