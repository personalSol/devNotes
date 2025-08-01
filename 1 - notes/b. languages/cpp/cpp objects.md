---
status: newBorn
related-links:
  - "[[Cpp-MOC]]"
created: 2025-05-18T21:29
updated: 2025-07-03T11:08
---
---

- [[objects]]

### 🔹 Summary: Stack vs Heap Allocation
  
| Feature            | Stack Allocation         | Heap Allocation                |
| ------------------ | ------------------------ | ------------------------------ |
| Syntax             | `Robot r1;`              | `Robot* r2 = new Robot;`       |
| Storage            | Stack                    | Heap                           |
| Lifetime           | Auto                     | Manual (use `delete`)          |
| Access             | `ob.method()`            | `ob->method()`                 |


### 🔹 Object Creation

#### Step 1: Create a Blueprint (Class or Struct)
```cpp
class Robot {
public:
    string name;

    void sayHello() {
        cout << "Hello! I am " << name << endl;
    }
};
```

#### Step 2: Creating an object
---
 - Stack (automatic):
	- Auto destroyed when it goes out of scope/function ends
	- Fast
- **Heap (dynamic)**: ^55qbbg
	- Manual delete needed
	- Lives until you `delete` it
#### object in cpp code
```cpp
// stack ( automatic )
Robot r1; // Uses default constructor
r1.name = "ABC";
r1.sayHello();

// heap ( dynamic )
Robot* r2 = new Robot();
r2->name = "EVA";
r2->sayHello();
delete r2; // Manual cleanup required

// we can also use
(*r2).sayHello()

```
### why do we have to use delete with new

```cpp
MyClass* obj = new MyClass();
```


- `new` allocates memory on **heap**.
- `*` is used because `new` returns a **pointer**.
- You need it because `new` gives you a **memory address**, not the object itself.
- Stack holds the pointer; **heap holds the object**.
- When function ends, stack pointer is gone, but heap memory stays.
- ❗️Always `delete` if you used `new`
