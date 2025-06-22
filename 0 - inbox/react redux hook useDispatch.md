---
status: newBorn
related-links: 
created: 2025-06-21T00:25
updated: 2025-06-21T01:12
---
---

- [[react redux hook useDispatch basics]]

### code

```jsx
    const [input, setInput] = useState("");
    const dispatch = useDispatch();
  
    const addTodoHandler = (e) => {
        e.preventDefault;
  
        dispatch(addTodo(input));
        setInput("");
    };
```