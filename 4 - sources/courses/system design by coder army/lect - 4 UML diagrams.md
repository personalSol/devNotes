---
created: 2025-05-16T18:58:40
status: 
source: 
updated: 2025-05-22T12:35
---
---

### What is UML?

- **UML (Unified Modeling Language)** is a standardized way to **visualize software systems**.
- It helps model the **structure and behavior** of a system before or during development.

UML diagrams are generally divided into two broad categories:
1. Structural diagram ( static diagram )
	- Called **static** because they show the **unchanging structure** of a system.
	- Focus on how things are **organized**, not how they behave.
	- Example: A **Class Diagram** shows classes and their relationships — this doesn’t change during runtime.

> 📌 Think of static diagrams as a **blueprint** – they define structure, not motion.

1. Behavioural diagram ( dynamic diagram )
	- Called **dynamic** because they model the **behavior over time**.
	- Focus on **what happens**, like interactions, workflows, and state changes.
	- Example: A **Sequence Diagram** shows the **order of messages** exchanged between objects during a process.

> 📌 Think of dynamic diagrams as a **movie script** – they show how things happen and change.


## structural diagram

- have 7 types
	- class diagram ⭐ ( used 99% of the time )
	- rest 6 have specific usecases

### class diagram

- tells class structure
- their association/connection with other classes
![[Pasted image 20250516192122.png]]

#### UML **Class Representation**

A class in UML is drawn as a **rectangle divided into 3 compartments**:
```pgsql
+----------------------+
|     ClassName        |   ← 1. Class Name
+----------------------+
| - attribute1: Type   |   ← 2. Attributes (fields)
| + attribute2: Type   |
+----------------------+
| + method1(): Return  |   ← 3. Methods (operations)
| - method2(param): T  |
+----------------------+
```

- **Key Symbols**
	- **+** → Public
	- **-** → Private
	- **#** → Protected
	- **~** → Package/Internal
- we add `<<static>>` at the top of class rectangle if the class is static

#### association

![[Pasted image 20250520180332.png||500]]

- whenever two classes are connected somehow then we say that those classe are connected
- are of two types
	1. class association
		- have inheritance
	2. object association
		- simple association
		- aggregation
		- composition
	- they are all same ( and are considered composition ) when we program but are theoritically different 


##### class association - inheritance

- inheritance have a ( is a ) relationship
- ex: cow is a animal, dog is a animal 
- in uml, we represent (is-a) relation with `■────▶`

##### object association  
- simple association have a ( has a ) relationship


**simple association**
- weaker relationship
- ex: arjun has a hourse ( yeah common in arjun lives in a house but we can derive that arjun has a )
- in uml, we represent (has-a) relation with `■────>`

**aggregation**
- here one object is an aggregator and contains multiple objects
- these objects can also individually exist ( means ki chair, table, sofa jaruri nhi room mai hi ho, they can be separately there as well )
- much stronger relationship that simple association
- ex: room contrains a chair, sofa, table
- shows with an empty diamond arrow
- in uml, we represent it with `◇───` 
- **Diamond is placed on the side of the container class**.

- ![[Pasted image 20250516195519.png||400]]

**composition**
- **Has-a** relationship where the **contained object can exist independently**.
- Denoted by: `◆—` (filled diamond)
- ex: chair contains wheels, seat, arms ( these individually have no usecase)
- - **Diamond is placed on the side of the container/owner class**.


## behavioural diagram

- have 7 types
	- sequence diagram 
	- rest 6 have specific usecases

### sequence diagram

- rarely asked in interviews
- but will be very helpful in some usecases
- shows how one object will communicate/interact with another
- we represent classes and variables by Characters and we don't have to show properties or anything
	- as we are onl telling how they interact with each other
- we create sequence diagram of each usecase
	- a single application can have 1000rs of sequence diagram according to flows


**Purpose**: Illustrate communication/interaction between objects in time sequence

**Elements**:
1. **Objects/Actors** (drawn at the top)
2. **Lifelines** (dotted vertical lines)
3. **Messages**:
    - **Synchronous**: Solid arrow with filled head
        - can send only one request at a time and then have to wait for response
    - **Asynchronous**: Solid arrow with open head
        - can send multiple requests at the same time without waiting for response
- **Object Creation**: `Create →`
- **Object Destruction**: `Destroy →` or marked with `X`
- **Control Structures**:
	- `alt`: if/else
	- `opt`: optional
	- `loop`: iteration (for/while

![[notes.pdf]]

- here transaction is a little down because that transaction never existed before while all the other things existed before.


# Reference
`related link(if any)`

