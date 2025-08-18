---
status: newBorn
related-links: 
created: 2025-06-21T01:12
updated: 2025-06-21T01:12
---
---

### Redux: `useDispatch` Hook

`useDispatch` is a React-Redux hook that allows components to send actions to the Redux store to update the state.

---

### What `useDispatch` Does

- **Dispatches an action** to the Redux store ==through reducer==
- **Sends a payload** (data) with the action.
- **Triggers the reducer**, which reads the action type and updates the state accordingly.

---

### Key Concepts

- **Action**: An object that describes what you want to do.

```js
{ type: 'ACTION_TYPE', payload: someData }
```

- **Reducer**: A function that takes the current state and an action, and returns the new state.
	- decides how to update the store using action
- **Payload**: The data you send with the action. It can be:
    - A single value
    - An object
    - Multiple values (packed inside an object)

---

### Syntax Example

```js
const dispatch = useDispatch();

// Dispatching with one payload
dispatch(addTodo('Learn Redux'));

// Dispatching with multiple data points (wrapped in an object)
dispatch(addTodo({ title: 'Learn Redux', priority: 'High' }));
```

---

### Additional Notes

- You **cannot directly send multiple separate payloads**.
    - Solution: Pass an **object** that contains multiple values.
    
    ```js
    dispatch(addTodo({ title: 'Task', priority: 'High' }));
    ```
    
- `dispatch` works by sending the action to the reducer, which decides how to update the store.
- `useDispatch` is **only for sending actions**.
    - It does not read or return state.
    - To read state, use `useSelector`.

---

### visual example

```text
dispatch(addTodo('Learn Redux')) 
        │
        ▼
Redux receives → { type: 'todo/addTodo', payload: 'Learn Redux' }
        │
        ▼
Redux automatically calls → reducer(currentState, action)

```

### Summary

|Concept|Purpose|
|---|---|
|`useDispatch`|Send actions to Redux store|
|`dispatch`|Send specific action + payload|
|Action|Describes what change is needed|
|Reducer|Handles the change in the store|


