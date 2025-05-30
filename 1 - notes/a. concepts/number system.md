---
status: newBorn
related-links: "[[Basic-Concepts-MOC]]"
created: 2025-05-25T09:05
updated: 2025-05-25T09:05
---
---

Number systems define how we represent numbers using symbols or digits. Different systems use different bases:

### 1. **Decimal (Base-10)**
- Digits: `0–9`
- Most commonly used in daily life.
- Each digit is a power of 10.
- Example: `321 = 3×10² + 2×10¹ + 1×10⁰`

### 2. **Binary (Base-2)**
- Digits: `0, 1`
- Used by computers and digital electronics.
- Each digit is a power of 2.
- Example: `1011 = 1×2³ + 0×2² + 1×2¹ + 1×2⁰ = 11`

### 3. **Octal (Base-8)**
- Digits: `0–7`
- Sometimes used in computing (e.g., file permissions in Unix).
- Example: `73 (octal) = 7×8¹ + 3×8⁰ = 56 + 3 = 59`

### 4. **Hexadecimal (Base-16)**
- Digits: `0–9, A–F` (A=10 to F=15)
- Common in programming (e.g., memory, colors).
- Example: `1F = 1×16¹ + 15×16⁰ = 16 + 15 = 31`

---

## 🔁 Conversion Techniques

### 🔄 Decimal to Other Bases

- **To Binary**: Divide by 2, keep remainders.
- **To Octal**: Divide by 8, keep remainders.
- **To Hex**: Divide by 16, use 0–9 and A–F.

#### Example: Decimal 59
- Binary: 59 → 111011
- Octal: 59 → 73
- Hex: 59 → 3B

### 🔄 Binary to Decimal

- Multiply each bit by 2 raised to its position (right to left).
- Example: `1011 = 1×8 + 0×4 + 1×2 + 1×1 = 11`

### 🔄 Binary to Octal/Hex

- **To Octal**: Group bits in 3s from the right.
- **To Hex**: Group bits in 4s from the right.

#### Example: Binary `111011`
- Octal: `111 011` → `7 3` → 73
- Hex: `0011 1011` → `3 B` → 3B

### 🔄 Octal/Hex to Binary

- **Octal → Binary**: Each digit → 3-bit binary
  - 7 → 111, 3 → 011 → Binary = `111011`
- **Hex → Binary**: Each digit → 4-bit binary
  - 3 → 0011, B → 1011 → Binary = `00111011`


## 🧠 Binary Grouping Tips

- Group from right, pad with 0s on the left if needed.
- Octal groups = 3 bits, Hex groups = 4 bits.
- Example: `Binary 1011` = `Octal 13`, `Hex B`

---

### 📋 System Overview

| System       | Base | Digits           | Used In                        |
|--------------|------|------------------|--------------------------------|
| Decimal      | 10   | 0–9              | Human-readable numbers         |
| Binary       | 2    | 0, 1             | Computers, logic circuits      |
| Octal        | 8    | 0–7              | Unix file permissions          |
| Hexadecimal  | 16   | 0–9, A–F (10–15) | Programming, memory, colors    |

### 📋 Example Conversions

| System   | Value | Decimal | Binary   | Octal | Hex |
|----------|-------|---------|----------|-------|-----|
| Decimal  | 59    | 59      | 111011   | 73    | 3B  |
| Binary   | 1011  | 11      | 1011     | 13    | B   |
| Octal    | 73    | 59      | 111011   | 73    | 3B  |
| Hex      | 3B    | 59      | 00111011 | 73    | 3B  |


