---
status: newBorn
related-links: []
created: 2025-04-20T18:12
updated: 2025-04-20T18:12
---
---

> "Show only what’s important, and hide the messy details."

You **focus on _what_ an object does**, not _how_ it does it.

- You use abstract classes or interfaces to create abstraction.
- can create fields, constructor and full functions in abstract class.

```java
interface Animal {
    void makeSound();  // No details here
}

class Dog implements Animal {
	@Override
    public void makeSound() {
        System.out.println("Bark");
    }
}
```

- The `Animal` interface says: "Every animal can make a sound" — but **doesn’t say how**.
- Each animal (like `Dog`) decides **how** it makes that sound.

---

### ✅ Why Use Abstraction?

- Makes code **cleaner** and easier to understand
- Hides **unnecessary complexity**
- Helps in designing **reusable and flexible** code



# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 