---
status: newBorn
related-links: "[[Java-MOC]]"
created: 2025-04-11T15:15
updated: 2025-05-25T11:35
---
---

- variable size depends on the type of data it holds
- 1 byte represents 8 bits
- The first bit is used to store sign and all the other bits are used to store number

how they are stored: [[datatype#How Data Types Are Stored Binary Representation]]

### Types of DATA TYPES:

##### a. primitive

These are the basic data types built into the language.

| Data Type | Size    | Description                          | Example             |
| --------- | ------- | ------------------------------------ | ------------------- |
| `byte`    | 1 byte  | Whole numbers from -128 to 127       | `byte a = 10;`      |
| `short`   | 2 bytes | Whole numbers from -32,768 to 32,767 | `short b = 1000;`   |
| `int`     | 4 bytes | Whole numbers from -2³¹ to 2³¹-1     | `int c = 100000;`   |
| `long`    | 8 bytes | Very large whole numbers             | `long d = 100000L;` |
| `float`   | 4 bytes | Single-precision decimal numbers     | `float e = 10.5f;`  |
| `double`  | 8 bytes | Double-precision decimal numbers     | `double f = 10.5;`  |
| `char`    | 2 bytes | A single 16-bit Unicode character    | `char g = 'A';`     |
| `boolean` | 1 bit   | `true` or `false`                    | `boolean h = true;` |
- in long we can write small L but it looks like 1 so big L is recommended
- if we write long without L then it's considered int and it can only store value upto into range
- by default java considers a decimal digit as double
- we can use capital F for float too
- float stores upto 6 decimal digits precisely
- double stores around 15

> **all primitive data types in Java have corresponding [[java wrapper classes]]!** ✅

---

##### b. non primitive ( reference )

These are objects and more complex types.

- **Strings** – A sequence of characters (e.g. `"Hello"`)
- **Arrays** – Collections of fixed-size elements (`int[] numbers = {1, 2, 3};`)
- **Classes** – Custom data structures (`class Person { ... }`)
- **Interfaces, Enums, etc.**


# Reference
`related tags + notes + source + link(if any)`
