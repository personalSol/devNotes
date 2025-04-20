---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-11T15:58
updated: 2025-04-11T16:02
---
---

#### 📦 What is Autoboxing?

**Autoboxing** is the automatic conversion of a **primitive type** (like `int`, `char`, etc.) into its **corresponding wrapper class object** (like `Integer`, `Character`, etc.).

```java
int num = 5;
Integer obj = num; // ✅ Autoboxing: int → Integer
```

#### 🔓 What is Unboxing?

**Unboxing** is the automatic conversion of a **wrapper class object** back into a **primitive type**.

```java
Integer obj = 10;
int num = obj; // ✅ Unboxing: Integer → int
```

#### ✅ Why is it Helpful?

| Benefit                                | Example                                                               |
| -------------------------------------- | --------------------------------------------------------------------- |
| 1. **Cleaner code**                    | No need to manually convert between primitive and object types.       |
| 2. **Works smoothly with collections** | Collections like `ArrayList` need objects — autoboxing makes it easy. |
| 3. **Reduces boilerplate**             | Avoids calls like `new Integer(5)` or `obj.intValue()` manually.      |

#### ✨ Real-World Example

✅ With Autoboxing & Unboxing

```java
List<Integer> list = new ArrayList<>();
list.add(100); // Autoboxing: int → Integer

int num = list.get(0); // Unboxing: Integer → int
```

❌ Without Autoboxing & Unboxing

```java
List<Integer> list = new ArrayList<>();
list.add(Integer.valueOf(100)); // Manual boxing

int num = list.get(0).intValue(); // Manual unboxing
```

# Reference
`related tags + notes + source + link(if any)`
 

- 