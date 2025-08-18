---
status: newBorn
related-links: 
created: 2025-06-16T11:23
updated: 2025-06-16T11:23
---
---

- zustand helps us in creating a global state which we can use anywhere
- it saves us from a big chain of importing that state using props.
![[Pasted image 20250404141621.png]]
- also only the component that uses it have to re-render and not the parent ones which just bacame a importing medium ( matlab yaar ek se dusri file mai import krenge toh woh saari files jisme yee state thi woh re-render hogi akar state change hui, pr akar apan zustand see ek global state banayenge toh sirf wahi component re-render hoga )
- humko haar jagha pass nhi krna padega woh state as a parameterr just because child ke child ke child ko woh state use krna hai


