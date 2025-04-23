---
status: newBorn
related-links:
  - "[[react-MOC]]"
created: 2025-03-11T11:11
updated: 2025-04-22T16:50
---
---

Link: [useState – React](https://react.dev/reference/react/useState#adding-state-to-a-component)

- syntax: `const [state, setState] = useState(initialState)`
- setState: used to set new value to state
- **Two Update Styles**:
    - **Direct**: `setState(newValue)` → Replaces state.
    - **Functional**: `setState(prev => prev + 1)` → Uses previous state.
- **Initial Value**: Set once on first render (`useState(0)` → 0 is initial).
- **Async**: Updates batched; state doesn’t change immediately.  
    - can check it by immediately logging state  
    - but it does update which we can see on the second `console.log`  
    - preState is like .then in promise. the next one works when the previous one completes
- **Batching**: Multiple `setState` calls in same event → merged.
    - **Reset on Reload**: State is in-memory → reload = reinitialize.
    - **Persist State**: Use `localStorage`/backend to save across reloads.
- it is prefered that we change or update the value of state directly inside setState and not first update it and then load it.


in setState update styles:
- it's set that in function method we will use previous state value so it doesn't matter what we name it
- though it's prefered to use first letter of state name
- setState is async and batched all the function together. 

what I have understood is it batches all the setCount and after that is completed it updates the state value for re render. And that's why new value only shows after re render even in code 2.


##### code:
```javascript
const [count, setCount] = useState(0);

  function increCount() {
    // setCount((c) => c + 1);
    // setCount((c) => c + 1);
    // setCount((c) => c + 1);
    setCount(count + 1);
    setCount(count + 1);
    setCount(count + 1);
    console.log(count);
  }

  return (
    <>
      <button onClick={increCount}>counter is {count}</button>
    </>
  );
```

##### code 2: 

```javascript
import { useState } from "react";
import "./App.css";

function App() {
  const [count, setCount] = useState(0);

  function increCount() {
    setCount((c) => c + 1);
    console.log(count);
    setCount((c) => c + 1);
    console.log(count);
    setCount((c) => c + 1);
    console.log(count);
  }

  return (
    <>
      <button onClick={increCount}>counter is {count}</button>
    </>
  );
}

export default App;
```



# Reference
`related tags + notes + source + link(if any)`
 

- 