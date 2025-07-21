---
status: newBorn
related-links: 
created: 2025-07-19T19:55
updated: 2025-07-21T06:48
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
#include<bits/stdc++.h>
class Solution {
public:
    int GCD(int n1,int n2) {
        while(n1 != 0 && n2 != 0){
            if(n1>n2){
                n1 = n1 % n2;
                continue;
            } else{
                n2 = n2 % n1;
                continue;
            }
        }

        if(n1==0){
            return n2;
        }
        return n1;
    }
};
```

---

#### Time Complexity

- **Worst-case Time Complexity**: `O(log(min(a, b)))`
    
- Reason: With each step, the numbers reduce rapidly (at least by half in many cases).
    
- This makes it **very efficient** even for large integers.

