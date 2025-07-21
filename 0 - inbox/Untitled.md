---
status: newBorn
related-links: 
created: 2025-07-19T19:55
updated: 2025-07-19T19:55
---
---

### Euclidean Algorithm for GCD

#### What is it?

The **Euclidean Algorithm** is an efficient method to compute the **greatest common divisor (GCD)** of two integers `a` and `b`.

> It is based on the principle:  
> `GCD(a, b) = GCD(b, a % b)`, where `a > b`

---

#### How It Works

1. Given two integers `a` and `b` (`a > b`), compute `a % b`.
    
2. Replace `a` with `b` and `b` with `a % b`.
    
3. Repeat the process until `b` becomes 0.
    
4. When `b == 0`, the GCD is the value of `a`.
    

---

#### Example

Find `GCD(48, 18)`:

```
GCD(48, 18)
→ 48 % 18 = 12 → GCD(18, 12)
→ 18 % 12 = 6  → GCD(12, 6)
→ 12 % 6 = 0   → GCD = 6
```

---

#### Iterative Code in C++

```cpp
int gcd(int a, int b) {
    while(b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}
```

---

#### Time Complexity

- **Worst-case Time Complexity**: `O(log(min(a, b)))`
    
- Reason: With each step, the numbers reduce rapidly (at least by half in many cases).
    
- This makes it **very efficient** even for large integers.

