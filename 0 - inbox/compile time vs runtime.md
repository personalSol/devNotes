---
status: newBorn
related-links: []
created: 2025-04-20T17:44
updated: 2025-04-20T17:45
---
---
### **Compile-time vs Runtime Errors**

#### ✅ **Compile-time Errors**
- **Happen before the program runs** (when Java is converting your code to bytecode).
- **Errors at this stage are called compile-time errors**.
- **Examples:**
  - Syntax mistakes
  - Missing semicolons
  - Calling a method that doesn’t exist
  - Using the wrong data type
  - Not properly overriding a method (if `@Override` is used)

➡️ **Java can't even understand your code to run it.**

---

#### ✅ **Runtime Errors**
- **Happen while the program is running**.
- **Errors at this stage are called runtime errors**.
- **Examples:**
  - Dividing by zero
  - Accessing a null object (`NullPointerException`)
  - File not found
  - Array index out of bounds

➡️ **The code was valid, but something went wrong during execution.**

---

#### ❗ **Logical Errors**
- **Can happen at runtime** but are not the same as runtime errors.
- **Don't crash the program**, but cause it to behave incorrectly.
- **Example:**
  ```java
  int a = 10, b = 5;
  System.out.println("Sum: " + (a - b));  // Oops! Meant to add, not subtract
```
➡️ **Logical errors occur when the code is valid but does the wrong thing.**


# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 