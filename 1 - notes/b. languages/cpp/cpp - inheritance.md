---
status: newBorn
related-links:
  - "[[Cpp-MOC]]"
  - "[[cpp - oops]]"
created: 2025-05-15T19:41
updated: 2025-05-15T23:27
---
---

### inheritance types

When inheriting a class in C++, access to base class members changes based on the inheritance type:

#### 1. **Public Inheritance**

- `public` → stays `public`
- `protected` → stays `protected`
- `private` → inaccessible

> Used when the derived class **is-a** base class.

#### 2. **Protected Inheritance**

- `public` → becomes `protected`
- `protected` → stays `protected`
- `private` → inaccessible

> Used when you want to restrict further access but still allow subclasses.

#### 3. **Private Inheritance**

- `public` → becomes `private`
- `protected` → becomes `private`
- `private` → inaccessible

> Used when the derived class **uses** the base class internally, not meant to expose its interface.

NOTE: 99% of times we inherit a class publically as changing it breaks the inhritance rule for infinite inheritance 

# Reference
`related tags + notes + source + link(if any)`
 

- 