---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-10T19:07
updated: 2025-04-15T10:09
---
---

the basic simple meaning of access-modifiers is it modifies who can access that method or class

Java has four main access levels:

![[Pasted image 20250414081624.png]]

| Access Modifier          | Accessible From                                                                                                                        |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| `public`                 | **Anywhere** (any class in any package)                                                                                                |
| `protected`              | Same package + subclasses (even in other packages). means in the other package we have to inherit(extent the subclass with superclass) |
| `default` _(no keyword)_ | Same package only                                                                                                                      |
| `private`                | Only within the same class                                                                                                             |

---

### Summary Table:

|Modifier|Same Class|Same Package|Subclass (other package)|Other Packages|
|---|---|---|---|---|
|`public`|✅|✅|✅|✅|
|`protected`|✅|✅|✅|❌|
|`default`|✅|✅|❌|❌|
|`private`|✅|❌|❌|❌|


## code example of protected inheritance

Folder structure:
```css
src/
├── animals/
│   └── Animal.java
└── zoo/
    └── Lion.java
```

📄 `Animal.java` (in package `animals`)
```java
package animals;

public class Animal {
    protected String name = "Generic Animal";

    protected void makeSound() {
        System.out.println("Animal makes a sound");
    }
}
```

📄 `Lion.java` (in package `zoo`, subclass of `Animal`)
```java
package zoo;

import animals.Animal;

public class Lion extends Animal {
    public void roar() {
        System.out.println("Lion name: " + name); // ✅ protected member accessed via inheritance
        makeSound(); // ✅ protected method accessed via inheritance
        System.out.println("Lion roars loudly!");
    }

    public static void main(String[] args) {
        Lion lion = new Lion();
        lion.roar();

        Animal animal = new Animal();
        // animal.name = "Some Animal"; // ❌ Can't access protected via object from another package
        // animal.makeSound();          // ❌ Same here
    }
}
```

# Reference
`related tags + notes + source + link(if any)`
 

- 