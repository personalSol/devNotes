---
status: newBorn
related-links: 
created: 2025-06-11T07:31
updated: 2025-06-12T10:41
---
---

- we create validation schemas
- use those validation schemas inside our function where we want to validate
- returns an object
- object.success value returns true or false

```js
const { z } = require('zod');

// Step 1: Basic structure
const userSchema = z.object({
  email: z.string()
    .email({ message: "Invalid email format. Please enter a valid email address." }),
  
  password: z.string()
    .min(8, { message: "Password must be at least 8 characters long." })
    .max(20, { message: "Password must not exceed 20 characters." })
    .refine((val) => /[A-Z]/.test(val), { message: "Password must include at least one uppercase letter." })
    .refine((val) => /[a-z]/.test(val), { message: "Password must include at least one lowercase letter." })
    .refine((val) => /[0-9]/.test(val), { message: "Password must include at least one number." })
    .refine((val) => /[!@#$%^&*(),.?":{}|<>]/.test(val), { message: "Password must include at least one special character." })
});

// Example input
const userInput = {
  email: 'abc@domain.com',
  password: 'weakpass' // Example: Missing uppercase, number, special char
};

try {
  userSchema.parse(userInput);
  console.log('Validation passed!');
} catch (err) {
  console.log('Validation errors:');
  console.log(err.errors);
}
```

### ✅ Explanation:

- `.refine()` allows **custom checks with specific errors**.
- Each `.refine()` adds a **separate validation rule** with its own message.
- This way, you can **catch multiple errors at once**.

### output

```js
Validation errors:
[
  { message: 'Password must include at least one uppercase letter.', path: [ 'password' ] },
  { message: 'Password must include at least one number.', path: [ 'password' ] },
  { message: 'Password must include at least one special character.', path: [ 'password' ] }
]
```