---
status: newBorn
related-links:
  - "[[react-MOC]]"
created: 2025-03-11T11:11
updated: 2025-04-11T10:47
---
---

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