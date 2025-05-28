---
status: newBorn
related-links:
  - "[[Cpp-MOC]]"
  - "[[cpp enum]]"
created: 2025-05-19T09:54
updated: 2025-05-19T09:54
---
---

## 🔵 5. Enum Class (Scoped Enums)
Introduced in C++11 for safety and clarity.

### Benefits:
- Values are scoped (`Difficulty::Hard` instead of just `Hard`)
- Prevents implicit conversion to/from int
- Avoids name conflicts

### Example:
```cpp
enum class Difficulty {
    Easy = 1,
    Medium = 5,
    Hard = 10
};

Difficulty level = Difficulty::Hard;
```

### Printing Enum Class Values:
```cpp
cout << static_cast<int>(level);  // Need to cast to int
```

### Enum Class in switch:
```cpp
switch (level) {
    case Difficulty::Easy:
        // code
        break;
}
```


