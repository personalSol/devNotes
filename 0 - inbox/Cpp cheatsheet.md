---
status: newBorn
related-links: []
created: 2025-05-09T10:44
updated: 2025-05-09T10:46
---


Here's a properly formatted Markdown (.md) file for your C++ cheatsheet, optimized for Obsidian:

### Basic Data Types
- `int`: Whole numbers (e.g., 1, 2, etc.)
- `char`: Single character (e.g., 'A', 'B')
- `float`: Floating-point numbers (e.g., 3.14)
- `double`: Double-precision floating-point numbers
- `bool`: Boolean values (true/false)
- `void`: No type

### Modifiers
- `short`, `long`
- `unsigned`, `signed`

### Example
```cpp
int num = 10;
char letter = 'A';
```

### Sizeof Operator
```cpp
sizeof(int) // Returns the size of int in bytes
```

---

## Operators
### Arithmetic Operators
- `+` Addition
- `-` Subtraction
- `*` Multiplication
- `/` Division
- `%` Modulus

### Assignment Operators
- `=` Assignment
- `+=`, `-=`, `*=`, `/=`, `%=`

### Comparison Operators
- `==` Equal to
- `!=` Not equal to
- `>` Greater than
- `<` Less than
- `>=` Greater than or equal to
- `<=` Less than or equal to

### Logical Operators
- `&&` Logical AND
- `||` Logical OR
- `!` Logical NOT

### Increment/Decrement Operators
- `++a` Pre-increment
- `a++` Post-increment

### Bitwise Operators
- `&` Bitwise AND
- `|` Bitwise OR
- `^` Bitwise XOR
- `~` Bitwise NOT
- `<<` Left shift
- `>>` Right shift

### Ternary Operator
```cpp
condition ? true_expression : false_expression;
```

---

## Control Structures
### If-Else Statement
```cpp
if (condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```

### Switch-Case Statement
```cpp
switch (variable) {
    case 1:
        // Code to execute if variable == 1
        break;
    case 2:
        // Code to execute if variable == 2
        break;
    default:
        // Code to execute if no cases match
        break;
}
```

### Loops
#### For Loop
```cpp
for (int i = 0; i < 5; i++) {
    // Code to execute
}
```

#### While Loop
```cpp
while (condition) {
    // Code to execute
}
```

#### Do-While Loop
```cpp
do {
    // Code to execute
} while (condition);
```

### Jump Statements
- `break`: Exits the nearest enclosing loop or switch statement
- `continue`: Skips the rest of the current iteration and moves to the next one
- `goto`: Jumps to a labeled statement

---

## Functions
### Function Declaration
```cpp
return_type function_name(parameters) {
    // Function body
}
```

### Function Parameters
- Pass by value: `func(int x)`
- Pass by reference: `func(int &x)`

### Function Overloading
```cpp
int add(int a, int b);
double add(double a, double b);
```

### Default Arguments
```cpp
void func(int a, int b = 5);
```

---

## Arrays and Vectors
### Arrays
```cpp
int arr[5] = {1, 2, 3, 4, 5};
```

### Vectors
```cpp
#include <vector>
std::vector<int> vec = {1, 2, 3};
```

---

## Pointers
### Pointer Declaration
```cpp
int *ptr;
```

### Dynamic Memory Allocation
```cpp
int* p = new int;   // Allocate memory
delete p;           // Deallocate memory
```

---

## Classes and Objects
### Class Definition
```cpp
class MyClass {
private:
    int x;          // Private member variable
public:
    MyClass() {     // Constructor
        x = 0;
    }
    ~MyClass() {    // Destructor
        // Cleanup code
    }
    void func();    // Member function
};
```

---

## File Handling
### Reading from a File
```cpp
#include <fstream>
std::ifstream infile("file.txt");
```

### Writing to a File
```cpp
#include <fstream>
std::ofstream outfile("file.txt");
```

---

## Additional Features
### Namespaces
```cpp
using namespace std;
```

### Templates
```cpp
template <typename T>
T max(T a, T b) {
    return (a > b) ? a : b;
}
```

### Exception Handling
```cpp
try {
    // Code that may throw an exception
} catch (exception_type) {
    // Code to handle the exception
}
throw exception; // Throw an exception
```

### Smart Pointers
```cpp
#include <memory>
std::unique_ptr<int> ptr(new int); // Unique pointer
std::shared_ptr<int> ptr(new int);  // Shared pointer
```

### Lambda Expressions
```cpp
[] (int x) { 
    // Code to execute
};
```

### Move Semantics
```cpp
std::string a = "Hello";
std::string b = std::move(a); // Transfer ownership
```

### Multithreading
```cpp
#include <thread>
std::thread t(func); // Create a new thread
```

---

You can copy this entire content into a new note in Obsidian. The Markdown formatting will make it easy to read and navigate. You can also expand on any section as needed!