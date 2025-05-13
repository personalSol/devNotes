---
created: 2025-05-09T10:44
updated: 2025-05-12T17:28
---
  

# 🧠 C++ Cheatsheet (With Explanations)

  

## 📌 Basics

```cpp

#include <iostream>

using namespace std;

  

int main() {

    cout << "Hello, World!" << endl;

    return 0;

}

```

- `#include <iostream>`: includes input/output stream.

- `main()` is the program's entry point.

- `cout`, `cin` are used for output/input.

  

---

  

## 📦 Data Types

| Type       | Description          | Example             |
|------------|----------------------|---------------------|
| `int`      | Integer values       | `int x = 42;`       |
| `float`    | Floating point       | `float f = 3.14;`   |
| `double`   | Double precision     | `double d = 9.81;`  |
| `char`     | Character            | `char c = 'A';`     |
| `bool`     | Boolean true/false   | `bool b = true;`    |
| `string`   | Text string          | `string s = "Hi";`  *(`#include <string>`)*


---

  

## 🔁 Control Structures

```cpp

if (x > 0) { ... }

else if (x < 0) { ... }

else { ... }

  

for (int i = 0; i < 10; i++) { ... }

while (condition) { ... }

do { ... } while (condition);

```
  

---

  

## 🧮 Operators

| Type        | Operators             
|-------------|------------------------|
| Arithmetic  | `+ - * / %`            |
| Logical     | `&& || !`              |
| Comparison  | ` == != < > <= >= `      |
| Bitwise     | `& | ^ ~ << >>`        |
| Assignment  | ` = += -= *= /= %= `     |

  

---

  

## 🧰 Functions

```cpp

int add(int a, int b) {

    return a + b;

}

```

- Functions allow reusable blocks of code.

  

---

  

## 🔤 I/O

```cpp

cin >> name;

cout << "Hi " << name << endl;

```

- `cin` reads input, `cout` prints output.

  

---

  

## 📚 Arrays & Vectors

```cpp

int arr[3] = {1, 2, 3};

  

#include <vector>

vector<int> v = {1, 2, 3};

v.push_back(4);

v.size();

```

- `array` is fixed size.
- `vector` is dynamic and resizable.

---

  

## 📦 Structs & Classes

```cpp

struct Point {

    int x, y;

}; // Struct groups related variables.

  

class Person {

public:

    string name;

    int age;

  

    Person(string n, int a) : name(n), age(a) {}

    void greet() {

        cout << "Hi, I'm " << name << endl;

    }

};

```

- `struct`: groups variables, members public by default.

- `class`: encapsulates data/functions, members private by default.

  

---

  

## 🧱 Inheritance

```cpp

class Animal {

public:

    void speak() { cout << "Generic sound\n"; }

};

  

class Dog : public Animal {

public:

    void speak() { cout << "Woof!\n"; }

};

```

- Enables code reuse and polymorphism.

  

---

  

## 🧠 Pointers

```cpp

int x = 10;

int* p = &x;

cout << *p << endl; // 10

```

- Store address of variables.

  

---

  

## 🔄 References

```cpp

void modify(int& x) {

    x += 5;

}

```

- Alias for another variable.

  

---

  

## 🛠️ STL Containers

  

### `vector` (dynamic array)

```cpp
#include <vector>
vector<int> v = {1, 2};
v.push_back(3);
```

  

### `deque` (double-ended queue)

```cpp

#include <deque>

deque<int> dq;

dq.push_front(1);

dq.push_back(2);

```

  

### `list` (doubly-linked list)

```cpp

#include <list>

list<int> lst = {1, 2, 3};

```

  

### `stack` (LIFO)

```cpp

#include <stack>

stack<int> st;

st.push(1); st.pop();

```

  

### `queue` (FIFO)

```cpp

#include <queue>

queue<int> q;

q.push(1); q.pop();

```

  

### `priority_queue` (heap)

```cpp

#include <queue>

priority_queue<int> pq;

pq.push(10); pq.top();

```

  

### `set` (unique sorted elements)

```cpp

#include <set>

set<int> s = {1, 2, 2}; // stores 1, 2

```

  

### `multiset` (sorted duplicates allowed)

```cpp

#include <set>

multiset<int> ms;

ms.insert(1); ms.insert(1);

```

  

### `unordered_set` (hash table)

```cpp

#include <unordered_set>

unordered_set<int> us = {1, 2};

```

  

### `map` (key-value, sorted by key)

```cpp

#include <map>

map<string, int> m;

m["age"] = 25;

```

  

### `unordered_map` (hash map)

```cpp

#include <unordered_map>

unordered_map<string, int> um;

um["a"] = 1;

```

  

---

  

## ⚙️ Algorithms (`<algorithm>`)

```cpp

#include <algorithm>

sort(v.begin(), v.end());

reverse(v.begin(), v.end());

auto it = find(v.begin(), v.end(), 3);

count(v.begin(), v.end(), 3);

```

  

---

  

## 🧼 Memory Management

```cpp

int* ptr = new int(5);

delete ptr;

  

int* arr = new int[10];

delete[] arr;

```

  

---

  

## 🧪 Exception Handling

```cpp

try {

    throw runtime_error("Error");

} catch (exception& e) {

    cout << e.what();

}

```

- Use for error handling.

  

---

  

## 🧾 Namespace

```cpp

namespace myspace {

    int val = 100;

}

cout << myspace::val;

```

  

---

  

## 🧩 Templates

```cpp

template<typename T>

T add(T a, T b) {

    return a + b;

}

```

- Enables generic programming.

  

---

  

## 🧹 Smart Pointers (`<memory>`)

```cpp

#include <memory>

unique_ptr<int> up = make_unique<int>(10);

shared_ptr<int> sp = make_shared<int>(20);

```