---
status: newBorn
related-links: 
created: 2025-06-24T17:20
updated: 2025-06-24T17:20
---
---

### 📚 React `forwardRef` – Simple Notes

### 🚫 Problem Without `forwardRef`
When you use a custom component like this:
```jsx
<MyInput ref={inputRef} />
```
👉 **This will not work.**

- The `ref` will not reach the input box.
- The `ref` will only point to the whole `MyInput` component, not the real input inside it.

---

### ✅ Solution 1: Using `forwardRef`

#### 🔹 Why?  
`forwardRef` helps send the `ref` directly to the input inside the component.

#### 🔹 Example (Different Files)

##### 👉 MyInput.js
```jsx
import React from 'react';

const MyInput = React.forwardRef((props, ref) => {
    return <input ref={ref} {...props} />;
});

export default MyInput;
```

##### 👉 App.js
```jsx
import React, { useRef } from 'react';
import MyInput from './MyInput';

export default function App() {
    const inputRef = useRef();

    const focusInput = () => {
        inputRef.current.focus();  // ✅ This works now
    };

    return (
        <>
            <MyInput ref={inputRef} />
            <button onClick={focusInput}>Focus Input</button>
        </>
    );
}
```

#### ✅ Key Point:
- You can write `<MyInput ref={inputRef} />` directly.
- This is the **best and cleanest way.**

---

### ✅ Solution 2: Passing ref as a Normal Prop

#### 🔹 You can also pass the `ref` like a normal prop (not using `forwardRef`).

#### 🔹 Example (Different Files)

##### 👉 MyInput.js
```jsx
import React from 'react';

export default function MyInput({ inputRef }) {
    return <input ref={inputRef} />;
}
```

##### 👉 App.js
```jsx
import React, { useRef } from 'react';
import MyInput from './MyInput';

export default function App() {
    const inputRef = useRef();

    const focusInput = () => {
        inputRef.current.focus();  // ✅ This also works
    };

    return (
        <>
            <MyInput inputRef={inputRef} />  // Pass like a normal prop
            <button onClick={focusInput}>Focus Input</button>
        </>
    );
}
```

#### ✅ Key Point:
- You **must pass the ref as a normal prop** like this:  
  `inputRef={inputRef}`  
- This works, but it’s not the cleanest React style.

---

### ❌ What if You Make Local ref Inside MyInput?

#### 🔹 Example

##### 👉 MyInput.js
```jsx
import React from 'react';

export default function MyInput() {
    const inputRef = React.useRef();  // Local ref

    return <input ref={inputRef} />;
}
```

##### 👉 App.js
```jsx
import React from 'react';
import MyInput from './MyInput';

export default function App() {

    const focusInput = () => {
        // ❌ You can't control the input here
    };

    return (
        <>
            <MyInput />
            <button onClick={focusInput}>Focus Input</button>
        </>
    );
}
```

#### 🚫 Problem:
- The `ref` is local to **MyInput.**
- The parent cannot focus or control the input.
- The button won’t work.

---

### ✅ Quick Comparison Table

| Case | Can parent control input? | Can write `ref={inputRef}`? | Clean React style? |
|------|----------------------------|-----------------------------|--------------------|
| Using `forwardRef` | ✅ Yes | ✅ Yes | ✅ Best |
| Passing ref as prop | ✅ Yes | ❌ No | ⚪ Okay |
| Local ref inside | ❌ No | ❌ No | ❌ Not useful |


