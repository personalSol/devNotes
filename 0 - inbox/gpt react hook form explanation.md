---
status: newBorn
related-links: 
created: 2025-07-25T01:15
updated: 2025-07-25T01:15
---
---

### React Hook Form – Simple Explanation

#### 🧠 What is React Hook Form?

React Hook Form is a small library that helps manage forms in React. It:

- Collects input values
    
- Validates them
    
- Handles form submission
    

All of this with **less code** and **better performance**.

---

#### 🔧 How it works

You start by importing and using the `useForm()` hook.

```js
import { useForm } from 'react-hook-form';
```

This gives you useful tools to manage your form.

```js
const { register, handleSubmit } = useForm();
```

---

### ✏️ `register`

The `register` function is used to **connect your input fields** to React Hook Form.

It automatically:

- Tracks the value
    
- Applies validation
    
- Helps collect all input values on submit
    

#### ✅ Usage:

```js
<input {...register("email")} />
```

Here, `"email"` is a unique name used as the **key** for this field in the final form data.

---

#### ⚙️ With Validation:

```js
<input
  {...register("email", {
    required: true,
    validate: value =>
      value.includes("@") || "Email must include '@'"
  })}
/>
```

- `required: true` → Input is mandatory
    
- `validate: fn` → A custom function to check value
    
    - If `fn` returns `true`, input is valid
        
    - If it returns a string, that becomes the error message
        

---

### 📤 `handleSubmit`

This is used to wrap your `onSubmit` function.

```js
<form onSubmit={handleSubmit(onSubmit)}>
```

#### 🔁 What happens when you submit the form?

1. All fields are validated.
    
2. If any field is **invalid**, `onSubmit` is **not called**.
    
3. If all fields are **valid**, then:
    
    - Form data is collected
        
    - Your `onSubmit(data)` function is called with the values
        

So:

> `handleSubmit` **stops invalid data** from going into `onSubmit`.

---

### ✅ Full Example:

```jsx
import { useForm } from 'react-hook-form';

function MyForm() {
  const { register, handleSubmit } = useForm();

  const onSubmit = (data) => {
    console.log(data); // { email: "...", password: "..." }
  };

  return (
    <form onSubmit={handleSubmit(onSubmit)}>
      <input
        {...register("email", {
          required: true,
          validate: value => value.includes("@") || "Invalid email"
        })}
        placeholder="Email"
      />
      <input
        type="password"
        {...register("password", { required: true })}
        placeholder="Password"
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

---

### 🔒 Summary

- `register` connects each input to the form and handles its value and validation.
    
- `handleSubmit`:
    
    - Runs validation
        
    - Prevents `onSubmit` if any validation fails
        
    - Only passes valid data to `onSubmit(data)`

