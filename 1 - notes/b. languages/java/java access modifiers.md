---
status: newBorn
related-links:
  - "[[Java-MOC]]"
created: 2025-04-10T19:07
updated: 2025-04-11T10:56
---
---

the basic simple meaning of access-modifiers is it modifies who can access that method or class

Java has four main access levels:

|Access Modifier|Accessible From|
|---|---|
|`public`|**Anywhere** (any class in any package)|
|`protected`|Same package + subclasses (even in other packages)|
|`default` _(no keyword)_|Same package only|
|`private`|Only within the same class|

---

### Summary Table:

|Modifier|Same Class|Same Package|Subclass (other package)|Other Packages|
|---|---|---|---|---|
|`public`|✅|✅|✅|✅|
|`protected`|✅|✅|✅|❌|
|`default`|✅|✅|❌|❌|
|`private`|✅|❌|❌|❌|





# Reference
`related tags + notes + source + link(if any)`
 

- 