---
status: newBorn
related-links: 
created: 2025-08-01T00:56
updated: 2025-08-01T00:56
---
---

> basically spread array and object creation mai use hota hai and isme hum ek `entire` object/array ko destructure krdete hai and. REST mai hum ek object ke inner contents ko gather krte hai ek variable name ke under.
> 
> ex of rest. jaise ki ek object mai 5 fields hai. mujhe usme see 2 chayia toh maine unn 2 ke name destructure mai likhe and bakiyo ke liye maine `...restValues` likhdiya. toh yaha rest values ek object baan jayega jisme meri remaining 3 values hongi which I can use anywhere😁😁

- Both use `...` but have **different roles depending on context**

---

### 🟣 Rest Operator

**Used in:** Destructuring (objects or arrays)

**Purpose:** Collect remaining properties or elements into a new variable.

```js
const obj = { a: 1, b: 2, c: 3 };
const { a, ...rest } = obj;
// a = 1
// rest = { b: 2, c: 3 }
```

🔸 Think of it as: **"Give me what's left"**

---

### 🔵 Spread Operator

**Used in:** Object/array literals or function calls

**Purpose:** Expand contents into another object, array, or argument list.

```js
const obj1 = { b: 2, c: 3 };
const obj2 = { a: 1, ...obj1 };
// obj2 = { a: 1, b: 2, c: 3 }
```

🔸 Think of it as: **"Break this open and insert its pieces here"**

---

### ⚖️ Summary

|Operator|Context|Role|Example|
|---|---|---|---|
|`...rest`|Destructuring|Collect rest|`const { a, ...rest } = obj`|
|`...spread`|Object/Array usage|Expand contents|`{ ...obj }`, `[...arr]`|

---

### 💡 Tips

- `rest` collects leftover properties.
    
- `spread` spreads them out.
    
- They look the same, but **position matters**.

