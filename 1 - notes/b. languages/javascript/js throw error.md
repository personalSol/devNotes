---
status: newBorn
related-links: 
created: 2025-05-21T12:41
updated: 2025-05-21T12:41
---
---

- `throw error` in a `catch` block **rethrows** the error after optional handling (like logging).
- It allows the error to **propagate up** to another `try...catch` or global handler.
- If you **don't throw**, the error is considered handled and won't bubble up.
- ✅ **Correct syntax**: `catch (error) { ... }`
- ❌ **Wrong syntax**: `catch { (error) => { ... } }` (invalid function syntax)
- Use rethrowing when you **log or partially handle** the error but can't fully resolve it.

