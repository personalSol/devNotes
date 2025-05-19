---
status: newBorn
related-links:
  - "[[Cpp-MOC]]"
  - "[[cpp enum class]]"
created: 2025-05-19T09:53
updated: 2025-05-19T09:53
---
---

### 🧠 Summary
| Feature                 | `enum`       | `enum class`     |
| ----------------------- | ------------ | ---------------- |
| Scoped names            | ❌ No         | ✅ Yes            |
| Implicit int conversion | ✅ Yes        | ❌ No (need cast) |
| Safer & modern          | ❌ No         | ✅ Yes            |
| Recommeded for new code | ❌ Not really | ✅ Definitely     |


### 🟢 1. What is an Enum?
An `enum` (short for "enumeration") is a user-defined type that lets you assign names to a set of fixed values.

### Example:
```cpp
enum Mood {
    Happy,
    Sad,
    Angry
};
```

### ✅ Why Use Enums?
- Makes code easier to read and maintain
- Groups related constants under one name
- Reduces mistakes (compared to using plain numbers)

---

### 🟡 2. How Enums Work (Under the Hood)
- Values are actually integers starting from 0 by default.
```cpp
enum Outfit { Knight, Wizard, Ninja };  // Knight = 0, Wizard = 1, Ninja = 2
```

---

### 🟠 3. Custom Enum Values
You can assign specific integer values to each name.
```cpp
enum Difficulty {
    Easy = 1,
    Medium = 5,
    Hard = 10,
    Insane = 20
};
```

- These are constants, not variables.
- You can use them in comparisons and switch statements.

---

### 🔁 4. Enums in `switch` Statements
```cpp
switch (currentLevel) {
    case Hard:
        cout << "Hard mode selected.";
        break;
}
```
This works because enums are just integers underneath.

---


