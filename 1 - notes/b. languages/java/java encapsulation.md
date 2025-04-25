---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-20T18:08
updated: 2025-04-24T21:54
---
---

- basic meaning: [[encapsulation]]

### 💻 In Java terms:

- We **hide variables** inside a class using `private`
- We use **`get` and `set` methods** to access or change those variables

---

### ✅ Why use encapsulation?

- Protect data from being changed in the wrong way
- Control how data is accessed or updated
- Makes the code easier to manage and safer

---

### 📦 Simple Java Example:

```java
public class Person {
    // Private variable (hidden from outside)
    private String name;

    // Getter - to read the name
    public String getName() {
        return name;
    }

    // Setter - to change the name
    public void setName(String newName) {
        name = newName;
    }
}
```

🧪 Using the class:
```java
Person p = new Person();
p.setName("John");             // set the name
System.out.println(p.getName());  // get the name
```




# Reference
`related tags + notes + source + link(if any)`
 

- 