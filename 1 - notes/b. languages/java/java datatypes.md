---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-11T15:15
updated: 2025-04-20T11:08
---
---

- variable size depends on the type of data it holds
- 1 byte represents 8 bits
- The first bit is used to store sign and all the other bits are used to store number

### **How Data Types Are Stored (Binary Representation)**

|Sign Bit (0 = positive, 1 = negative)|Remaining bits store the value in binary (0s and 1s)|
|---|---|
|`0`|`0001010`|
**Example: Storing `10` in 8 bits**

|0|0|0|0|1|0|1|0|
|---|---|---|---|---|---|---|---|
|**`0`** indicates the number is **positive**.||||||||

##### **Storing Negative Numbers: Two’s Complement Format**

To store `-10`, follow these steps:

1. Start with binary of `10`:  
    `00001010`
2. Get **1’s complement** (flip all bits):  
    `11110101`
3. Add `1` to get **2’s complement**:  
    `11110110`

|1|1|1|1|0|1|1|0|
|---|---|---|---|---|---|---|---|
|**`1`** as the first bit indicates it's **negative**.||||||||

---

**Why Two’s Complement?**

It simplifies arithmetic operations like subtraction. Using two’s complement, subtraction can be performed as addition internally, avoiding separate circuitry for negative numbers.

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
