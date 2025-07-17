---
status: newBorn
related-links: 
created: 2025-06-21T00:22
updated: 2025-06-24T10:54
---
---

``` js
// slice file

import { createSlice, nanoid } from '@reduxjs/toolkit';

const initialState = {
    todos: [
        {
            id: 1,
            todo: "hello text",
        },
    ],
};

export const todoSlice = createSlice({
    name: 'todo',
    initialState,
    reducers: {
        addTodo: (state, action) => {
            const todo = {
                id: nanoid(),
                todo: action.payload,
                // We can pass an object in the payload if needed, 
                // but since we only need a single value from the user, it's not required here.
            };
            state.todos.push(todo);
        },
        removeTodo: (state, action) => {
            state.todos = state.todos.filter((todo) => todo.id !== action.payload);
        },
        updateTodo: (state, action) => {
            state.todos = state.todos.map((todo) =>
                todo.id === action.payload.id
                    ? { ...todo, todo: action.payload.todo }
                    : todo
            );
        },
    },
});

export const { addTodo, removeTodo, updateTodo } = todoSlice.actions;

export default todoSlice.reducer;


```

- reducer: (from what i understood) it is the medium through which we modify state in store
	- basically we have multiple mini stores so what will update and how functionality is inside reducer
- slice contains: 
	- name, initialState, reducers :{key: property, key: function}
- the name we give while creating slice is the name which will be shown in tools like redux dev extension
- 2nd we give initial state of the data we want to save
	- don't know why in initial state we saves it in todos and not directly an arroy of objects with 1st object as data
- reducer: stores variable and function
	- each function have two predefined output with their meanings 
	- state is used to access the current state of whatever we are saving
	- action helps us access payload passed by client
- it's syntax that we use `todoSlice.reducer` so that our main which is store.js can use these reducers
	- to make sure that these reducers are real etc
- we also export functions/our reducers which we got through actions
	- exporting them so we can import them in components where we want to use them

