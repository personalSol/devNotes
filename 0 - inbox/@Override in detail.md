---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-20T17:47
updated: 2025-04-20T18:07
---
---

- it tells the compiler you're overriding a method from the parent class.
- ✅ With `@Override`
	- Compiler checks if the method actually exists in the parent.
	- Gives an error if there's a mismatch (e.g., typo or wrong parameters).
	- Helps catch bugs early.
	- Improves code readability and clarity.
- ❌ Without `@Override`
	- No compiler check.
	- If method matches perfectly → still overrides correctly.
	- If there's a small mistake (e.g., typo) → Java treats it as a **new method**, and no error is shown.
	- Can lead to silent bugs.

- CASES: there are basically three cases in it:
	- when we @Override a method correctly using `@Override`
	- when we `@Override` but doesn't write annotation
	- when we don't override method but write annotation

Case 1: correct way
``` java
class test1 {
    String makeSound() {
        return "Bark!";
    }
}

class polymorph extends test1 {
    @Override
    String makeSound() {
        return "Barking!";
    }
}
```

Case 2: works but prone to heavy errors
```java
// this one still works as mentioned above but it wouldn't give error if we make any mistake in name or anything and will just create a new method

class test1 {
    String makeSound() {
        return "Bark!";
    }
}

class polymorph extends test1 {
    // No @Override here
    String makeSound() {
        return "Barking!";
    }
}
```

Case 3: will give compile time error ( as we aren't overriding anything )
```java
class test1 {
    String makeSound() {
        return "Bark!";
    }
}

class polymorph extends test1 {
    @Override
    String eating() {
        return "eating!";
    }
}
```



# Reference
`related tags + notes + source + link(if any)`
 
- [[tG function overridding]]
- 