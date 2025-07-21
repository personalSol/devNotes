---
status: newBorn
related-links: 
created: 2025-07-21T10:41
updated: 2025-07-21T11:15
---
---

### in short
- when a function calls itself
- until a specific condition is met
- A **recursion tree** is a visual diagram showing how a recursive function branches and when each call stops. It helps analyze the total number of calls and complexity.


### detailed

- **When a function calls itself**, it is called **recursion**.
- This continues **until a specific base condition is met**, which helps **terminate** the recursive calls.
- **If no base condition is met**, or if the base condition is unreachable, **infinite recursion occurs**, which leads to a **stack overflow error**.
- In recursion:
    - Each time the function calls itself, **a new stack frame** is created **on the call stack**.
    - These stack frames hold local variables, return addresses, and function parameters.
    - The stack frames are **not created inside the previous one**, but rather **added on top of the call stack**.
    - Once the base condition is met and the function returns, the stack frames **start to unwind** (i.e., they are popped off the stack in reverse order of their creation).
- **Recursion tree**:
	- A **recursion tree** is a visual representation of the **function call flow**.
	- It shows **how many times the function runs**, how it **branches**, and where the **calls stop** (i.e., where base conditions are met).
	- It helps analyze the **number of calls** and **overall time complexity**.

```cpp
#include<bits/stdc++.h>
using namespace std;

int cnt = 0;
void print(){
    if(cnt == 10) return;
    cnt++;
    cout<<"hii: "<<cnt<<endl;
    print();
}

int main(){
    print();
}
```