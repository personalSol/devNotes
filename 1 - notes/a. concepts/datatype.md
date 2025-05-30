---
status: newBorn
related-links: "[[Programming-Language-Concepts-MOC]]"
created: 2025-05-25T11:18
updated: 2025-05-26T08:53
---
---
##### basic
datatypes are specified with variables to tell the compiler how much space it need to allot to a particular variable
- first from left is reserved for sign 
- so the general the value range of a datatype for positive values is equal to 2^(number of bits - 1 ) - 1 
	- bits - 1 is for ommiting the first bit from left which is for sign
	- and - 1 is for including 0 as well 
- for negative values
	- it's 2^(number of bits - 1) 
	- no need to -1 extra as there is no negative 0
##### **How Data Types Are Stored (Binary Representation)**

| Sign Bit (0 = positive, 1 = negative) | Remaining bits store the value in binary (0s and 1s) |
| ------------------------------------- | ---------------------------------------------------- |
| `0`                                   | `0001010`                                            |
**Example: Storing `10` in 8 bits**

|0|0|0|0|1|0|1|0|
|---|---|---|---|---|---|---|---|
|**`0`** indicates the number is **positive**.||||||||

###### **Storing Negative Numbers: Two’s Complement Format**
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


---

##### sizes
- char in most programming languages have 1 byte of storage which means 8 bits
- int have 4 bits means 32 bits so it stores data

- [[cpp datatypes]]
- [[java datatypes]]
- 