---
status: newBorn
related-links: []
created: 2025-04-20T18:12
updated: 2025-04-20T18:12
---
---

| Feature      | Encapsulation                     | Abstraction                           |
| ------------ | --------------------------------- | ------------------------------------- |
| Hides        | Data (fields)                     | Implementation details (logic)        |
| Focuses on   | Data protection & access control  | Functionality design & simplification |
| Achieved via | `private` fields, getters/setters | `abstract` classes, `interface`s      |
| Goal         | Safely expose the internals       | Show only necessary parts to the user |

```java

// encapsulation

class Account {
    private double balance;  // hidden data

    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }

    public double getBalance() {
        return balance;
    }
}


// abstraction

abstract class Animal {
    abstract void makeSound();  // No implementation
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Bark");
    }
}

```



# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 