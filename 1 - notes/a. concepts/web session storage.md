---
status: newBorn
related-links: 
created: 2025-06-11T06:08
updated: 2025-06-11T06:08
---
---

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

