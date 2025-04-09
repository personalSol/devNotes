---
status: teenager
related-links:
  - "[[tG-java]]"
  - "[[Cheatsheets-MOC]]"
created: 2025-02-10T23:09
updated: 2025-04-07T13:32
---
---

# -1. things to remember

- arrays have length property and string have length() function
# 0. Basics

- No support for negative indexing

#### Loops
- in java loop, iteration depends totally on condition
	- the last iteration isn't exclusive ( like in python )
###### - for loop
```Java
String[] friends = {"Rahul", "Simran", "Kiran", "Naina", "Aman"};
for (int i = 0; i < friends.length; i++) {
  System.out.println(friends[i]);
}
```

###### - for each loop
- very simple: just creates a temperorary variable and pass it through array
- no indexing or counting or length needed

```Java
String[] friends = {"Rahul", "Simran", "Kiran", "Naina", "Aman"};
for (String friend : friends) {
  System.out.println(friend);
}
```


#### Methods
- functions because inside a class are methods in java

**Default parameter:**



#### Type Conversions

```Java
// Primitive ↔ Wrapper
int num = Integer.valueOf("100"); // String → Integer → int
String s = String.valueOf(100);    // int → String

// String ↔ Primitive
String s = Integer.toString(10);  // int → String
int x = Integer.parseInt("20");   // String → int

// Primitive ↔ char (ASCII)
char c = (char) 65; // 'A'
int ascii = 'A';    // 65
```


# 1. Primitive Data Types

- Fixed size, stored directly in memory.

| **Type**  | **Size** | **Range/Values**              | **Example**            | **Key Notes**                                                             |
| --------- | -------- | ----------------------------- | ---------------------- | ------------------------------------------------------------------------- |
| `byte`    | 1 byte   | -128 to 127                   | `byte b = 100;`        | Used for small integers to save memory.                                   |
| `short`   | 2 bytes  | -32,768 to 32,767             | `short s = 200;`       | Rarely used; larger than `byte`, smaller than `int`.                      |
| `int`     | 4 bytes  | -2³¹ to 2³¹-1                 | `int i = 1000;`        | Default choice for integers.                                              |
| `long`    | 8 bytes  | -2⁶³ to 2⁶³-1                 | `long l = 5000L;`      | Append `L` to denote long.                                                |
| `float`   | 4 bytes  | ~±3.4e³⁸ (7 decimal digits)   | `float f = 3.14f;`     | Append `f` to denote float. Less precise than `double`.                   |
| `double`  | 8 bytes  | ~±1.7e³⁰⁸ (15 decimal digits) | `double d = 3.14;`     | Default choice for decimals.                                              |
| `char`    | 2 bytes  | Unicode (0 to 65,535)         | `char c = 'A';`        | Single quotes for literals. Can store symbols, letters, and ASCII values. |
| `boolean` | 1 bit    | `true` or `false`             | `boolean flag = true;` | Used for logical conditions. Not compatible with `0`/`1` (unlike C/C++).  |

##### a. char
---
to take a char input:
```java
import java.util.*;

public class input_char {

    public static void main(String[] args){

        // Create Scanner object
        Scanner input = new Scanner(System.in);

        // Take character input
        System.out.println("Enter any character value:");
        char character = input.next().charAt(0);

        // Print input values
        System.out.println("Character Value: " + character);

        // close the Scanner object
        input.close();

    }

}
```


# 2. Non-Primitive Data Types

Objects stored as references; size depends on the object

##### a. **Strings**

- **Immutable**: Once created, value cannot be changed.
- **Memory Efficiency**: Uses the **String Pool** for reusability.
- in string == operator checks if both the 

```Java
	String s1 = "Hello";           // Uses String Pool  
String s2 = new String("Hello"); // Creates a new object in heap

// Example String
String str = "  Hello World!  ";

// --- Methods ---
str.length();                      // Returns 14 (includes spaces)
str.charAt(1);                     // ' ' (space at index 1)
str.substring(6);                  // "World!  " (from index 6)
str.substring(0, 5);               // "  Hell" (indices 0-4)
str.trim();                        // "Hello World!" (removes leading/trailing spaces)
str.toUpperCase();                 // "  HELLO WORLD!  "
str.toLowerCase();                 // "  hello world!  "
str.replace('l', 'z');             // "  Hezzo Worzd!  " (replaces all 'l's)
str.replace("World", "Java");      // "  Hello Java!  " (replaces substring)
str.indexOf('W');                  // 7 (first occurrence of 'W')
str.contains("Hello");             // true
str.startsWith("  ");              // true
str.endsWith("!  ");               // true
str.split(" ");                    // ["", "", "Hello", "World!", "", ""]
str.equals("hello world!  ");      // false (case-sensitive)
str.equalsIgnoreCase("HELLO WORLD!  "); // true

```


##### b. **Arrays**

- non primitive datatype
- Fixed-size ( while initializing, can omit while declaring )
- store one type of data in one array
- index based
- mutable collections
- unlike other programming languages have 'length' property
- can't store objects

###### - Single Dimensional Array

**Common Methods**:

- `Arrays.toString(arr)` → Converts an array to a readable string.
- `Arrays.equals(arr1, arr2)` → Checks if two arrays are equal.

```Java

import java.util.Arrays

// declaring: dataType arr[]; OR dataType[] arr; OR dataType []arr;
int[] arr1 = {1, 2, 3};           // Inline initialization  
int[] arr2 = new int[5];          // Default values: [0, 0, 0, 0, 0]

// --- Methods/Operations ---
Arrays.sort(numbers);              // Sorts array → [1, 2, 3, 5, 8]
Arrays.binarySearch(numbers, 3);   // Returns 2 (index of 3 in sorted array)
Arrays.fill(numbers, 0);           // Fills array → [0, 0, 0, 0, 0]
Arrays.copyOf(numbers, 3);         // New array → [0, 0, 0] (truncated)
Arrays.toString(numbers);          // "[0, 0, 0, 0, 0]"

// --- Property ---
int arrayLength = arr1.length;

```

###### - Multi Dimentional Array
```Java

int[][] matrix = {{1, 2}, {3, 4}}; // 2D array  
matrix[0][1] = 10;                 // Modifies → [[1, 10], [3, 4]]

// --- example code ---
int[][] a = {
	{ 1, 2, 3 },
	{ 4, 5, 6, 7 },
	{ 8, 9 },
	{10}
	};

// calculate and display the length of each row
for (int i = 0; i < a.length; i++) {
	System.out.println("row no. " + (i + 1) + ", length of that row : " + a[i].length);
}

// --- end example ---
```


# **3. Wrapper Classes**

- Convert primitives to objects (e.g., `int` ↔ `Integer`)
- Autoboxing: int → Integer
- Autoboxing: int → Integer

##### Integer

```Java

// properties
int largest = Integer.MIN_VALUE;

```

```Java

// Integer Example
Integer num = 10;      // Autoboxing: int → Integer
Integer num = Integer.valueOf(10); // Creates Integer object
int n = num;           // Autoboxing: int → Integer
int n = num.intValue();            // Extracts primitive → 10

// String ↔ Primitive Conversions
Integer.parseInt("123");     // String → int (123)
String s = Integer.toString(123);  // int → String
Integer val = Integer.valueOf("100"); // String → Integer
Double.parseDouble("3.14");  // String → double (3.14)

// int <-> Integer
Integer.valueOf(100);        // int → Integer

// Comparison
Integer a = 10, b = 20;
a.compareTo(b);                    // Returns -1 (10 < 20)
Integer.max(a, b);                 // Returns 20

```

# **4. Collections Framework**

##### **Lists**
- Mutable
- ordered collections
- allow duplicates


Syntax
```java
List<DataType> variableName = new ArrayList<>(initialCapacity); // Optional initial capacity
```

###### a. ArrayList
- Dynamic array
- can store objects 

```Java

List<String> list = new ArrayList<>();
list.add("Apple");                 // [Apple]
list.add(0, "Banana");             // [Banana, Apple] -- basically add at index or at last
list.set(1, "Cherry");             // [Banana, Cherry] -- replaces
list.remove(0);                    // [Cherry]
list.size();                       // 1
list.contains("Cherry");           // true
list.clear();                      // Empties the list

```

###### b. **LinkedList**
- Doubly-linked list

```Java
LinkedList<String> ll = new LinkedList<>();
ll.addFirst("A");     // Add to front
ll.pollLast();        // Remove last element
```

##### **Sets**
---
- No Duplicates

###### a. **HashSet** 
- Unordered
- fast access

```Java

Set<Integer> set = new HashSet<>();
set.add(10);                       // [10]
set.add(20);                       // [10, 20]
set.remove(10);                    // [20]
set.isEmpty();                     // false

```

###### b. **TreeSet**
- Sorted order

```Java
TreeSet<Integer> tree = new TreeSet<>();
tree.add(5);
tree.first();         // 5 (smallest element)
```

##### **Maps**
---
- Key-Value Pairs

###### **HashMap**
- Unordered

```Java 

Map<String, Integer> ages = new HashMap<>();
ages.put("Alice", 25);             // {Alice=25}
ages.put("Bob", 30);               // {Alice=25, Bob=30}
ages.get("Alice");                 // 25
ages.replace("Bob", 35);           // {Alice=25, Bob=35}
ages.containsKey("Alice");         // true

```

###### **LinkedHashMap**
- Insertion-order preserved

```Java
LinkedHashMap<String, Integer> lmap = new LinkedHashMap<>();
```

##### **Common Collections Methods**

- `Collections.sort(list);` // Sort a list
    
- `Collections.reverse(list);` // Reverse elements
    
- `Collections.shuffle(list);` // Randomly shuffle

# 5. Utility Classes

- All methods are **static** (no instance needed).

#### 1. **`java.util.Collections`**

**Purpose**: Operate on collections (lists, sets, etc.).  
**Common Methods**:

- `Collections.sort(list)` → Sorts a list.
- `Collections.reverse(list)` → Reverses a list.
- `Collections.shuffle(list)` → Randomly shuffles a list.
- `Collections.max(collection)` → Finds the maximum element.
- `Collections.frequency(collection, obj)` → Counts occurrences of an object.
- `Collections.synchronizedList(list)` → Creates a thread-safe list.

---

#### 2. **`java.util.Objects`**

**Purpose**: Null-safe operations and object utilities.  
**Common Methods**:

- `Objects.equals(a, b)` → Null-safe equality check.
- `Objects.hashCode(obj)` → Null-safe hash code.
- `Objects.requireNonNull(obj)` → Throws `NullPointerException` if `obj` is null.
- `Objects.isNull(obj)` → Checks if `obj` is `null`.
- `Objects.toString(obj, defaultStr)` → Converts `obj` to a string (with a default if `null`).

---

#### 3. **`java.lang.Math`**

**Purpose**: Mathematical operations.  
**Common Methods**:

- `Math.abs(x)` → Absolute value.
- `Math.sqrt(x)` → Square root.
- `Math.pow(a, b)` → (a^b).
- `Math.max(a, b)` / `Math.min(a, b)` → Returns the greater/smaller value.
- `Math.random()` → Random number between 0.0 and 1.0.
- `Math.round(x)` → Rounds a float/double to the nearest integer.


# **6. Miscellaneous**

###### **Varargs**
Variable-length arguments.

```Java
 void printAll(String... strings) { /* ... */ }
```
   
###### **Ternary Operator**:

``` Java
 int max = (a > b) ? a : b;
 ```

###### **Loops**:

```Java
for (int i : list) { ... }      // Enhanced for-loop
while (condition) { ... }
do { ... } while (condition);
```        

# Alternatives ( advance )
###### Mutable String Alternatives

- **StringBuilder** (non-thread-safe, fast):

```Java

StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");               // "Hello World"
sb.insert(5, " Java");             // "Hello Java World"
sb.delete(5, 10);                  // "Hello World"
sb.reverse();                      // "dlroW olleH"
sb.replace(0, 5, "Hi");            // "Hi olleH"
sb.length();                       // 8

```

- **StringBuffer** (thread-safe, slower).
#### **Key Concepts**:

1. **Immutability**:
    - `String`, `Integer`, `Double`, etc., cannot be modified after creation.
    - Methods like `substring()`, `toUpperCase()` return **new objects**.
2. **Mutability**:
    - Arrays, `StringBuilder`, and collections (e.g., `ArrayList`) can be modified in-place.
3. == vs .equals():
    - Use == for **primitive** value comparison.
    - Use `.equals()` for **object content** comparison (e.g., `String`, `Integer`).
4. Pass-by-Value:
    - Java passes object **references by value** (changes to object’s state persist, reassigning references does not).




## Reference
`related notes + source + link(if any)`
 
