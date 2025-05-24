---
created: 2025-05-22T15:46:51
status: 
source: 
updated: 2025-05-24T05:56
---
---

Problems we face without System design:

SOLID PRINCIPLES:
- `S`: Single Reponosibility Principle
- `O`: Open-close Principle
- `L`: Liskov Substitution Principle
- `I`: Interface Segregation Principle
- `D`: Dependency Inversion Principle


#### Single Responsibility Principle
- make sure each class have only one responsibility
	- so that they are not tightly couples
- it doesn't mean that each class should have only one method
	- it means that each class with handle one responsibilty with however methods needed

in **UML class diagrams**, `1..*` is the correct way to indicate that a class can be associated with **one or more** instances of another class.
![[Pasted image 20250523175902.png||500]]

#### Open close principle

- it says that a class should be open for extension and closed for modification
- means that if we are adding a new feature in out existing class then we should be able to do it without modifying existing methods and properties
- it's a very string method which cannot be followed always but we should try to follow it as much as possible
- 

