---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-11T15:48
updated: 2025-04-11T16:03
---
---

### 🧾 **Primitive Types & Their Wrapper Classes**

| Primitive Type | Wrapper Class | Example Constant or Method                     |
| -------------- | ------------- | ---------------------------------------------- |
| `byte`         | `Byte`        | `Byte.MAX_VALUE`, `Byte.parseByte()`           |
| `short`        | `Short`       | `Short.MIN_VALUE`                              |
| `int`          | `Integer`     | `Integer.parseInt("123")`                      |
| `long`         | `Long`        | `Long.toString(123L)`                          |
| `float`        | `Float`       | `Float.isNaN(3.14f)`                           |
| `double`       | `Double`      | `Double.parseDouble("3.14")`                   |
| `char`         | `Character`   | `Character.isDigit('7')`                       |
| `boolean`      | `Boolean`     | `Boolean.TRUE`, `Boolean.parseBoolean("true")` |

# 🧱 What are Wrapper Classes?

Wrapper classes are like **boxes** that hold primitive values (`int`, `char`, `boolean`, etc.) and turn them into **objects**.

Think of it like this:

> 🔢 `int` is just a number — but `Integer` is a **box** that holds that number and gives you some **extra tools** to work with it.

---

## ✅ Why Do We Need Wrapper Classes?

| Reason                             | Example                                                                 |
|------------------------------------|-------------------------------------------------------------------------|
| 1. To use primitives where objects are required | `List<Integer> numbers = new ArrayList<>();`                             |
| 2. To access helpful methods       | `int num = Integer.parseInt("123");`                                    |
| 3. To use constants                | `int max = Integer.MAX_VALUE;`                                          |
| 4. To allow `null` values          | `Integer x = null;` <br> `int y = null; // ❌ Error`                     |

---

## 🔁[[autoboxing and unboxing in java]]

Java automatically converts between primitives and wrapper classes:

```java
Integer a = 5;   // autoboxing: int -> Integer
int b = a;       // unboxing: Integer -> int
```



# Reference
`related tags + notes + source + link(if any)`
 

- 