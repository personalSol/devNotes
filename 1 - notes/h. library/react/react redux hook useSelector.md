---
status: newBorn
related-links: 
created: 2025-06-21T00:24
updated: 2025-06-24T11:37
---
---

- to select a value from store
	- we just use the value from 

```js
const todos = useSelector((store) => store.todos);
```

### right way to use `useSelector` properly

# Redux useSelector Notes for Todos.jsx

## Selector Line in Todos.jsx

```js
const todos = useSelector((store) => store.todos);
```

- This selector is **correct** for your current Redux store setup.

---

## Store Configuration

Your store is configured like this:

```js
export const store = configureStore({
    reducer: todoReducer
});
```

This means your Redux state shape is:

```js
{
  todos: [...]
}
```

---

## Alternative Store Configuration

If you configure your store like this:

```js
export const store = configureStore({
    reducer: { todo: todoReducer }
});
```

Then your state shape will be:

```js
{
  todo: {
    todos: [...]
  }
}
```

And you would need to use:

```js
const todos = useSelector((store) => store.todo.todos);
```

---

## Summary

- Use `store.todos` for your current setup.
- Use `store.todo.todos` only if you change your store reducer to `{ todo: todoReducer }`.