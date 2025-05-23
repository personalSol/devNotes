---
status: newBorn
related-links: "[[React-MOC]]"
created: 2025-04-25T18:14
updated: 2025-05-23T09:11
---
---

![[Pasted image 20250425180815.png||500]]



#### ✅ **Trigger:**

- A change occurs: `setState()`, `props`, or context update.

---

### 🎨 **Phase 1: Rendering**

- **What Happens:**  
    React calls your component function and **converts JSX into a new Virtual DOM**.
- **Key Output:**  
    New **Virtual DOM**

---

### 🔍 **Phase 2: Reconciliation**

This is React's smart diffing and updating phase.

- **Step 1: Diffing (Comparison)**
    - Compare the **new Virtual DOM** with the **old Virtual DOM**
    - Find what changed
- **Step 2: DOM Updates (Patching)**
    - Apply only the necessary changes to the **Real DOM**
    - Very efficient: only the changed nodes are updated

✅ **Both of these steps (diffing + patching)** are part of **Reconciliation**
❌ Updating the real DOM is **not just** reconciliation — it's the final part of the reconciliation process.

### diagram

```sql
1. Trigger: state/prop/context change
       ↓
2. Rendering: JSX → New Virtual DOM
       ↓
3. Reconciliation:
     a. Diffing: Compare new VDOM with old VDOM
     b. Patching: Apply changes to the Real DOM
```

---
