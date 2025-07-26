---
status: newBorn
related-links: 
created: 2025-06-21T00:24
updated: 2025-07-26T22:47
---
---

- to select/read a value from store
	- we just use the value from 
- here store is the name of store and todos is the name of slice. 
- doing this gives us the value of initial state
- if we are storing the reducer directly like firsst example below then we directly use it
	- but if we have multiple reducers then we create an object and then we have to include the reducer key accordingly like in 2nd example
- for better understanding check: [[full code example of redux]]

```js
const todos = useSelector((store) => store.todos);
```


---

#### Store Configuration

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

#### Alternative Store Configuration

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

#### Summary

- Use `store.todos` for your current setup.
- Use `store.todo.todos` only if you change your store reducer to `{ todo: todoReducer }`.