---
status: newBorn
related-links: 
created: 2025-07-07T18:27
updated: 2025-07-12T14:16
---
---

### Static Variable in C++

```cpp
#include <iostream>
using namespace std;

void demoFunction() {
    static int counter = 0; // Initialized only once
    counter++;
    cout << "Counter: " << counter << endl;
}

int main() {
    demoFunction(); // Counter: 1
    demoFunction(); // Counter: 2
    demoFunction(); // Counter: 3
    return 0;
}
```

### Key Points:
- `static` variables are **initialized only once**.
- They **retain their value** between function calls.
- Unlike regular local variables, they are **not re-declared** or re-initialized with each call.

### Comparison:
| Variable Type | Initialization     | Lifetime           | Scope         |
|---------------|--------------------|--------------------|---------------|
| Normal local  | Every function call| Until function ends| Local function|
| Static local  | Only once          | Entire program run | Local function|

---

### Static Functions in C++

#### 1. **Static Member Functions**
- Belong to the class, not to an object.
- Cannot access non-static members/variables directly.
- Useful for utility-style functions or shared counters.

```cpp
#include <iostream>
using namespace std;

class Logger {
private:
    static int logCount;

public:
    static void log(const string& message) {
        logCount++;
        cout << "[Log " << logCount << "]: " << message << endl;
    }
};

int Logger::logCount = 0;

int main() {
    Logger::log("System started");
    Logger::log("User logged in");
    Logger::log("Error: File not found");
    return 0;
}
```

#### Output:
```
[Log 1]: System started
[Log 2]: User logged in
[Log 3]: Error: File not found
```

	#### 2. **Static Functions at File Scope** - not imp
- Declared with `static` outside of any class or function.
- Visible only within the file they are defined in.
- Often used in multi-file programs to limit scope.

```cpp
// file1.cpp
static void helper() {
    // Only accessible within file1.cpp
}
```

### Summary
- **Static variables** preserve state.
- **Static functions** can be class members or file-local.
- Use static when shared state or limited visibility is needed.


