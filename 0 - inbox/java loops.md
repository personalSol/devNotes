---
status: newBorn
related-links: []
created: 2025-04-12T13:16
updated: 2025-04-12T13:27
---
---


#### for-each

The `for-each` loop in Java (also known as the **enhanced for loop**) is a simpler way to iterate over arrays or collections like `ArrayList`, `HashSet`, etc., without using an index or iterator manually.

**Syntax:**
```java
for (type variable : collection) {
    // code to be executed
}
```

**Code:**
```java
int[] numbers = {1, 2, 3, 4, 5};

for (int num : numbers) {
    System.out.println(num);
}


import java.util.ArrayList;

ArrayList<String> fruits = new ArrayList<>();
fruits.add("Apple");
fruits.add("Banana");
fruits.add("Mango");

for (String fruit : fruits) {
    System.out.println(fruit);
}
```


##### Note:
- You **can't modify** the collection (like remove elements) using a for-each loop.
- You **can't access the index** of elements directly.
- Ideal when you just want to **read or print** values.



# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 